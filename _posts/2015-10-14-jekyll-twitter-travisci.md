---
title: Tweet your blog post title with Jekyll
---

1. Add `gem 't'` to your Gemfile
2. `bundle install`
3. `bundle exec t authorize` and follow instructions to get [API keys](https://apps.twitter.com/).
4. Permissions must be *'Read and Write'*
5. Once authenticated, the permissions are stored in `~/.trc`. We will need this file to tweet once the deployment successful, but as this file contains sensitive information, you want to secure it via `travis encrypt-file` like this:

{% gist c6d97f59656d802b9f32 %}

Now let's see what happen in the rake task `tweet_last_article`. Two parts :

**1.Before Deployment,** we check if we have an unpublished article and retrieve its title and url.

We go through the list of `_posts` files and take the last one. Grab the title from the content if any or build the one from the filename. Then goes the URL also building the last name.

{%gist 8e89571a7b0637c5b703 %}

*Note that the base URL could certainly be retrieved from somewhere else, but I didn't look more into it.*

Don't forget to execute it before the deployment to Github:

{%gist e7362d86fdfae6560455 %}

**2.After successful deployment**, we tweet any message created before the deployment.

{%gist 52a3a45e5e1392129877 %}

And so we will need to add the following to `.travis.yml`:

{% gist 39680add2472addded06 %}

That's it! if you think there's another simpler, more secure solution or any improvements, let me know on [Twitter](https://twitter.com/netbeatwork).
