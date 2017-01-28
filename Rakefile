require 'rake-jekyll'
require 'net/http'

TWEET_FILE="new-article.txt"

Rake::Jekyll::GitDeployTask.new(:deploy) do |t|

  # Description of the rake task.
  t.description = 'Generate the site and push changes to remote repository'

  # Overrides the *author* of the commit being created with author of the
  # source commit (i.e. HEAD in the current branch).
  t.author = -> {
    `git log -n 1 --format='%aN <%aE>'`.strip
  }
  # Overrides the *author date* of the commit being created with date of the
  # source commit.
  t.author_date = -> {
    `git log -n 1 --format='%aD'`.strip
  }
  # The commit message will contain hash of the source commit.
  t.commit_message = -> {
    "Built from #{`git rev-parse --short HEAD`.strip}"
  }
  # Use 'Jekyll' as the default *committer* name (with empty email) when the
  # user.name is not set in git config.
  t.committer = 'Jekyll'

  # Deploy the built site into remote branch named 'gh-pages'. It will be
  # automatically created if not exist yet.
  t.deploy_branch = 'master'

  # Run this command to build the site.
  t.jekyll_build = ->(dest_dir) {
    Rake.sh "bundle exec jekyll build --destination #{dest_dir}"
  }
  # Use the default committer (configured in git) when available.
  t.override_committer = true

  # Use URL of the 'origin' remote to fetch/push the built site into. If env.
  # variable GH_TOKEN is set, then it adds it as a userinfo to the URL.
  t.remote_url = -> {
    `git config remote.origin.url`.strip.gsub(/^git:/, 'https:').tap do |url|
      url.gsub!(%r{^https://}, "https://#{ENV['GH_TOKEN']}@") if ENV.key? 'GH_TOKEN'
    end
  }
  # Skip commit and push when building a pull request or env. variable
  # SKIP_COMMIT represents truthy.
  t.skip_commit = -> {
    ENV['TRAVIS_PULL_REQUEST'].to_i > 0 ||
      %w[yes y true 1].include?(ENV['SKIP_COMMIT'].to_s.downcase)
  }
end

desc "Check if we have a new article and create the message"
task :prepare_new_article_tweet do
  title, article_url  = last_article
  # Check if article already published
  uri = URI(article_url)
  res = Net::HTTP.get_response(uri)
  if res.is_a?(Net::HTTPNotFound)
    puts "If successful deployment, we should tweet"
    message = "#{title} - #{article_url}"
    system "echo #{message} > #{TWEET_FILE}"
  else
    puts "Last article already published"
  end
end

desc "Tweet the newly published article"
task :tweet do
  if File.exists?(TWEET_FILE)
    message = File.read(TWEET_FILE)
    puts "Tweeting #{message}"
    `bundle exec t update "#{message}" -P .trc`
  end
end

def last_article
  filename =  nil

  Dir.chdir("_posts") do
    filenames = `git ls-files`.split("\n")
    filename = filenames.last
  end

  title = nil
  # Try to find title inside article
  File.read("_posts/#{filename}").each_line do |line|
    next if /^---$/.match(line)
    if match = /title: (.*)/.match(line)
      title = match[1]
      break
    end
  end
  basename = filename.split('.')[0]
  matched, year, month, day, name = /^(\d{4})-(\d{2})-(\d{2})-(.*)$/.match(basename).to_a
  if title.nil?
    # build title from filename if not found
    title = name.gsub(/-/, ' ').capitalize
  end
  article_url = "https://netbe.github.io/#{year}/#{month}/#{day}/#{name}"
  return title, article_url
end
