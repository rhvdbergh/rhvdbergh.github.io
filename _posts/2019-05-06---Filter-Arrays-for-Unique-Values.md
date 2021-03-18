---
layout: post
title: Filter Arrays for Unique Values
# toc: true
date: '2019-11-11'
draft: false
slug: '/posts/Filter-Arrays-for-Unique-Values.md'
categories: 'Tips & Tricks'
tags:
  - 'Arrays'
  - 'Set'
  - 'Duplicates'
  - 'Unique Values'
  - '.includes()'
description: 'Ever needed to remove all the duplicates from an `Array` in JavaScript? Well, there is a hard way, an easy way, and an elegant way.'
---

## The Problem

Ever needed to remove all the duplicates from an `Array` in JavaScript, or in other words, had to filter an array for all its unique values? Well, there's a hard way, an easy way, and an elegant way. I'm going to talk about the hard way first, but feel free to [skip to the easy way](#the-easy-way) or [the elegant way](#the-elegant-way) if you want.

![Filtering things can be quite rewarding. Photo by Thomas Martinsen on Unsplash.](/media/thomas-martinsen-_FilM6g6DEQ-unsplash.jpg)
_Filtering things can be quite rewarding. Photo by Thomas Martinsen on Unsplash._

## The Hard Way

The hard way of doing this would be to set up two loops. While stepping through the first `Array` - let's call that `firstArray` with the first loop, you'd have to compare each entry in the array to another `Array` - let's call this one `uniqueValues`. You'll have to set `uniqueValues` to the first value in `firstArray`, so there's something to compare. And then you'll have to iterate over the second loop to check and add the value if it's not there yet. Depending on how you set up the loops, there could be an additional problem: the loop will keep going, the computer will keep checking and keep on adding any mismatches to `uniqueValues`. You might have to use a boolean, let's say, `valueMatched`, to keep track of whether you actually already found that value in `uniqueValues`.

There's more than one way of doing this, but here's an example:

```javascript
// assuming you have a firstArray and you've declared an empty uniqueValues

uniqueValues.push(firstArray[0]);

firstArray.forEach(value => {
  // set up a boolean to test whether there has
  // been a match already

  let valueMatched = false;

  // iterate over the second array
  uniqueValues.forEach(uniqueValue => {
    if (uniqueValue === value ) {
      valueMatched = true;
    }
  })

  if (!valueMatched) { // this value is unique,
    // so add it to uniqueValues
    uniqueValues.push(value)
  }
})
```

By the way, that `forEach` used on `uniqueValues` will keep getting longer as you push more unique values into the array.

## The Easy Way

The easy way, since 2016, would be to let `.includes()` do the hard work for you, essentially taking the place of that second loop. In this case, too, you wouldn't have to set an initial value for `uniqueValues`, since includes() will simply return `false` for an empty array.

```javascript
// assuming you have a firstArray and you've declared an empty uniqueArray

firstArray.forEach(value => {
  if (!uniqueValues.includes(value)) {
    uniqueValues.push(value)
  }
})
```

## The Elegant Way

The elegant way would be to convert the `Array` to a `Set` (and then switching it back to an array with a [spread operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)):

```javascript
const newSet = new Set(arr);
const newArr = [...newSet];
```

`Set`s can only hold unique values, so the hard work is being done for you. Magic!

## Thanks

I learned about this use of `Set`s while doing a [Frontend Masters](https://frontendmasters.com/) course on interviewing taught by [Jem Young](https://twitter.com/JemYoung). One of the benefits of living in Minneapolis is that I can attend some of the Frontend Masters courses in person - for free! They're a great company with lots of great content - you should check them out.
