---
layout: post
title: CNAME fix for Persistent Custom Domain with Gatsby and GitHub Pages
date: '2019-05-08'
draft: false
slug: '/posts/custom-domain-with-gatsby-and-github-pages/'
categories: 'Tips & Tricks'
tags:
  - 'Gatsby'
  - 'GitHub Pages'
  - 'Tips'
  - 'CNAME'
excerpt: 'I am using GitHub Pages to host this blog, which was built with Gatsby. As you can probably see, I use a custom domain ([https://vanderbergh.com](https://vanderbergh.com)) which needs to be set in the GitHub Pages repository settings.'
---

I am using GitHub Pages to host this blog, which was built with Gatsby. As you can probably see, I use a custom domain ([https://vanderbergh.com](https://vanderbergh.com)) which needs to be set in the GitHub Pages repository's settings.

I'm using [`gh-pages`](https://www.npmjs.com/package/gh-pages) to manage the upload (and this works really well). However, every time I used my `npm run deploy` script (for me,that amounts to `gatsby build --prefix-paths && gh-pages -d public`), I had to manually enter the custom domain in the repo settings, or else I would end up with GitHub's 404 (page not found) message.

Luckily, this issue was easy to fix. The only thing that was missing was a CNAME file, which can be copied directly into the `static` folder. (Read more about Gatsby's `static` folder [in their docs](https://www.gatsbyjs.org/docs/static-folder/).) GitHub Pages will look for this CNAME file in the root directory and set any custom domains accordingly. The only content of the CNAME file is the domain name, which for me would be:

```
vanderbergh.com
```

This solved my problem, and now the upload works like a charm.

By the way, the CNAME file has no extension - it's only named 'CNAME'.
