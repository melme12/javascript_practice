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
var watchList = [.....]

// Add your code below this line
let rating = watchList.map( (watchListObj) => ({
  "title":watchListObj["Title"],
  "rating":watchListObj["imdbRating"]
  }) );
// Add your code above this line

console.log(rating); 
```

### 8. Implement map on a Prototype

Write your own `Array.prototype.myMap()`, which should behave exactly like `Array.prototype.map()`. You may use a `for` loop or the `forEach` method.

**My Solution:**
```javascript
// the global Array
var s = [23, 65, 98, 5];

Array.prototype.myMap = function(callback){
  var newArray = [];
  // Add your code below this line
  this.forEach(item => newArray.push(callback(item)));
  // Add your code above this line
  return newArray;

};

var new_s = s.myMap(function(item){
  return item * 2;
});
```

### 9. Use the filter Method to Extract Data from an Array

The variable `watchList` holds an array of objects with information on several movies. Use a combination of `filter` and `map` to return a new array of objects with only `title` and `rating` keys, but where `imdbRating` is greater than or equal to 8.0. Note that the rating values are saved as strings in the object and you may want to convert them into numbers to perform mathematical operations on them.

**My Solution:**
```javascript
var watchList = [.....]

// Add your code below this line
var filteredList = watchList.map(function(x) {
  return {title: x["Title"], rating: x["imdbRating"]}
}).filter((x) => x.rating >= 8);

// Add your code above this line
console.log(filteredList); 
```

### 10. Implement the filter Method on a Prototype

Write your own `Array.prototype.myFilter()`, which should behave exactly like `Array.prototype.filter()`. You may use a for loop or the `Array.prototype.forEach()` method.

**My Solution:**
```javascript
// the global Array
var s = [23, 65, 98, 5];

Array.prototype.myFilter = function(callback){
  var newArray = [];
  // Add your code below this line
  
  for (let i = 0; i< this.length; i++) {
    if(callback(this[i])=== true ){
      newArray.push(this[i]);
    }
  }

  // Add your code above this line
  return newArray;

};

var new_s = s.myFilter(function(item){
  return item % 2 === 1;
});
```

### 11. Return Part of an Array Using the slice Method

Use the `slice` method in the `sliceArray` function to return part of the `anim` array given the provided `beginSlice` and `endSlice` indices. The function should return an array.

**My Solution:**
```javascript
function sliceArray(anim, beginSlice, endSlice) {
  // Add your code below this line
  return anim.slice(beginSlice, endSlice);
  // Add your code above this line
}
var inputAnim = ["Cat", "Dog", "Tiger", "Zebra", "Ant"];
sliceArray(inputAnim, 1, 3);
```

### 12. Remove Elements from an Array Using slice Instead of splice

Rewrite the function `nonMutatingSplice` by using `slice` instead of `splice`. It should limit the provided `cities` array to a length of 3, and return a new array with only the first three items.

Do not mutate the original array provided to the function.

**My Solution:**
```javascript
function nonMutatingSplice(cities) {
  // Add your code below this line
  return cities.slice(0, 3);
  // Add your code above this line
}
var inputCities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
nonMutatingSplice(inputCities);
```

### 13. Combine Two Arrays Using the concat Method

Use the `concat` method in the `nonMutatingConcat` function to concatenate `attach` to the end of `original`. The function should return the concatenated array.

**My Solution:**
```javascript
function nonMutatingConcat(original, attach) {
  // Add your code below this line
  return original.concat(attach);
  // Add your code above this line
}
var first = [1, 2, 3];
var second = [4, 5];
nonMutatingConcat(first, second);
```

### 14. Add Elements to the End of an Array Using concat Instead of push

Change the `nonMutatingPush` function so it uses `concat` to add `newItem` to the end of `original` instead of `push`. The function should return an array.

**My Solution:**
```javascript
function nonMutatingPush(original, newItem) {
  // Add your code below this line
  return original.concat(newItem);
  // Add your code above this line
}
var first = [1, 2, 3];
var second = [4, 5];
nonMutatingPush(first, second);
```

### 15. Use the reduce Method to Analyze Data

The variable `watchList` holds an array of objects with information on several movies. Use `reduce` to find the average IMDB rating of the movies **directed by Christopher Nolan**. Recall from prior challenges how to `filter` data and `map` over it to pull what you need. You may need to create other variables, but save the final average into the variable `averageRating`. Note that the rating values are saved as strings in the object and need to be converted into numbers before they are used in any mathematical operations.

**My Solution:**
```javascript
watchList = [......]
// Add your code below this line

//filter List for everything Christopher Nolan
let filteredList = watchList.filter(x => x.Director === "Christopher Nolan");

//get ratings and turn strings into numbers
let mappedList = filteredList.map(y => Number(y.imdbRating))

//divide the sum of mappedList items throught the length of filteredlist
var averageRating = mappedList.reduce((x1, x2) => x1 + x2) / filteredList.length;

// Add your code above this line

console.log(averageRating); 
```

### 16. Sort an Array Alphabetically using the sort Method

Use the `sort` method in the `alphabeticalOrder` function to sort the elements of `arr` in alphabetical order.

**My Solution:**
```javascript

```
