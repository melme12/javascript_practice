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
function translatePigLatin(str) {

  var regexVowels = /[aeiou]/gi;

  if (str[0].match(regexVowels)) {
    return str.concat("way");
  } else if (str.match(regexVowels) === null) {
    return str.concat("ay");
  } else {
    var howManyBeforeVowel = str.indexOf(str.match(regexVowels)[0]);
    return str.substr(howManyBeforeVowel) + str.substr(0, howManyBeforeVowel) + 'ay';
  }
}

translatePigLatin("consonant");
```

### 7. Search and Replace

Perform a search and replace on the sentence using the arguments provided and return the new sentence.

First argument is the sentence to perform the search and replace on.

Second argument is the word that you will be replacing (before).

Third argument is what you will be replacing the second argument with (after).

**Note**
Preserve the case of the first character in the original word when you are replacing it. For example if you mean to replace the word "Book" with the word "dog", it should be replaced as "Dog".

**My Solution:**
```javascript
function myReplace(str, before, after) {

  if (/[A-Z]/.test( before[0]) === true) {
    let toUpCase = after.charAt(0).toUpperCase() + after.slice(1);
    return str.split(before).join(toUpCase);

  } else if (/[A-Z]/.test( before[0]) === false) {
    let toLoCase = after.charAt(0).toLowerCase() + after.slice(1);
    return str.split(before).join(toLoCase);

  } else {
    return str.split(before).join(after);
  }
}

myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
```

### 8. DNA Pairing

The DNA strand is missing the pairing element. Take each character, get its pair, and return the results as a 2d array.

Base pairs are a pair of AT and CG. Match the missing element to the provided character.

Return the provided character as the first element in each array.

For example, for the input GCG, return [["G", "C"], ["C","G"],["G", "C"]]

The character and its pair are paired up in an array, and all the arrays are grouped into one encapsulating array.

**My Solution:**
```javascript
function pairElement(str) {
  
  let arr = str.split("");
  var newArr = [];

  for (var i = 0 ; i<arr.length; i++){
    if (arr[i]=="A") {
      newArr.push(["A", "T"]);
    } else if (arr[i]=="T") {
      newArr.push(["T", "A"]);
    } else if (arr[i]=="C") {
      newArr.push(["C", "G"]);
    } else if (arr[i]=="G") {
      newArr.push(["G", "C"]);
    }
  }
  return newArr;
}
pairElement("GCG");
```

### 9. Missing letters

Find the missing letter in the passed letter range and return it.

If all letters are present in the range, return undefined.

**My Solution:**
```javascript
function fearNotLetter(str) {
  for (var i = 0; i < str.length - 1; i++) {
    if (str.charCodeAt(i + 1) - str.charCodeAt(i) != 1) {
      return String.fromCharCode(str.charCodeAt(i) + 1);
    }
  }
}

