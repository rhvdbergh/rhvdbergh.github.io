---
layout: post
title: Automatically Run JavaScript after Page Reload
date: '2019-05-10'
draft: false
slug: '/posts/Automatically-Run-JavaScript-After-Page-Reload'
categories: 'Solutions'
tags:
  - 'Chrome Extension'
  - 'Express'
  - 'location.reload()'
  - 'nodemailer'
excerpt: 'I recently needed to automatically run JavaScript on a page (owned by someone else) that I wanted to refresh after regular intervals. Why would I want to do this? Well, I needed to watch a calendar for a cancellation so I can make a booking, and wanted to automate this process.'
---

## The Problem

I recently needed to automatically run JavaScript on a page (owned by someone else) that I wanted to refresh after regular intervals. [TLDR - Jump to the solution, which included creating a very basic Chrome Extension.](#the-solution)

Why would I want to do this? Well, I needed to watch a calendar for a cancellation so I can make a booking, and wanted to automate this process - instead of me having to check every few minutes, I wanted to write a script that would automatically inform me as soon as a date became available.

![Checking online calendars is a more time-consuming task than keeping a paper schedule.](/media/calendar.jpg)
_Checking online calendars is a more time-consuming task than keeping a paper schedule._

Writing the script (and then using it in the Chrome DevTools console) turned out to be relatively easy - I traversed the DOM and checked for specific classes on specific elements in the calendar - but the page had to be refreshed manually to check whether a new date has become available. Every time I refreshed the page, the console script would be wiped.

My next thought was to use an `iframe`, and then refresh the `iframe` programmatically. This would have been a good solution, I believe, but the website had its `X-Frame-Options` HTTP header set to `sameorigin`. This meant that the page wouldn't load in an `iframe`, and it turns out that this is [an excellent security choice](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options) and (almost) impossible to overcome. Good for them, more challenging for me.

## The Solution

The solution turned out to be creating a very basic Chrome Extension. Luckily, the [official Chrome Extensions tutorial](https://developers.chrome.com/extensions/getstarted) and documentation are pretty accessible.

The first step is to create a directory in which the extension will live. In this directory, one has to create a `manifest.json` file. As the name suggests, this file declares things about the extension like permissions and what scripts the extension will run. For a full list, see the [Extension Manifest File Format page.](https://developer.chrome.com/extensions/manifest)

This was the `manifest.json` file that I created (with the name of the website removed):

```
{
  "name": "Reloader",
  "version": "1.0",
  "description": "Automatically Check Calendar Status Script",
  "content_scripts": [
    {
      "matches": ["https://example_website.com/*"],
      "run_at": "document_end",
      "js": ["reloader.js"]
    }
  ],
  "manifest_version": 2
}
```

The magic happens here because this manifest declares a "content script." `matches` is a required array that contains any websites that the script will run on. As you can see from the `*`, this doesn't have to be an exact match. `run_at` declares when the script will run. In my case, I wanted the script to run as soon as but not before the whole page was loaded. This would ensure that I had access to the complete DOM. Finally, `js` points to a file, `reloader.js`, that lives in the same directory as the manifest that contains the script that needs to be run.

Next, I had to install the extension. This turned out to be easy too: simply navigate to `chrome://extensions` in a Chrome tab, make sure "Developer Mode" is switched on (top right of the screen), and select "Load Unpacked", pointing to the manifest and script's folder.

I could now access any element in the DOM and add some logic to it. In my case, the calendar was a table, so I grabbed hold of all the `td` elements on the page and tested each for a specific class. That's the way this page was set up-available dates had a specific class, so I could figure out whether there was an opening on the calendar or not. I then added the following to the `reloader.js` script:

```javascript
setTimeout(() => {
  location.reload();
}, 120000);
```

Every two minutes (the `setTimeout()`), the page would refresh (the `location.reload()`), and the extension would load the script again, checking to see if there was an availability. _This worked even better than I expected, as it kept on running in the background, as long as it was open in a Chrome tab._

I then used [express-generator](https://www.npmjs.com/package/express-generator) to spin up a local server, and called

```javascript
fetch('http://localhost:3000/open', { mode: 'no-cors', method: 'post' })
```

from the `reloader.js` script when an availability occurs. (I had to use `mode: 'no-cors' because of the website's tight security. This will probably only work locally, but that was all I needed.) On the Express end, I used [nodemailer](https://www.npmjs.com/package/nodemailer) to send myself an email as soon as an availability was detected. And then I waited like a spider in its web.

![Then I waited like a spider in its web.](/media/spider.jpg)
_Then I waited like a spider in its web._

For what it's worth, I did get my appointment, although I had to wait two days for one to open.
