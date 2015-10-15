source 'https://rubygems.org'

require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'jekyll', versions['jekyll']
gem 'jekyll-compose'

group :jekyll_plugins do
  gem 'jekyll-picture-tag', '~> 0.2.3'
end
gem 'redcarpet'
# custom deployment as Github Pages does not support all plugins like picture-tag
gem 'rake'
gem 'rake-jekyll'

gem 'travis'

gem 't'
