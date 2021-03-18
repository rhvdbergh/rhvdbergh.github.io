---
layout: post
title: Resize Multiple Images Quickly with the Mac Terminal
date: '2019-05-07'
draft: false
slug: '/posts/resize-multiple-images-quickly-with-the-mac-terminal/'
categories: 'Tips & Tricks'
tags:
  - 'Sips'
  - 'Image'
  - 'Tips & Tricks'
  - 'Command line'
excerpt: 'I recently had to resize several photos for my project page. Normally, I would use the excellent free image manipulation program GIMP. But I wondered whether there was an easier way to apply the same resizing to images without having to open GIMP.'
---

## Introducing **sips**

I recently had to resize several photos for this blog's project page. Normally, I would use the excellent free image manipulation program [GIMP](https://www.gimp.org/). But I wondered whether there was an easier way to apply the same resizing to images without having to open GIMP. And indeed, there is - using **sips** in the macOS Terminal (or anywhere that one has access to the command line in macOS).

## Example

Let's say there's a bunch of `.png`s that you would want to resize. (**Sips** can also handle `.jpg` and a lot of other file formats, but I was working with `.png` for the blog.) Simply open up your terminal and navigate to the folder containing the images you want to resize. Then type in the command

```
sips -Z 640 *.png
```

and hit Return. This should do it; all your images will be resized. The `-Z` in this instance keeps the aspect ratio intact. (See my note below, though). `640` specifies the new height, and the `*.png` specifies that this operation should be done to all the `.png` files in this folder.

- Note: Actually,the `-Z` ensures that the maximum size doesn't exceed the specified number of pixels, in this case `640`; this will apply to the height or width, whichever is larger. The smaller side will be adjusted to keep the aspect ratio. So a picture in portrait orientation will not exceed 640 pixels in its height, and a landscape will not exceed 640 in its width.

## Other uses

**Sips** stands for _scriptable image processing system_, and has many more uses, including rotating or flipping images and converting images from one format to another. It's super fast and handy. I stumbled onto it by reading [this post by Adam Dachis](https://lifehacker.com/batch-resize-images-quickly-in-the-os-x-terminal-5962420), but you can also consult the [**sips** manual here](https://ss64.com/osx/sips.html) or by using the Terminal command

```
man sips
```
