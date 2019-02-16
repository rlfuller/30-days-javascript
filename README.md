# 30 Days of JavaScript

## Description
This repository is to document my thoughts and what I learn taking Wes Bos' [30 Days of JavaScript](https://javascript30.com/) challenge. 

## Installation and Usage
Each day of the challenge is in it's own folder. You can download this repository from my github [here](https://github.com/rlfuller/30-days-javascript) and download or clone to your computer. Each solution is html, css and javascript files. To run any given exercise, simply launch the html file in a browser. 


### Day 1 - JavaScript Drum Kit - February 11
The JS Drumkit consisted of .wav files that would play when a user pressed one of several keys associated with the .wav files. The starter files included CSS that could be added to an element to highlight the key that was pressed. These stylings used a `transition` that when applied, changed the border color and box shadow of the div that represented the keypress.  

My solution involved adding an `eventListener` for `keydown` to apply the class associated with the CSS and adding a second `eventListener` for the `keyup` to remove the class. What I learned from Wes Bos' solution was about the `transitionend` event. His solution was to use an `eventListener` listening for the `transtioinend` instead of the `keyup` to remove the styling. I think this is a good solution because althouugh the transition was short at .07 seconds, in my testing, if you changed the transition to be longer than how long it takes to perform a `keyup`, the transition would not run because the `keyup` had already completed before the transition could even start.

### Day 2 - JavaScript / CSS Clock - February 16
This lesson creates an analog clock using CSS and then animates the movement of the clock hands using JavaScript in conjunction with CSS transforms and transitions.  The hardest thing about this exercise was understanding the math involved that was needed to place the clock hands into the proper position. I"ve a little rusty on my geometry.  The JS works by getting the current date using `new Date()` and then getting the hours, minutes and seconds which are then transformed into their equivalent values in degrees. Using a `transform: rotate()`, the clock hands are then moved. All of this is done in a function called by `setInterval()` so it runs every second. 

I spent most of my time on this learning about the difference between `transition` and `transform`. I deviated from solution at the end to add some different styling to the hour hand as the solution had the hour hand the same length as the minute and second hand. All the clock hands were set at `width: 50%`. I set the width to be 35%, then set the `position:relative` with a left of 15% to account for the difference. I also changed the colors of the clock hands and the height of the second hand to differentiate that from the minute hand. 