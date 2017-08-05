---
layout: post
title: "How to use Jekyll Clean Dark?"
date: 2017-08-04
tags: jekyll
description: Things I didn't figure out in the beginning.
comments: true
share: true
---

## What is Jekyll Clean Dark?
There’s the [repository](https://github.com/streetturtle/jekyll-clean-dark) and [demo site](http://pavelmakhov.com/jekyll-clean-dark). I think this theme is pretty clean and simple not that too fancy. It’s a good thing to help your reader only focus on the content.

## Tag?

[Author already explained how to use tag with this theme](http://pavelmakhov.com/jekyll-clean-dark/2016/08/analytics-tags-comments). But there are some steps I think not clear for me. When you write down your post in markdown, you need to add tags in the header of post. After that, you need to generate HTML for those tags. You need to execute the command - `jekyll serve` in your root directory. It will generate those HTML in `{project}/_side/tag`, then you could simply copy all of HTMLs in this folder to `{project}/tag`.

## Disqus

Don't forget you need account in Disqus. And you need to setup your sites in Disqus. When you setup through [This page](https://disqus.com/admin/create/) it should let Disqus recognize your website. Or you would get message - ***We were unable to load Disqus*** from Disqus' JavaScript.
