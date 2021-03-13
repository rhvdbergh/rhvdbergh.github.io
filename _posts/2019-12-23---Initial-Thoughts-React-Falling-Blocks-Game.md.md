---
layout: post
title: Initial Thoughts on Building a Falling Blocks Game with React
date: '2019-12-24'
draft: false
slug: '/posts/Initial-Thoughts-React-Falling-Blocks-Game.md'
categories: 'Falling Blocks Game'
tags:
  - 'React'
  - 'Roadmap'
  - 'Planning'
  - 'Design'
description: 'Some initial thoughts on building a falling blocks game (you know, that game where pieces consisting of four blocks fall down the screen and stack on each other - until you fill up a whole horizontal line). This post is the first in a series.'
---

## Introduction

A certain falling blocks game (which shall remain unnamed) is really just a matrix (or two-dimensional array). You know, that game where pieces consisting of four blocks fall down the screen and stack on each other - until you fill up a whole horizontal line. This is probably a good game to build in React, as it's built out of only a few components with some changes in state.

![This is *not* the falling blocks game I'm talking about, although the colors are very similar. Photo by La-Rel Easter on Unsplash.](/media/blocks.jpg)
_This is not the falling blocks game I'm talking about, although the colors are very similar. Photo by La-Rel Easter on Unsplash._

In this post, I'll lay out a sort of roadmap for how I will go about building the game. You're welcome to follow along as the game develops. Things may change as we progress; these are just some initial thoughts to form an overview on what’s needed. I’ll add some more detailed notes as we build the game.

## Mobile First

We’ll want to make sure that the game is playable on a mobile device of any shape and size. The screen size will have to dynamically adjust and components will have to be arranged differently on the screen for mobile and desktop. We’ll want buttons to appear only when the game is played on a mobile device (desktop users will use the arrow keys to move pieces around).

## Components

We’ll need the following main components:

#### Blocks (and pieces)

Well, it stands to reason that we’ll need blocks. At the very least, a block will consist of a single `div` with a class of "empty" or a specific color.

Blocks are different from pieces. Each piece consists of four blocks. (We don’t necessarily need a piece component. We’ll see how that takes shape as the code develops.)

Different pieces will be made up of different colors, so we'll have to indicate the color of each block. We'll want to use a matrix for the playing field (see below), so we can simply use the color as an indication that a block exists on specific coordinates on the playing field. That way, we can use the color to style the `div` while also keeping track of the position on the grid (see below).

Note: there are seven different ways to arrange four blocks to form different shapes of pieces, so we will need seven colors.

#### Playing field

We’ll need a 10 wide x 20 high grid for the playing field. Positions in the playing field, or the `div`s that make up these positions, will either be "empty” or filled with color.

#### Show next block

To show the user the next piece that will drop into the playing field, we’ll need a 4 wide x 2 wide grid. (Any piece formed by four blocks will fit in these dimensions). As with the playing field, this component will consist of smaller `div`s that are either "empty" or will be filled with color.

#### Score board

This will be a board displaying two things (which will be two smaller components): the score and the current level.

#### Buttons

For the mobile game, there will be at least three buttons: rotate left, rotate right, and slow drop. (There will also be a fast drop where the piece falls really quickly, but we'll rather use a gesture than a button to accomplish this.)

## Things to keep track of - state

The following are some things we need to keep track of in the game; we can assume that these will need variables. It’s probably best to keep most of these in an upper level so it can be passed down to all the components that need it.

#### Score

We'll want to keep track of the `currentScore`. The score will determine when the player reaches the next level.￼

#### Level

We'll need a level counter, `currentLevel`, which will increase when the player reaches a certain score. The level will determine the speed at which the pieces drop.

#### Positions of blocks

The positions of blocks will be stored in a `grid`, which will be a 2D array (`[10][20]`). Each position in the array will contain either an indication of being "empty" or a color.

#### Position of current piece

We can think of the current piece as an object, `currentPiece`, consisting of four coordinates on the `grid`. Coordinates will consist of x and y variables.

#### Type of next piece

We want to show users the `nextPiece` that will come after the `currentPiece`, so we'll need a randomly generated object that can be displayed in the show next piece component.

![Nope, not this block game either. But note the colors! Photo by phil sheldon ABIPP on Unsplash.](/media/blocks2.jpg)
_Nope, not this block game either. But note the colors! Photo by phil sheldon ABIPP on Unsplash._

## Logic

I'll probably think more about the game logic as we continue, but here are the basics in a sort of pre-pseudocode.

There will have to be a `counter` to count the time between pieces moving downwards. The counter's `speed` will be determined using the `currentLevel`.

After the `counter`'s time runs out (or the user makes the piece drop), we'll have to calculate whether there are any blocks on the `grid` that are directly below the y coordinates of the `currentPiece` (but only those coordinates that are facing the bottom of the screen). At this point, the counter resets.

If there are active blocks that will stop `currentPiece` moving downwards, this means that `currentPiece` will become stationery and a new piece will start dropping. Before a new piece starts falling, however, we'll first check whether this new situation on the `grid` means that any horizontal lines are now all active (in which case those lines should disappear and all active blocks on the `grid` should move down, a score should be calculated and added to the `currentScore`, and it should be checked whether the `currentScore` means that the `currentLevel` should be increased).

We should next assign `currentPiece` new values on the `grid` according to the values in `nextPiece`. We should then check to see if there is actually space for the new piece to start falling; if not, the game is over. Otherwise, we have to update `grid` to color in blocks according to the new coordinates in `currentPiece`. We then have to generate a random `nextPiece`.

## Effects and styling

I think the styling should be pretty basic. The blocks that make up pieces should be in different colors. The background should not be too distracting. The only "effect" that I'm planning at this stage is that , Whenever the score and level counters change, there will be an effect where the numbers quickly grow and shrink back to their original size.

This seems to me to be the basic gist of it. Stay tuned if you want to see how the game develops step by step.
