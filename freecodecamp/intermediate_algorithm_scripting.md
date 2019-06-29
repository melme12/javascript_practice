# Javascript Algorithms And Data Structures Certification (freeCodeCamp)

## [Intermediate Algorithm Scripting](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting)

### 1. Sum All Numbers in a Range

We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them.

The lowest number will not always come first.

**My Solution:**
```javascript
function sumAll(arr) {
  let sortedNum = arr.sort((a, b) => a - b);
  let start = sortedNum[0];
  let end = sortedNum[1];
  let newVar = 0;
  
  for (var i= start; i <= end; i++){
        newVar += i;
    }
  return(newVar);
}

sumAll([1, 4]);
```

### 2. Diff Two Arrays

Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

Remember to use Read-Search-Ask if you get stuck. Try to pair program. Write your own code.

**My Solution:**
```javascript
function diffArray(arr1, arr2) {
  var newArr = [];
  // Same, same; but different.
  newArr = arr1.filter(x => !arr2.includes(x)).concat(arr2.filter(x => !arr1.includes(x)));
  return newArr;
}

diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]);
```

### 3. Seek and Destroy

You will be provided with an initial array (the first argument in the destroyer function), followed by one or more arguments. Remove all elements from the initial array that are of the same value as these arguments.

**Note**
You have to use the `arguments` object.

**My Solution:**
```javascript
function destroyer(arr) {
  // Remove all the values
  let otherArgs = Array.from(arguments);
  let givenArr = otherArgs.shift();
  givenArr = givenArr.filter(function(item) {
    return !otherArgs.includes(item);
  })
  return givenArr;
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```

### 4. Wherefore art thou

Make a function that looks through an array of objects (first argument) and returns an array of all objects that have matching name and value pairs (second argument). Each name and value pair of the source object has to be present in the object from the collection if it is to be included in the returned array.

For example, if the first argument is `[{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }]`, and the second argument is `{ last: "Capulet" }`, then you must return the third object from the array (the first argument), because it contains the name and its value, that was passed on as the second argument.

**My Solution:**
```javascript
function whatIsInAName(collection, source) {
  // What's in a name?
  var arr = [];
  // Only change code below this line
 
  var objKeys = Object.keys(source);

  return collection.filter(function (obj) {
    return objKeys.every(function (item) {
      return obj.hasOwnProperty(item) && obj[item] === source[item];
    });
  });
  
  // Only change code above this line
  return item;
}

whatIsInAName([{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }], { last: "Capulet" });
```

### 5. Spinal Tap Case

Convert a string to spinal case. Spinal case is all-lowercase-words-joined-by-dashes.

**My Solution:**
```javascript
function spinalCase(str) {
  // "It's such a fine line between stupid, and clever."
  // --David St. Hubbins

  let regex = /\s+|_+/g;

  // Replace low-upper case to low-space-uppercase: puts a space before any encountered uppercase characters in the string str so that the spaces can be replaced by dashes later on
  str = str.replace(/([a-z])([A-Z])/g, '$1 $2');

  // Replace space and underscore with "-"
  return str.replace(regex, '-').toLowerCase();
}

spinalCase('This Is Spinal Tap');
```
**Notes:** This one was hard. I tried several approaches, but failed with the test Cases where the string had no characters between the words. Had to look at the solution in the end.

### 6. Pig Latin

Translate the provided string to pig latin.

Pig Latin takes the first consonant (or consonant cluster) of an English word, moves it to the end of the word and suffixes an "ay".

If a word begins with a vowel you just add "way" to the end.

Input strings are guaranteed to be English words in all lowercase.

**My Solution:**
```javascript

```
