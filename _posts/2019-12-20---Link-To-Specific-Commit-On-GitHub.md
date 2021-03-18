---
layout: post
title: How to Link to a Specific Commit on GitHub
date: '2019-12-20'
draft: false
slug: '/posts/Link-To-Specific-Commit-On-GitHub.md'
categories: 'Tips & Tricks'
tags:
  - 'GitHub'
  - 'Git'
  - 'Commit'
excerpt: 'A quick post on how to link to a specific snapshot of code on GitHub.'
---

## Introduction

There are several reasons why you would want to link to a specific commit on GitHub. In active projects, code is always changing. You want to make sure that you're linking to the exact code that you want to link to (for instance, in a tutorial, in a blog post, or when working on a collaborative project and, for some obscure reason, you're working on the same branch).

## How to Link to the Files Involved in a Specific Commit

GitHub will by default show the latest status of the Master branch. For instance, [this is the latest status of the Master branch of my blog](https://github.com/rhvdbergh/gatsby-blog). When I'm done writing this blog post, that link will include a commit which will contain this blog post already written.

If you click on the "commits" link, however, you will be redirected to [https://github.com/rhvdbergh/gatsby-blog/commits/master](https://github.com/rhvdbergh/gatsby-blog/commits/master), where you will be able to see all of the commits that has been made in the current branch (i.e., master). (Tip: You can also switch out the branch, here, either by clicking on the "Branch" drop-down menu button, or by changing the word "master" in the URL to the branch of which you would like to see the commits).

You can now select a specific commit. (Hopefully you used descriptive commit messages!) If I click on my [commit on May 10, 2019](https://github.com/rhvdbergh/gatsby-blog/commit/da001e48b98b41779d9ab9fb4e28391094a92dab), I am taken to a commit that I made for a blog post on that day. You'll see that, instead of the branch name, the URL now includes the commit ID:

https://github.com/rhvdbergh/gatsby-blog/commit/da001e48b98b41779d9ab9fb4e28391094a92dab

## How to Link to a Snapshot of a Branch of a Specific Commit

Pointing to a specific file or files might be exactly what you want to achieve, but perhaps you want to point to the state of the whole branch when this commit was made. You can do this by clicking on "Browse files" on that specific commit. Alternatively, you can simply change the "commit" part of the URL to "tree":

https://github.com/rhvdbergh/gatsby-blog/tree/da001e48b98b41779d9ab9fb4e28391094a92dab

Now you can simply copy that URL; it will always point to that specific snapshot of the code on GitHub. Don't forget to return to the master branch if you want to look at the latest state of the code!
