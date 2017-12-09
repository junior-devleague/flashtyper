# flashtyper

Spice up your flashcards!

![Final Product Example](https://github.com/junior-devleague/flashtyper/blob/master/example.gif)

## Objective

Use **JavaScript String Methods**, **Arrays**, and **Functions** to create a flashcard that lets you type in each character and generates a new flashcard when you finish typing.

## Prerequisites

To complete this project, students should have the following:
* Basic understanding of HTML structures and attributes.
* Basic understanding of Flexbox.
* Intermediate understanding of JavaScript (Arrays, For Loops, Creating Elements in JavaScript) and DOM

## Concepts

JS | Description
---|-------------
JS | **J** ava **S** script
somethingthatsaString.split('') | A String method that splits a ```String``` into an array of each character. The ```('')``` denotes the separator - try it out with different separators (instead of just the ```''```) on http://jsbin.com to see how it works!
String.fromCharCode(Unicode values) | A String method that returns a string created by using the specified sequence of Unicode values.
String.charCodeAt(index) | A String method that returns a number representing the UTF-16 code unit value of the character at the given index.

Note: Flexbox comes in very handy! It is helpful to remember the following common CSS Flexbox properties. Possible values for each CSS property are separated with a ``` | ```.
* ```display: flex;``` Use this to activate Flexbox! If you do not have this property, other flexbox properties will not work.
* ```justify-content: center | space-around | space-between;``` Control horizontal spacing.
* ```align-items: center | space-around | space-between;``` Control vertical spacing.
* ```flex-direction: column | row;``` Control the direction of items.


## Your Challenge

### Part I

To complete Part I, fulfill the following requirements:
1. Set up your project file structure through the command line.
2. Create the following:
* HTML file
* CSS file
* JS folder (include both data.js and app.js in this folder)
3. Link all of your files correctly. Make sure to link your JS files **in the right order**. *Hint: Look inside the data.js file. What do you see? There are variables that hold information we will be using later in our app.js file. So, if the computer executes each line of code from top to bottom, which should we link first - our data.js file or app.js file?*

### Part II HTML

To complete Part II, fulfill the following requirements:

1. Create a ```div``` with a ```class``` of "container".
2. **Inside** of this ```div```, create another ```div``` with an ```id``` of flashcard.

That's it!

### Part III CSS

To complete Part III, fulfill the following requirements:

1. Target the ```class``` of container.
* Set the ```width``` to calculate 100% of the view width - use calc(100vw). *This only works on newer browsers but we will use this for now.*
* Set the ```height``` to calculate 100% of the view height - use the same pattern as above!
* Activate flex box!
* Center the items horizontally using flex box.
* Center the items vertically using flex box.

2. Target the ```id``` of flashcard.
* Set the ```width``` to 40%.
* Set the ```height``` to auto. Setting the height to auto will make this element adjust the height the inner elements are.
* Activate flex box!
* Center the items horizontally using flex box.
* Center the items vertically using flex box.
* Allow the wrapping of items using flex box.
* Set the ```color``` to rgb(130,130,130). This is light gray.
* Set the ```box-shadow``` to ```0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23)```
* Set the ```padding``` to 20px.

3. Target the ```element``` p. *Note: It doesn't exist yet, we will be creating this in our JS!*
* Set the ```min-width``` to 10px. *This property sets the minimum width that the element should be. As you will see in the JS section, each character of the string will be a p element. Some characters will be spaces that contain nothing, but we want to at minimum see a visible space at those space characters.*
* Set the ```min-height``` to 10px.
* Set the ```margin-left``` to 4px.

4. Target the ```class``` of typed. *Note: This doesn't exist yet, we will be creating elements with this class in our JS!*
* Set the ```color``` to rgb(50,50,50). This is a lighter than black color.
* Set the ```font-size``` to 20px.
