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

After a few tryouts, I ended up using the `jekyll-picture-tag` [plugin](https://github.com/robwierzbowski/jekyll-picture-tag) in order to have different image sizes depending on the resolution of the device (responsive design).

It worked well locally but Github was still failing, because it does not support all plugins[^2]. The only solution then was to use Travis to build and publish the site ; quite straight forward with the `rake-jekyll` [gem](https://github.com/jirutka/rake-jekyll).

## Thoughts

Create a mobile app that would:

* retrieve website content from github
* build and serve the website locally. See [GCDServer](https://github.com/swisspol/GCDWebServer)
* create/edit articles
* publish article

Create a development friendly keyboard extension (arrows, ESC, CTRL keys...)

## Next steps

* Post to Twitter the article link when published - should be easy with travis now.
* Add comments system with Github issues

[^1]: Need to get back to this later, [Editorial](http://www.hardscrabble.net/2015/how-to-jekyll-from-ios/) seems to be a good solution ($6.99).

[^2]: [GitHub Pages currently supports **several** Jekyll plugins](https://help.github.com/articles/using-jekyll-plugins-with-github-pages/)
