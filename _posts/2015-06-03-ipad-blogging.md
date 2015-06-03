---
title: Blogging on iPad
---

Last weekend, I tried to finish the setup of this blog (layout and images) but I had only my iPad mini with me, but because everything was hosted on Github I thought it would be *easy* to do it.

So I googled a little bit about people blogging with Jekyll and iPad. Most of them combine  and I did not find any ~~good~~ free solution[^1]. Besides I needed to edit the config to resolve the issue with the first article's image (too big, needing to be resized).


## Config and Images

Though I manage to commit directly on Github and see the result of the generated page, I needed at one point edit my `Gemfile` so to regenerate the `Gemfile.lock`, and that was definitely not possible on a simple editor. I needed a server, hopefully I remembered the [Cloud9 service](http://cloud9.io) and could have my own console to run commands like `bundle install` and even serving the website on it.

One issue though is that it does not support mobile devices yet:

* Can't copy/paste
* Can't run a command again
* ...

## Thoughts

Create a mobile app that would:

* retrieve website content from github
* build and serve the website locally. See [GCDServer](https://github.com/swisspol/GCDWebServer)
* create/edit articles
* publish article

Create a development friendly keyboard extension (arrows, ESC, CTRL keys...)


[^1]: Need to get back to this later, [Editorial](http://www.hardscrabble.net/2015/how-to-jekyll-from-ios/) seems to be a good solution ($6.99).