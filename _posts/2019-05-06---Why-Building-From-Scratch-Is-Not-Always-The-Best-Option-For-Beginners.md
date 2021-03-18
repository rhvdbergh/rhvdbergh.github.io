---
layout: post
title: Why Building from Scratch Isn't Always the Best Option for Beginners
date: '2019-05-06'
draft: false
slug: '/posts/Why-Building-From-Scratch-Is-Not-Always-The-Best-Option-For-Beginners.md'
categories: 'Learning'
tags:
  - 'Beginner'
  - 'Code Review'
excerpt: 'Building something from scratch is a great learning opportunity. When I put together this blog, I could have done just that. And I could have opted to use a tutorial to guide me in this process.'
---
UPDATE: In March 2021, I switched to using Jekyll as a static site generator for this blog. I'm using a slightly modified version of the [Hamilton theme by Shanghzi Huang](https://github.com/ngzhio/jekyll-theme-hamilton). Most of what I say below still applies. 

Building something from scratch is a great learning opportunity.

When I put together this blog, I could have done just that. And I could have opted to use a tutorial to guide me in this process. There are brilliant tutorials out there, like [this one by Taylor Bell on egghead.io](https://egghead.io/courses/build-a-blog-with-react-and-markdown-using-gatsby).

Instead, I opted for a starter, which essentially provides code for a working blog. I considered, as a sensible option, the [Gatsby Starter Blog](https://www.gatsbyjs.org/starters/gatsbyjs/gatsby-starter-blog/) by Kyle Mathews (the founder of Gatsby). But I liked the somewhat added complexity and the aesthetics of [Alexander Shelepenok's Lumen starter](https://www.gatsbyjs.org/starters/alxshelepenok/gatsby-starter-lumen/).

## Is using (Gatsby) starter code cheating?

This sounds like I'm cheating, right? I won't lie, I probably did save some time. But I don't think I missed out an a learning opportunity.

Let me explain. If you are working on a team of developers it would be very unlikely that your day to day coding would be starting from scratch. Rather, you would have to read other developers' code _all of the time_. This could have been code that was authored by some on your team or even a developer that has already left the company. Things would look similar if you started working as a lone developer at a small company. You would have had to be able to make sense of complex, already _functioning_ systems so that you could make the required changes or additions without breaking anything.

## Some benefits of code review

Developers _constantly_ do code review. In opting for a slightly more complex starter, you might actually be getting some practice in code review, a useful - even required - skill.

![Code Review is a useful skill. Photo by Markus Spiske on Unsplash.](/media/markus-spiske-109588-unsplash.jpg)
_Code Review is a useful skill. Photo by Markus Spiske on Unsplash._

This doesn't mean that you have to understand _everything_ that the starter code does. But in order to change the code, you would have to understand at least some of it. And the bonus, of course, is that you would also get exposed to actual (hopefully best) practices. For instance, I don't know exactly how every bit of the Lumen code functions. But I don't think that's necessary, either. I had to figure out enough to get this blog up and running, and now I have a good idea how everything fits together in general and how I could possibly change it if I needed to.

## Conclusion

I don't think one should succumb to overthinking the question about starting from scratch or learning from tweaking someone else's code. There are benefits to both approaches, but only if you _actually build something_.
