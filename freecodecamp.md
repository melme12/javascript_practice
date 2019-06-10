# Javascript Algorithms And Data Structures Certification (freeCodeCamp)

## [Basic Algorithm Scripting](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/basic-algorithm-scripting/)

### 1. Convert Celsius to Fahrenheit

The algorithm to convert from Celsius to Fahrenheit is the temperature in Celsius times `9/5`, plus `32`.

You are given a variable `celsius` representing a temperature in Celsius. Use the variable `fahrenheit` already defined and assign it the Fahrenheit temperature equivalent to the given Celsius temperature. Use the algorithm mentioned above to help convert the Celsius temperature to Fahrenheit.

Don't worry too much about the function and return statements as they will be covered in future challenges. For now, only use operators that you have already learned.

**My Solution:**
```javascript
function convertToF(celsius) {
  let fahrenheit = (celsius * (9 / 5) + 32);
  return fahrenheit;
}

convertToF(30);
```

### 2.Reverse a String

Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

**My Solution:**
```javascript
function reverseString(str) {
  let arr = str.split('');
  let reverseArr = arr.reverse();
  let reverseStr = reverseArr.join('');
  return reverseStr;
}

reverseString("hello");
```

### 3. Factorialize a Number

Return the factorial of the provided integer.

If the integer is represented with the letter n, a factorial is the product of all positive integers less than or equal to `n`.

Factorials are often represented with the shorthand notation n!

For example: `5! = 1 * 2 * 3 * 4 * 5 = 120`

Only integers greater than or equal to zero will be supplied to the function.

**My Solution:**
```javascript
function factorialize(num) {
  let a = 1;
  for (let i = 1; i <= num; i++) {
    a = a * i;
  }
  return a;
}

factorialize(5);
```

### 4. Find the Longest Word in a String

Return the length of the longest word in the provided sentence.

Your response should be a number.

**My Solution:**
```javascript
function findLongestWordLength(str) {
  var strArr = str.split(' ');
  var wordLen = 0;
  for(let i = 0; i < strArr.length; i++){
    if(strArr[i].length > wordLen){
	    wordLen = strArr[i].length;
     }
  }
  return wordLen;
}

findLongestWordLength("The quick brown fox jumped over the lazy dog");
```

### 5. Return Largest Numbers in Arrays

Return an array consisting of the largest number from each provided sub-array. For simplicity, the provided array will contain exactly 4 sub-arrays.

Remember, you can iterate through an array with a simple for loop, and access each member with array syntax `arr[i]`.

**My Solution:**

```javascript
function largestOfFour(arr) {
  // You can do this!
  var newArr = [];
  for (let i = 0; i < arr.length; i++) {
    arr[i].sort((a, b) => b - a);
    newArr[i] = arr[i][0];
  }
  return newArr;
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```

### 6. Confirm the Ending

Check if a string (first argument, `str`) ends with the given target string (second argument, `target`).

This challenge can be solved with the `.endsWith()` method, which was introduced in ES2015. But for the purpose of this challenge, we would like you to use one of the JavaScript substring methods instead.

**My Solution:**

```javascript
function confirmEnding(str, target) {
  // "Never give up and good luck will find you."
  // -- Falcor
  if (target === str.substr(- target.length)) {
     return true;
     } else {
       return false;
   }
}

confirmEnding("Bastian", "n");
```

### 7. Repeat a String Repeat a String

Repeat a given string `str` (first argument) for `num` times (second argument). Return an empty string if `num` is not a positive number.

**My Solution:**

```javascript
function repeatStringNumTimes(str, num) {
  // repeat after me
  var multiStr = "";
  while (num > 0) {
    multiStr += str;
    num--;
  }
  return multiStr;
}

repeatStringNumTimes("abc", 3);
```

### 8. Truncate a String

Truncate a string (first argument) if it is longer than the given maximum string length (second argument). Return the truncated string with a `...` ending.

**My Solution:*

```javascript
function truncateString(str, num) {
  // Clear out that junk in your trunk
  let trunStr = str.substring(0, num);
  let newStr = "";
  if (str.length > num) {
    return trunStr + "...";
  } else {
    return trunStr;
  }
}

truncateString("A-tisket a-tasket A green and yellow basket", 8);
```
