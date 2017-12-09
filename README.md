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
String.split('') | A String method that splits a ```String``` into an array of each character. The ```('')``` denotes the separator - try it out with different separators (instead of just the ```''```) on http://jsbin.com to see how it works! *Substitute the word String for an actual String e.g. "Hello"*
String.fromCharCode(Unicode values) | A String method that returns a string created by using the specified sequence of Unicode values. *Use the actual word String.*
String.charCodeAt(index) | A String method that returns a number representing the UTF-16 code unit value of the character at the given index. *Use the actual word String.*

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

### Part IV JS

To complete Part III, fulfill the following requirements:

1. Create a function, ```window.onload``` that will make sure our JS runs only when all of the content of our window loads first.

```JavaScript
window.onload = function() {
  //Put all of your code goes in here
}
```
2. Create a ```variable``` called flashcard that will store your element with an id of flashcard. *Hint: Use document.getElementById('putYourIdHere');*

3. Create a ```variable``` called currentCard. Do not store anything in here yet. *This will store the name of a random card object.*

4. Create a ```variable``` called charArray. Do not store anything in here yet. *This will store the array of characters that we get when we split the description of the card object.*

5. Create a ```variable``` called counter. Do not store anything in here yet. *The counter will be used to track which letter the user is currently on while typing. Each press of the keyboard will increment this counter. If the counter is equal to the length of the character array, the user has reached the end of the card and can move on to the next one.*

6. Create a ```variable``` called currentLength. Do not store anything in here yet.

7. Create a ```function``` called generateCard. In this function, do the following:
* Create a ```variable``` called randomNumber. In this variable store a random integer from 0 to the length of the array called terms found in your data.js file.
* Use your randomNumber and assign a random note object from the terms array (e.g., note1, note3, note13..etc.) to the currentCard variable. *Hint: How do you access an element from an array?*
* Return the value of currentCard. *Hint: Don't overthink this! Use the keyword return.*

8. Create a ```function``` called createElements that will take in a parameter called ```card```. This parameter ```card``` will be a placeholder for a random card that we obtain from our generateCard function. In this function, do the following:
* Assign the value of 0 to your counter variable.
* Assign a character array of the description of the card into the charArray variable.  *If you look inside the data.js file, the terms array is an array of objects. Each object has a property called description. How do we 1). access the property description from our card object and 2). make that into an array of characters?*
  * An array of characters can be obtained by using the method String.split('')! Substitute the word string for an actual string.
* Create a for loop that will iterate over the length of the ```charArray```. In this loop, do the following:
  * Create a variable p that will store a newly created 'P' (paragraph) element.
  * Assign each character from the charArray to the innerHTML of p. Use ```i```! *Hint: p.innerHTML = The ith element of the charArray*
  * Append this p element to the flashcard.  

9. Add an ```Event Listener``` to the ```window``` that will listen for a ```keydown```. On key down, create a function that will take in ```event``` as the parameter. In this function, do the following:
  * Create a variable called currentChar and store the character code of the 1st character in the description of the currentCard using our ```currentCard``` and ```counter``` variables. To do that, we can use the ```charCodeAt``` String method.

  ``` JavaScript
  "hello".charCodeAt(0);
  // This will print out the character code of "h", the character at index 0.

  "hello".charCodeAt(1);
  // This will print out the character code of "e", the character at index 1.
  ```
    * This sounds like a lot so let's break it down. We want to 1). Access the value of the description property from our currentCard variable (Remember currentCard is storing an object!). 2). Get the character code at index 0 of the description string using the above String method.
  * Create a variable called currentKeyCode and store the String representing the currentChar character code that we obtained. To do that, we can use the ```String.fromCharCode(character)``` method as follows:
    ``` JavaScript
    String.fromCharCode(2333);
    // This will return a string that the character code 2333 represents. Change the 2333 to the character we are interested in changing to a String.
    ```
  * Create a variable called currentInput and store the String representing the character code of the keyCode of the key the user is pressing on the keyboard. *Hint: You know how to generate a String of a specific character code. The character code we are interested in now is that of the current key being pressed. We can access this using event.keyCode!*

  * Let's check if the currentInput (what is being pressed) is equal to the upper case version of the currentKeyCode (the letter that the user is "on" now). Why uppercase? The keydown event uses the uppercase letter's code whether the user types in lowercase or uppercase.
    * Create an if statement that checks if ```currentInput``` is equal to the uppercase version of ```currentKeyCode```.
      * In this if statement, create a variable ```pElements``` that will collect all of the p elements. Instead of using ```document.getElementById```, we will use the following:
      ``` javascript
      document.querySelectorAll('p');
      //This will select all of the p elements and store it into a nodelist.
      ```

      * All the p elements are now stored in something called a nodelist. A nodelist is a collection of DOM elements. In this case, it is a collection of p elements. It is like an array, but it actually is not a real array. However, we can still access elements from it like an array. If we correctly type in the right letter of the 1st p element, we want the 1st p element to get bigger and change color! We already made a class called "typed" to have the styles we want, so access the element at the counter's position from your ```pElements``` nodelist and set a class name ```typed``` to it.
      * Now, increment your counter by 1 so we can go to the next character.
      * Create an if statement that will check if the ```counter``` is equal to the length of the ```charArray```. In this if statement, do the following:
        * Set the counter back to 0.
        * Set the innerHTML of the flashcard to "" to reset the card's contents.
        * Call the createElements function and pass in the function generateCard(). What's going on here? The generateCard function will return a random card that the createElements functions can use! 
