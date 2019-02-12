# 30 Days of JavaScript

## Description
This repository is to document my thoughts and what I learn taking Wes Bos' [30 Days of JavaScript](https://javascript30.com/) challenge. 

## Installation and Usage
Each day of the challenge is in it's own folder. You can download this repository from my github [here](https://github.com/rlfuller/30-days-javascript) and download or clone to your computer. Each solution is html, css and javascript files. To run any given exercise, simply launch the html file in a browser. 


* Day 1 - JavaScript Drum Kit
The JS Drumkit consisted of .wav files that would play when a user typed one of several keys associated with the .wav files. The starter files included CSS styling that could be added to an element to highlight the key that was pressed. These stylings used a `transition` that when applied, changed the border color and box shadow of the div that represented the keypress.  

My solution involved adding an `eventListener` for `keydown` to apply the class associated with the CSS and adding a second `eventListener` for the `keyup` to remove the class. What I learned from Wes Bos' solution was about the `transitionend` event. His solution was to use an `eventListener` listening for the `transtioinend` instead of the `keyup` to remove the styling. I think is a good solution because althouugh the transition was short at .07 seconds, in my testing, if you changed the transition to be longer than how long it takes to perform a `keyup`, the transition would not run because the `keyup` had already completed before the transition could even start.