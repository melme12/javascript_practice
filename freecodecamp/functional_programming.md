# Javascript Algorithms And Data Structures Certification (freeCodeCamp)

## [Functional Programming](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/functional-programming)

### 1. Learn About Functional Programming
The members of freeCodeCamp happen to love tea.

In the code editor, the `prepareTea` and `getTea` functions are already defined for you. Call the `getTea` function to get 40 cups of tea for the team, and store them in the `tea4TeamFCC` variable.

**My Solution:**
```javascript
/**
 * A long process to prepare tea.
 * @return {string} A cup of tea.
 **/
const prepareTea = () => 'greenTea';

/**
 * Get given number of cups of tea.
 * @param {number} numOfCups Number of required cups of tea.
 * @return {Array<string>} Given amount of tea cups.
 **/
const getTea = (numOfCups) => {
  const teaCups = [];
  
  for(let cups = 1; cups <= numOfCups; cups += 1) {
    const teaCup = prepareTea();
    teaCups.push(teaCup);
  }

  return teaCups;
};

// Add your code below this line

const tea4TeamFCC = getTea(40); // :(

// Add your code above this line

console.log(tea4TeamFCC);
```

### 2. Understand Functional Programming Terminology

Prepare 27 cups of green tea and 13 cups of black tea and store them in `tea4GreenTeamFCC` and `tea4BlackTeamFCC` variables, respectively. Note that the `getTea` function has been modified so it now takes a function as the first argument.

Note: The data (the number of cups of tea) is supplied as the last argument. We'll discuss this more in later lessons.

*My Solution:**
```javascript
/**
 * A long process to prepare green tea.
 * @return {string} A cup of green tea.
 **/
const prepareGreenTea = () => 'greenTea';

/**
 * A long process to prepare black tea.
 * @return {string} A cup of black tea.
 **/
const prepareBlackTea = () => 'blackTea';

/**
 * Get given number of cups of tea.
 * @param {function():string} prepareTea The type of tea preparing function.
 * @param {number} numOfCups Number of required cups of tea.
 * @return {Array<string>} Given amount of tea cups.
 **/
const getTea = (prepareTea, numOfCups) => {
  const teaCups = [];

  for(let cups = 1; cups <= numOfCups; cups += 1) {
    const teaCup = prepareTea();
    teaCups.push(teaCup);
  }

  return teaCups;
};

// Add your code below this line

const tea4GreenTeamFCC = getTea(prepareGreenTea, 27); // :(
const tea4BlackTeamFCC = getTea(prepareBlackTea, 13); // :(

// Add your code above this line

console.log(
  tea4GreenTeamFCC,
  tea4BlackTeamFCC
);
```

### 3. Understand the Hazards of Using Imperative Code

Run the code in the editor. It's using a method that has side effects in the program, causing incorrect output. The final list of open tabs should be `['FB', 'Gitter', 'Reddit', 'Twitter', 'Medium', 'new tab', 'Netflix', 'YouTube', 'Vine', 'GMail', 'Work mail', 'Docs', 'freeCodeCamp', 'new tab']` but the output will be slightly different.

Work through the code and see if you can figure out the problem, then advance to the next challenge to learn more.

**Notes:** When running the code, it doesn't show 'Vine'.

### 4. Avoid Mutations and Side Effects Using Functional Programming

Fill in the code for the function `incrementer` so it returns the value of the global variable `fixedValue` increased by one.

**My Solution:**
```javascript
// the global variable
var fixedValue = 4;

function incrementer () {
  // Add your code below this line
  const newValue = fixedValue + 1;
  return newValue;
  // Add your code above this line
}

var newValue = incrementer(); // Should equal 5
console.log(fixedValue); // Should print 4
```

### 5. Pass Arguments to Avoid External Dependence in a Function

Let's update the `incrementer` function to clearly declare its dependencies.

Write the `incrementer` function so it takes an argument, and then increases the value by one.

**My Solution:**
```javascript
// the global variable
var fixedValue = 4;

// Add your code below this line
function incrementer (arg) {
  return newValue = arg + 1;
  // Add your code above this line
}

var newValue = incrementer(fixedValue); // Should equal 5
console.log(fixedValue); // Should print 4
```

### 6. Refactor Global Variables Out of Functions

Refactor (rewrite) the code so the global array `bookList` is not changed inside either function. The `add` function should add the given `bookName` to the end of an array. The `remove` function should remove the given `bookName` from an array. Both functions should return an array, and any new parameters should be added before the `bookName` one.

**My Solution:**
```javascript
// the global variable
var bookList = ["The Hound of the Baskervilles", "On The Electrodynamics of Moving Bodies", "Philosophiæ Naturalis Principia Mathematica", "Disquisitiones Arithmeticae"];

/* This function should add a book to the list and return the list */
// New parameters should come before the bookName one

// Add your code below this line
function add (oldBookList,bookName) {
  return [...oldBookList, bookName];
}

/* This function should remove a book from the list and return the list */
// New parameters should come before the bookName one

// Add your code below this line
function remove (oldBookList,bookName) {
  if (oldBookList.indexOf(bookName) >= 0) {
    return oldBookList.filter((item) => item !== bookName);
    }
}

var newBookList = add(bookList, 'A Brief History of Time');
var newerBookList = remove(bookList, 'On The Electrodynamics of Moving Bodies');
var newestBookList = remove(add(bookList, 'A Brief History of Time'), 'On The Electrodynamics of Moving Bodies');

console.log(bookList);
```

### 7. Use the map Method to Extract Data from an Array

The `watchList` array holds objects with information on several movies. Use `map` to pull the title and rating from `watchList` and save the new array in the `rating` variable. The code in the editor currently uses a `for` loop to do this, replace the loop functionality with your `map` expression.


**My Solution:**
```javascript

```
