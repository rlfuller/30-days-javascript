# 30 Days of JavaScript

## Description
This repository is to document my thoughts and what I learn taking Wes Bos' [30 Days of JavaScript](https://javascript30.com/) challenge. 

## Installation and Usage
Each day of the challenge is in it's own folder. You can download this repository from my github [here](https://github.com/rlfuller/30-days-javascript) and download or clone to your computer. Each solution is html, css and javascript files. To run any given exercise, simply launch the html file in a browser. 


### Day 1 - JavaScript Drum Kit - February 11
The JS Drumkit consisted of .wav files that would play when a user pressed one of several keys associated with the .wav files. The starter files included CSS that could be added to an element to highlight the key that was pressed. These stylings used a `transition` that when applied, changed the border color and box shadow of the div that represented the keypress.  

My solution involved adding an `eventListener` for `keydown` to apply the class associated with the CSS and adding a second `eventListener` for the `keyup` to remove the class. What I learned from Wes Bos' solution was about the `transitionend` event. His solution was to use an `eventListener` listening for the `transtioinend` instead of the `keyup` to remove the styling. I think this is a good solution because althouugh the transition was short at .07 seconds, in my testing, if you changed the transition to be longer than how long it takes to perform a `keyup`, the transition would not run because the `keyup` had already completed before the transition could even start.

### Day 2 - JavaScript / CSS Clock - February 16
This lesson creates an analog clock using CSS and then animates the movement of the clock hands using JavaScript in conjunction with CSS transforms and transitions.  The hardest thing about this exercise was understanding the math involved that was needed to place the clock hands into the proper position. I"m a little rusty on my geometry. Or make that a lot rusty. The JS works by getting the current date using `new Date()` and then getting the hours, minutes and seconds which are then transformed into their equivalent values in degrees. Using a `transform: rotate()`, the clock hands are then moved. All of this is done in a function called by `setInterval()` so it runs every second. 

I spent most of my time on this learning about the difference between `transition` and `transform`. I deviated from solution at the end to add some different styling to the hour hand as the solution had the hour hand the same length as the minute and second hand. All the clock hands were set at `width: 50%`. I set the width to be 35%, then set the `position:relative` with a left of 15% to account for the difference. I also changed the colors of the clock hands and the height of the second hand to differentiate that from the minute hand. 

### Day 3 - CSS Variables - February 17
This lesson involved using CSS variables that are tied to thiree inputs on a website and then updating those based on the user input via JavaScript. 

I've never played around with CSS Variables before. I thought that this was pretty cool. Wes Bos didn't realy talk about scope, but during my research on this topic, I learned that you can declare variables to be global by putting on the `:root` pseudoelement, or local by just declaring them on the specific element that you want. Local CSS variables are available to just that element and it's children.  As CSS elements have access to the DOM unlike LESS or SASS, you can update them with JS by calling `setProperty()` on the element and passing in the CSS variable and it's new value. 

### Day 4 - Array Cardio - February 18
Array cardio was all about getting more experience with map, reduce, filter and sort.  My biggest takeaway from this is to be cognizant of the state of the items in your arrays. Most of the arrays we are working with in these exercises are arrays of objects. There was one exercise, #2, where we needed to use map to take an array of objects and return the first and last names from amoungst other properties. My first attempt before watching the solution was to use `delete` on the properties that we didn't need. I then couldn't figure out why subsequent exercises starting from the same array were only showing 2 out of 4 properties in the objects even though I had returned my array to a new variable in #2. Even though map returns a new array, that new array was an array of objects that were still pointing back to the original object, that I had just deleted. I was able to rework this solution to just create a new array only using those properties we needed instead of deleting the properties we didn't want. 

