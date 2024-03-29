---
layout: page
title: Some of My Coding Projects
permalink: /projects/
toc: true
---

## Flashy: A teacher-focused flash card app

Flashy was my solo project at [Prime Digital Academy](https://www.primeacademy.io/). It is a teacher-focused flash card app intended for language study. Teachers assign stacks of flash cards to students and are then able to track each student’s progress and participation rate. Teachers can upload CSV files of cards (with front, back, and optionally a batch number in the CSV file) instead of typing out all the cards in the app. (Although that is an option too, along with editing any cards that were already created). The app makes use of Unicode and supports right-to-left text, so languages like Hebrew will display correctly on the digital cards.

Students receive feedback on their progress and reminders when they need to review cards. Cards get sorted based on the student’s familiarity with each card; once cards are marked “known” they will be reviewed periodically, but at intervals increasing in length. (For instance, cards get reviewed after 1 day, then 3 days, then 7 days, etc.).

Teachers are expected to interact with this application on desktop, while students are mostly expected to interact with the application on mobile.

The app uses a [PostgreSQL](https://www.postgresql.org/) database to on the back end, [Express](https://expressjs.com/) / [Node.js](https://nodejs.org/en/) as a server, and [React](https://reactjs.org/), [Redux](https://redux.js.org/), and [Redux-Saga](https://redux-saga.js.org/) on the front end. Styling is provided by [Material-UI](https://mui.com/).

[![Flashy (Node Express / SQL / React / Redux / Material-UI)](/media/projects/student_learn.png)](https://shrouded-bayou-74485.herokuapp.com/)

[![Flashy (Node Express / SQL / React / Redux / Material-UI)](/media/projects/student_stats.png)](https://shrouded-bayou-74485.herokuapp.com/)

[![Flashy (Node Express / SQL / React / Redux / Material-UI)](/media/projects/teacher_class_progress.png)](https://shrouded-bayou-74485.herokuapp.com/)

[![Flashy (Node Express / SQL / React / Redux / Material-UI)](/media/projects/teacher_edit_class.png)](https://shrouded-bayou-74485.herokuapp.com/)

[![Flashy (Node Express / SQL / React / Redux / Material-UI)](/media/projects/teacher_edit_stack.png)](https://shrouded-bayou-74485.herokuapp.com/)
## Typer

As a Greek teacher, I thought it was important that my students could type in Greek Unicode. However, normally this is a hard-won skill: it takes considerable time (and pain) to learn to type in a different language. So, I created a game. (I also wanted to play around with [PixiJs](https://pixijs.com/), a JavaScript animation library.) The game is inspired by Letter Invaders, a game I played myself when learning to touch type that was included with the Typing Tutor software. Increasingly difficult words to type fall down from the of the screen, and if the player doesn't finish typing out the word before it hits the bottom, they lose a life.

I wanted to keep the entry barrier low, so I mapped the keys of a standard US keyboard to what the Greek Polytonic keyboard would normally be. This way, students didn't have to install the keyboard first (a challenge for some people who want to learn Koine Greek, since not all students have strong tech skills). The game uses a drop-in language and keymap system, so other languages and keymaps could be used if needed. 

This app was built in [TypeScript](https://www.typescriptlang.org/) and uses [PixiJs](https://pixijs.com/) for animation.

[![Typer (TypeScript / PixiJs)](/media/projects/typer.png)](https://bit.ly/greektyper)

## Giftodo

Giftodo is a todo app for those who remember gifs better than words. Users can add new tasks (similar to most todo apps) with a name, description, priority, and due date and time. The twist lies therein that the user can also then add a randomly generated gif based on the name of the task. Users can click the generate button until they find a gif that they are satisfied with.

The bottom navigation bar allows users to navigate between four different views: a list of tasks, a list of tasks with gifs assigned to them (and this list displays each gif), the add task view (which becomes the edit task view when a user wants to edit a task), and the dedicated overdue view where users can immediately see which tasks are overdue.

All task lists can be sorted with a speed dial, and the sort can by ordered by priority, name, due date, and date added. Clicking the sort button again reverses the sort order.

I built this app in about three days during a Christmas holiday break. (Yes, I took some time off for the holidays too! Always a good thing to get some rest). The main reason for building this app was to explore working with React Native. (At the moment, the app was only tested on iPhone devices.)

The app uses a [PostgreSQL](https://www.postgresql.org/) database to on the back end, [Express](https://expressjs.com/) / [Node.js](https://nodejs.org/en/) as a server, and [React Native](https://reactnative.dev/) with [React Native Elements](https://reactnativeelements.com/) as a styling library on the front end. The app was initiated and run through [Expo](https://expo.dev/) to allow testing on a simulator and on a native device. Gifs are generated by integration with the [Giphy API](https://developers.giphy.com/).

[![Giftodo (Node Express / SQL / React Native / React Native Elements)](/media/projects/task_list.png)](https://github.com/rhvdbergh/giftodo)
[![Giftodo (Node Express / SQL / React Native / React Native Elements)](/media/projects/gif_list_sort.png)](https://github.com/rhvdbergh/giftodo)
## Movies Saga

This app is a movie list app. Users can view the top ten movies in the main page, but also search for specific movies (with no limit) by typing in the search box in the top right of the app. The search is immediate; results appear as the user types.

The user can also add movies (by supplying a title, poster url, description, and genres). Users can later edit movies by clicking on the movie on the main page—which will display the selected movie's details—and then selecting edit on the next page.

An additional feature is that (after a mock login), an admin user can add or remove genres.

This app was built as one of the portfolio projects for [Prime Digital Academy](https://www.primeacademy.io/).

The app uses a [PostgreSQL](https://www.postgresql.org/) database to store the movies and genres, [Express](https://expressjs.com/) / [Node.js](https://nodejs.org/en/) as a server, and [React](https://reactjs.org/), [Redux](https://redux.js.org/), and [Redux-Saga](https://redux-saga.js.org/) on the front end. Styling is provided by [Material-UI](https://mui.com/).

[![Movies-Saga (Node Express / SQL / React / Redux / Material-UI)](/media/projects/main.png)](https://radiant-mountain-30397.herokuapp.com/)

## React Redux Feedback Loop

This app is a reflection / feedback form that allows users to rate their feeling, comprehension, and perception of support and enter any comments. There is also an admin page where admin users can view feedback provided by users, flag feedback (for further review), or delete specific feedback.

The app uses a [PostgreSQL](https://www.postgresql.org/) database to store the feedback, [Express](https://expressjs.com/) / [Node.js](https://nodejs.org/en/) as a server, and [React](https://reactjs.org/) and [Redux](https://redux.js.org/) on the front end. Styling is provided by [Material-UI](https://mui.com/).

The app was built as one of the portfolio projects for [Prime Digital Academy](https://www.primeacademy.io/).

I enjoyed building this project because it was my first full-fledged app built with redux. Because the feedback forms were all so similar, it also gave me practice in keeping my code DRY: I could reuse the same components (a question page and a header) to which I could pass down a few props to change the way they behave. I could also implement a multi-purpose modal to which I could pass down props; depending on which props were being passed down, the modal displays different options (with either one button or two buttons, conditionally rendered). I also passed down callback functions to the modal which makes the modal more flexible, as the parent component can decide on what actions should be completed on accepting or rejecting the modal.

[![React-Redux-Feedback-Loop (Node Express / SQL / React / Redux / Material-UI)](/media/projects/feedback_review.png)](https://evening-stream-08359.herokuapp.com/)

<!-- | Node.js | Express | PostgreSQL | SQL | React | Redux | Material-UI | MUI | axios | -->

## To-Do-Lister

This app is a (traditional) to-do-list app, built as one of the portfolio projects for [Prime Digital Academy](https://www.primeacademy.io/). Users can enter tasks (by pressing Enter or clicking on the "Add Task" button), mark tasks complete by clicking a button, and delete tasks by clicking on a delete button. Clicking on the delete button for completed tasks will simply delete the selected task, but clicking on an incomplete task will bring up a modal window asking the user to confirm the deletion.

The tasks persist on a PostgreSQL database. Completed tasks are timestamped and display the date completed to the user. Completed tasks are also presented with a different color, gray text, and line-through so the user can distinguish between completed and incomplete tasks. In addition, the user can sort the tasks according to alphabetical order (ascending or descending) and date completed (ascending or descending).

The app is styled using Bootstrap 5 and is responsive. The input field for entering a new task and its associated submit button persists at the top of the page (it's sticky) so that users can easily add more tasks.

[![To-do-lister (Node Express / SQL)](/media/projects/to-do-lister-screenshot.png)](https://agile-inlet-82271.herokuapp.com/)

<!-- | Node.js | Express | PostgreSQL | SQL | -->

## React Gallery

This app is a gallery of photos, another one of the portfolio projects for [Prime Digital Academy](https://www.primeacademy.io/). Photos are displayed in a grid pattern on cards, and the user can interact with the photos in several ways. Users can "love" photos (with each successive click, the "love" counter goes up - conditional rendering will show either "1 person loves" or "x people love" this). By clicking on the info button, the photo's description is displayed on the card rather than the card itself. clicking the expand button on the card will bring up a modal with a larger resolution image of the picture, accompanied by its description as a caption. Finally, clicking the delete icon will remove the reference to this image from the database.

The app allows users to upload photos either by supplying a URL or description, or performing a batch upload of photos from their computer through a modal interface. Batch uploading photos will transfer the photos from the user's computer to the app's server, after which the user will be prompted to supply a description for each newly uploaded image. Users may choose to leave descriptions blank.

The upload modal is an implementation of [uppy](https://uppy.io/), while other modals make use of [react-modal](https://www.npmjs.com/package/react-modal). Most of the styling was done using [Material-UI](https://mui.com/).

[![React Gallery (Node Express / React / Material-UI)](/media/projects/gallery_screenshot_with_info.png)](https://github.com/rhvdbergh/weekend-react-gallery.)

[![React Gallery (Node Express / React / Material-UI)](/media/projects/expand_photo.png)](https://github.com/rhvdbergh/weekend-react-gallery.)

<!-- | Node.js | Express | React | PostgreSQL | SQL | Material-UI | uppy | express-fileupload | axios | react-modal | modal |-->

## jQuery Server Calculator

This project is a server-side calculator, built as one of the portfolio projects for [Prime Digital Academy](https://www.primeacademy.io/), where I am doing a Full Stack Software Engineering immersion course. The calculator takes user input (numbers, a decimal point, and mathematical operations) and submits this information to the server when the user hits the equals button through a POST route.

Validation takes place on both the client-side and the server-side (to be safe). Validation includes whether the symbols submitted are acceptable mathematical entries, whether mathematical operators always have a number between them, and whether these operators are at the correct positions.

The calculation is performed on the server. Several operators can be sent in a formula, e.g., 1+2/3-5\*4.3 would be a valid input. The server ensures that the mathematical operations are performed in the correct order: multiplication and division first, followed by addition and subtraction. (The calculator does not take parentheses as inputs.) The server then stores this result, and adds the formula that was submitted to an array. This allows the front-end interface to retrieve both the result of the latest calculation, but also the history of previous formulae through a GET request. The user can clear this history on the server by hitting a "Clear History" button—which sends a DELETE request to the server. The user can also click on these previous formulae to rerun the calculation.

The calculator behaves similar to a physical calculator. There is one screen which displays the current formula and eventually the result. The user can perform further operations on this result by selecting a mathematical operator, or choose to perform a new calculation by hitting a number or the decimal point.

[![JQuery Server Calculator (Node Express / jQuery)](/media/projects/server-side-calculator.png)](https://protected-bastion-65313.herokuapp.com/)

<!-- | Node.js | Express | jQuery | -->

## SQLite Library Management System

A library management system project completed for the [Full Stack JavaScript Treehouse Techdegree](https://www.credential.net/324e3a8f-7283-4386-8d5b-187bc0488cb2). The project instructions were:

> You've been tasked with creating a library management system for a small library. The librarian has been using a simple sqlite database and has been entering data in manually. The librarian wants a more intuitive way to handle the library's books, patrons and loans.

> You'll be given static HTML designs, a set of requirements and the existing SQLite database. You'll be required to implement a dynamic website using Express, Pug, and the SQL ORM Sequelize.

<!-- | Node.js | Express | Pug | SQL | Sequelize ORM | -->

[![SQLite Library Manager (Node Express / Pug / SQL ORM Sequelize)](/media/projects/SQLite_library_manager.png)](https://github.com/rhvdbergh/SQLite-Library-Manager)

## NewsCloud

An app that creates Word cloud comparisons of recent news headlines and summaries vs Twitter. Word clouds are based on the frequency of words found in the same headline, summary, or tweet as a specific search term. Data goes back 7 days and is restricted to the latest 100 headlines + summaries and tweets. A news ticker at the bottom of the page shows the 20 most recent searches, as well as the number of times these terms were searched.

NewsCloud was my capstone project for the [Treehouse Full Stack JavaScript Techdegree](https://www.credential.net/324e3a8f-7283-4386-8d5b-187bc0488cb2).

<!-- | Node.js | Express | MongoDB | Mongoose |
| Bootstrap | jQuery | Rest API | | -->

[![NewsCloud: Word clouds of news headlines and summaries vs Twitter](/media/projects/NewsCloud.png)](https://bit.ly/newscld)

## Markdown Previewer

A markdown previewer built as a project for the freeCodeCamp [Front End Libraries certification](https://www.freecodecamp.org/certification/rhvdbergh/front-end-libraries).

<!-- | JavaScript | HTML | CSS | marked.js |-->

[![A markdown previewer.](/media/projects/markdown_previewer.png)](https://vanderbergh.com/fcc-fel-markdown/)

## Remove Numbers and Carriage Returns from Text

I needed to sanitize (ancient) Greek text by removing line numbers and carriage returns, but couldn't find a quick way to do it - so I created this online tool. Any text copied to the left box is stripped of numbers and carriage returns. The text on the right is immediately copied to the clipboard. Changes to the text on the right can be made on the fly (and the altered text is automatically copied to the clipboard.)

<!-- | JavaScript | HTML | CSS | -->

[![Remove Numbers and Carriage Returns from Text](/media/projects/remnum.png)](https://vanderbergh.com/remnum/)

## Egreek Converter

A student had to convert several pages of Greek from the legacy font "Egreek" to Unicode characters. I wrote [a little utility](https://github.com/rhvdbergh/Greek-Converter) in Java to help.

<!-- | Java | -->

## Perroquet's Deep Listening Service

I wanted to play with Google's speech-to-text API, so I created this chatbot. Google's API is experimental (or at least was at the time I built this bot), so Perroquet uses speech recognition only when on Google Chrome (Desktop).

[![Perroquet's Deep Listening Service: A chatbot that can also use speech recognition when on Google Chrome (Desktop)](/media/projects/perroquet.png)](https://rhvdbergh.github.io/perroquet/)

## Animal Sounds Drumset

This farm animal "drum kit" was built with React as a project for the freeCodeCamp [Front End Libraries certification](https://www.freecodecamp.org/certification/rhvdbergh/front-end-libraries).

<!-- | React | CSS | HTML | JavaScript | -->

[![Farm animal "drum kit" built with React.](/media/projects/animal_sounds_drumset.png)](https://vanderbergh.com/fcc-fel-drum/)

## Tic Tac Toe

A Tic Tac Toe game - either two player or single player. The single player uses a minimax algorithm and is, well, unbeatable. If you don't believe me, give it a try!

[![Tic Tac Toe: A Tic Tac Toe game - either two player or single player. The single player uses a minimax algorithm and is, well, unbeatable. If you don't believe me, give it a try!](/media/projects/Tic_Tac_Toe.png)](https://rhvdbergh.github.io/Tic-Tac-Toe-TTP4/)

## Retro-themed Calculator

I gave this calculator, another freeCodeCamp project, a seventies look.

<!-- | React | CSS | HTML | JavaScript | -->

[![A retro-themed calculator.](/media/projects/calculator.png)](https://vanderbergh.com/fcc-fel-calculator/)

## Animated Pomodoro Clock

This adjustable pomodoro clock was built with React as a freeCodeCamp project. It's animated using scalable vector graphics (SVG) ... and ends with a splat.

<!-- | React | SVG | CSS | HTML | JavaScript | -->

[![Animated Pomodoro Clock](/media/projects/pomodoro_clock.png)](https://vanderbergh.com/fcc-fel-pomodoro/)