fearNotLetter("abce");
```

### 10. Sorted Union

Write a function that takes two or more arrays and returns a new array of unique values in the order of the original provided arrays.

In other words, all values present from all arrays should be included in their original order, but with no duplicates in the final array.

The unique numbers should be sorted by their original order, but the final array should not be sorted in numerical order.

Check the assertion tests for examples.

**My Solution:**
```javascript
function uniteUnique(...arr) {
  let newArr = [].concat(...arr); 
  return [...new Set(newArr)];
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```
**Notes:** I looked up how to get rid of duplicates. I found `set`: "Set object lets you store unique values of any type. In other words, Set will automatically remove duplicates for us." Then I first tried to concat the original array with the rest parameters and tried to `flat()` it, which of course didn't work. All I had to do was to use an empty array with `concat(...arr)`, `flat()` wasn't necessary at all.

### 11. Convert HTML Entities

Convert the characters `&`, `<`, `>`, `"` (double quote), and `'` (apostrophe), in a string to their corresponding HTML entities.

**My Solution:**
```javascript
function convertHTML(str) {
  const regex = /[&<>"']/g;
  const obj = {
    '"': "&quot;",
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;", 
    "'": "&apos;"
  }
  return str.replace(regex, (x => obj[x]));
  //Long function:
  //return str.replace(regex, (function(x){return obj[x]}));
}

convertHTML("Dolce & Gabbana");
```

### 12. Sum All Odd Fibonacci Numbers

Given a positive integer `num`, return the sum of all odd Fibonacci numbers that are less than or equal to `num`.

The first two numbers in the Fibonacci sequence are 1 and 1. Every additional number in the sequence is the sum of the two previous numbers. The first six numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8.

For example, `sumFibs(10)` should return `10` because all odd Fibonacci numbers less than or equal to `10` are 1, 1, 3, and 5.

**My Solution:**
```javascript
function sumFibs(num) {
  let fibArr = [1, 1];
  let i = 2;

  while (fibArr[i-1] + fibArr[i-2] <= num) {
      fibArr.push(fibArr[i-1] + fibArr[i-2]);
      i++;
  }

  let oddArr = fibArr.filter(x => x % 2 !== 0);

  return oddArr.reduce((a, b) => a + b, 0);
}

sumFibs(4);
```

### 13. Sum All Primes

Sum all the prime numbers up to and including the provided number.

A prime number is defined as a number greater than one and having only two divisors, one and itself. For example, 2 is a prime number because it's only divisible by one and two.

The provided number may not be a prime.

**My Solution:**
```javascript
function sumPrimes(num) {
  
  let primeNum = [];
  let isPrime;

  for (var i = 2; i <= num; i++) {    
    for (var j = 2; (isPrime = i === j || i % j !== 0) && j <= i / 2; j++) {}

    isPrime && primeNum.push(i);
  }

  return primeNum.reduce((a, b) => a + b)
}

sumPrimes(10);
```

### 14. Smallest Common Multiple

Find the smallest common multiple of the provided parameters that can be evenly divided by both, as well as by all sequential numbers in the range between these parameters.

The range will be an array of two numbers that will not necessarily be in numerical order.

For example, if given 1 and 3, find the smallest common multiple of both 1 and 3 that is also evenly divisible by all numbers between 1 and 3. The answer here would be 6.

**My Solution:**
```javascript
function smallestCommons(arr) {

  arr = arr.sort((a, b) => a - b);

  let min = arr[0];
  let max = arr[1];
  
  var newArr = [];
  for (var i = min; i <= max; i++) {
      newArr.push(i);
  }
  
  var x = 0;
  var loop = 1;
  var n;

  do {
    x = newArr[0] * loop * newArr[1];
    for (n = 2; n < newArr.length; n++) {
      if (x % newArr[n] !== 0) {
        break;
      }
    }
    loop++;
  } while (n !== newArr.length);

  return x;
}

smallestCommons([1,5]);
```
**Notes:** The code works locally, but won't pass FFC's test with `[1, 13]`. Others have encountered similar problems, so it seems to be a bug in their test.

### 15. Drop it

Given the array `arr`, iterate through and remove each element starting from the first element (the 0 index) until the function `func` returns `true` when the iterated element is passed through it.

Then return the rest of the array once the condition is satisfied, otherwise, arr should be returned as an empty array.

**My Solution:**
```javascript
function dropElements(arr, func) {
  const length = arr.length;
  for (let i = 0; i < length; i++) {
    
    if (func(arr[0]) === true) {
      break;
    } else {
      arr.shift();
    }
  }
  return arr;
}

dropElements([1, 2, 3], function(n) {return n < 3; });
```

### 15. Steamroller

Flatten a nested array. You must account for varying levels of nesting.

**My Solution**
```javascript
function steamrollArray(arr) {
  // I'm a steamroller, baby

  return arr.reduce((acc, val) => Array.isArray(val) ? acc.concat(steamrollArray(val)) : acc.concat(val), []);
}

steamrollArray([1, [2], [3, [[4]]]]);
```

### 16. Binary Agents

Return an English translated sentence of the passed binary string.

The binary string will be space separated.

**My Solution:**
```javascript
function binaryAgent(str) {

  let arr = str.split(" ");

  return arr.map(function(x) {
    return String.fromCharCode(parseInt(x, 2));
  }).join("");
}

binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");
```
**Notes:** Really hard one. Had to look on the 1st hint. First, turn the string into an array, so we can iterate through it with `map()`. `String.fromCharCode()` returns a string created from the specified sequence of UTF-16 code units, `parseInt(x, 2)` turns binary into decimal. In the end, join without space, which is already in the binary code.

### 17. Everything Be True

Check if the predicate (second argument) is truthy on all elements of a collection (first argument).

In other words, you are given an array collection of objects. The predicate `pre` will be an object property and you need to return `true` if its value is `truthy`. Otherwise, return `false`.

In JavaScript, `truthy` values are values that translate to `true` when evaluated in a Boolean context.

Remember, you can access object properties through either dot notation or `[]` notation.

**My Solution:**
```javascript
function truthCheck(collection, pre) {
  // Is everyone being true?

  return collection.every(function (item) {

    return item.hasOwnProperty(pre) && Boolean(item[pre]);

  });
}

truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy", "sex": "male"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex");
```
**Notes:** Come back and redo this lesson!

### 18. Arguments Optional

Create a function that sums two arguments together. If only one argument is provided, then return a function that expects one argument and returns the sum.

For example, `addTogether(2, 3)` should return `5`, and `addTogether(2)` should return a function.

Calling this returned function with a single argument will then return the sum:

`var sumTwoAnd = addTogether(2);`

`sumTwoAnd(3)` returns `5`.

If either argument isn't a valid number, return undefined.

**My Solution:**
```javascript
function addTogether() {

  const checkIfNum = function(num) {
    if (typeof num !== 'number') {
      return undefined;
    } else {
      return num;
    }
  }
  
  let num1 = checkIfNum(arguments[0]);
  let num2 = checkIfNum(arguments[1]);
  
  if (arguments.length >= 2) {
    if (num1 === undefined || num2 === undefined) {
      return undefined;
    } else {
      return num1 + num2;
    }
  } else {
    if (num1 === undefined) {
      return undefined;
    } else {
      return function(otherNum) {
        if (checkIfNum(otherNum) === undefined) {
          return undefined;
        } else {
          return num1 + otherNum;
        }
      }
    }
  }

}

addTogether(2, 3);
```

### 19. Make a Person

Fill in the object constructor with the following methods below:

`getFirstName() getLastName() getFullName() setFirstName(first) setLastName(last) setFullName(firstAndLast)`

Run the tests to see the expected output for each method.

The methods that take an argument must accept only one argument and it has to be a string.

These methods must be the only available means of interacting with the object.

**My Solution:**
```javascript
var Person = function(firstAndLast) {
  // Complete the method below and implement the others similarly

  let firstName;
  let lastName;

  function splitName(str) {
    firstName = str.split(" ")[0];
    lastName = str.split(" ")[1];
  }

  splitName(firstAndLast);

  this.getFirstName = function(){
    return firstName;
  };

  this.getLastName = function(){
    return lastName;
  };

  this.getFullName = function(){
    return firstName + " " + lastName;
  };

  this.setFirstName = function(str){
    firstName = str;
  };
 
  this.setLastName = function(str) {
    lastName = str;
  }

  this.setFullName = function(str) {
    splitName(str);
  }

};

var bob = new Person('Bob Ross');
bob.getFullName();
```

### 20. Map the Debris

Return a new array that transforms the elements' average altitude into their orbital periods (in seconds).

The array will contain objects in the format `{name: 'name', avgAlt: avgAlt}`.

You can read about orbital periods on Wikipedia.

The values should be rounded to the nearest whole number. The body being orbited is Earth.

The radius of the earth is 6367.4447 kilometers, and the GM value of earth is 398600.4418 km3s-2.

**My Solution:**
```javascript

```