### Day 5 - Array Cardio - February 20
This was so much fun. This lesson was using flex with some transforms to make some really cool flex panels that opened when you clicked them. I enjoyed it so much that I created another version using picktures of my dogs. My version can be run by cloning or downloading the project and then opening fun.html in your browser.  I had used flex before, you can see it on my website [here](http://www.rlfuller.com), but this was the first time that I had used flex to create columns versus rows. 

### Day 6 - Type Ahead - February 21
Today was about taking connectng to an api to grab some data and displaying it on a website. Once I understood what we were going to do, I created a function to grab the data using a `new XMLHttpRequest()`, which worked. But once I watched the solution, I saw that we actually used `fetch()` which was definitely a better way to go, as my xhr function was around 12 lines of code while the fetch was just 3 lines. This was a good introduction to fetch and promises. 

### Day 7 - Array Cardio 2 - February 22
Revisiting array functions, this time with `arr.some()`, `arr.every()`, and `arr.find()`. However, the coolest thing that I learned that I didn't know was this ... next time you need to print an array to the console to verify the data while debugging something, instead of `console.log(arr)`, use `console.table(arr)`.

### Day 8 - Fun with Canvas - February 24
I could play with this lesson for hours. It was a brief introduction to canvas, but I think the most relevant thing was understanding mouse events. We worked with the `event` object and used `mouseup`, `mousedown`, `mouseout` and `mousemove` to draw lines on a canvas when you drag the mouse. 

### Day 9 - Dev tools - February 26
Some different methods for the console to make life a little easier. 

### Day 10 - Holding Shift key to select multiple items - February 28
For this exercise, we were given a list of checkboxes and then asked to come up with a solution where if the user clicked and held down the shift key, then clicked again, all the checkboxes inbetween would be checked. I came up with a solution before watching the official answer and of course, my solution was a lot longer. My solution was to use two event listeners, one for `mousedown` and one for `mouseup` and check to see if the shift key was pressed. Then get the index of the two elements that were clicked. On the `nouseup`, loop through array of checkboxes only for those indicies and check all items. 

What I learned from watching Wes Bos\` solution is that you don't need two event listeners for the shift key, as the event has a built in boolean property `event.shiftKey` which indicates if the shift key was pressed or not while clicking. So you can do this exercise with one eventlistner which is listening for the click, then check the shiftKey property for true/false.

### Day 11 - Styling a video player - February 28
This lesson invovled using JS to style the controls of a video player. It was a nice introduction to some of the properites and methods of the video object, such as `video.play()`, `video.duration`, `video.currentTime`, `video.volume`, `video.playbackRate`. The most helpful one to know is `video.paused` because there is not a method to stop play, there is only a method to start the video playing, `video.play()`, so if you want to stop it, you can set `video.paused = true`. 

### Day 12 - Key Sequence Detection - March 4
I learned an easy method for detecting a sequence of keys, which is to store them in an array and then check for the sequence. But the most interesting things I learned were about the `konami` code `up`, `up`, `down`, `down`, `left`, `right`, `left`, `right`, `b`, `a`.  I did some research to see what websites are still using it. Try it on [buzzfeed](https://www.buzzfeed.com/), [digg.com](http://digg.com) or [British Vogue](https://www.vogue.co.uk).

### Day 13 - Adding Images on Scroll - March 6
This lesson shows how to give the effect of flying images in from off the page when you scroll up and down. You start with images being hidden and translated slightly off screen. As you scroll down a page to where the image image is, a class is appled with sets the `opacity: 1` and `transform: translateX(0%) scale(1);`. I"m personally not sure if this is a great effect because the end result is that as you are viewing the website and scrolling down, you see blank squares where the images should be. It's only as you scroll the page to the point where 1/2 of the image would be visible based on some math that looks at the image `offsetTop` property relative to the the current position in the scroll that the class is applied.  

The most important thing I took for this lesson though is an understanding of debouncing and when you would use it. We used a debounce function found online that would help eliminate crazy lag effects from scroll as our windown event was listening to scroll and would run approximately 50 times with one flick of scroll down versus 7 after wrapping it in a debounce function. 

### Day 14 - Copy By Reference vs Value - March 9
This is something that I have learned in C#, but the most helpful thing I learned was all the ways to copy arrays and objects instead of just assigning a reference. 

For arrays:
- `arr2 = arr.slice()`
- `arr3 = [].concat(arr)`
- `arr4 = [...arr]`
- `arr5 = Array.from(arr)`

For objects:
- `newObject2 = Object.assign({}, oldObject, {properties})`
- `newObject3 = {...oldObject}`

However, for objects, these only create a shallow copy, 1 level deep. If any of the properties are also objects, those will be copied by reference to the new object.

### Day 15 - localStorage and Event Delegation - March 10
Today is daylight savings time .... spring forward. Today is also the day I learned about localStorage and Event Delegation. This exercise added elements to a list when entered through a form, then the list was persisted in local storage. The given solution was to re-populate the entire list each time an element was entered. I kept thinking that instead, we should do a solution to just add each individual item to the array as each element was entered. I think though if we did that, we wouldn't need to put the event listener on the ul and use event delegation, when we could have the event listener on each ul item as it's added to the array after form submit. 

### Day 16 - Making shadows move with the cursor - March 14
We created a cool effect of moving a shadow around an element as the mouse moves. The biggest learning area is understanding some event properties. When you are dealing with events, you can use `offsetX` and `offsetY` to get the position of where the cursor is. 

### Day 17 - Sorting an array of strings, but ignoring leading articles - March 16
This lesson was about sorting an array of strings that had leading articles such as The, An, A and using regex to ignore the leading articles during the elements of the array. I definitely need to study more about regex, but the most interesting thing was about the evolution of functions. 

From starting with a sort function like this:
``` const sortedBands = bands.sort(function(a, b) {
    if(strip(a) > strip(b)) {
        return 1;
    } else {
    return -1;
    }
    });
```

To rewriting it to use ternary and es6 fat arrow:
```
const sortedBands = bands.sort((a, b) => {
    return strip(a) > strip(b) ? 1 : -1;
});
```

To understanding that if the only thing your function does is return, then you can use the implicit return, so removing the { } brackets and the `return` keyword:
`const sortedBands = bands.sort((a, b) => strip(a) > strip(b) ? 1 : -1);`
