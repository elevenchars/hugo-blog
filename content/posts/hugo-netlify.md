---
title: "Deploying a Hugo site with Netlify"
date: 2019-01-03T20:48:57-06:00
draft: false
toc: false
images:
tags: 
  - web
---

I figured it might be useful to post some quick notes on how I set this site up. When I was looking for tools to use, I wanted a low maintenance static site generator that did not require a lot of web design knowledge. I'm a big fan of how Hugo works so I decided to give it a shot with Netlify.

## Creating your first site

For this I pretty much followed the [Hugo quickstart](https://gohugo.io/getting-started/quick-start/) exactly. It's important to check if your theme has an example `config.toml` because often themes will have custom parameters in this. I decided to make my theme a submodule of my blog repo because I am (probably) the only one who is going to be maintaining this site so simple cloning is not a concern to me. I would look more into `git subtree` or simply cloning the theme repo if your site is going to be maintained by multiple people.

## Deploying to Netlify

This was honestly the easiest part of the process and something I was very impressed by. Once I had committed my site repo to Github it was just a few clicks to get it deployed on Netlify. Make sure that your `HUGO_VERSION` environment variable is set to something somewhat recent. If you are using a theme that requires [Hugo Extended](https://gohugo.io/news/0.43-relnotes/) (read: SASS/SCSS support) to build, make sure that the `resources/_gen/assets` directory is being tracked in your repo so that the Netlify build will skip the asset generation steps. This may be fixed in a newer version of Netlify. ([See here](https://github.com/netlify/build-image/issues/182))

Overall, I'm really impressed by how easy this was to set up. It has been mostly hands free on my part and I plan to use this setup for future static site projects.