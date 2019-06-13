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

**My Solution:**

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

**Notes:** Forgot to trun str into str.length (line 5) and spent nearly an hour to search for the mistake. 🤦

### 9. Finders Keepers

Create a function that looks through an array (first argument) and returns the first element in the array that passes a truth test (second argument). If no element passes the test, return undefined.

**My Solution:**

```javascript
function findElement(arr, func) {
  return arr.find(func);
}

findElement([1, 2, 3, 4], num => num % 2 === 0);
```

### 10. Boo who

Check if a value is classified as a boolean primitive. Return true or false.

Boolean primitives are true and false.

**My Solution:**
```javascript
function booWho(bool) {
  // What is the new fad diet for ghost developers? The Boolean.
  if (typeof bool === 'boolean') {
    return true;
  } else {
    return false;
  }
}

booWho(null);
```

**Notes:** I still have to work through the tasks word by word, which is why my solutions are often quite long. By now I know it would have been  enough to use `function booWho(bool) {return typeof bool === 'boolean';}`: If `typeof bool` is equal to `'boolean'` (the output of `typeof`in case of booleans) it will return true.

### 11. Title Case a Sentence

Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

For the purpose of this exercise, you should also capitalize connecting words like "the" and "of".

**My Solution:**

```javascript
function titleCase(str) {
  str = str.toLowerCase().split(' ');
  for (let i = 0; i < str.length; i++) {
    str[i] = str[i].charAt(0).toUpperCase() + str[i].slice(1);
  }
  return str.join(" ");
}

titleCase("I'm a little tea pot");
```

### 12. Slice and Splice

You are given two arrays and an index.

Use the array methods `slice` and `splice` to copy each element of the first array into the second array, in order.

Begin inserting elements at index `n` of the second array.

Return the resulting array. The input arrays should remain the same after the function runs.

**My Solution:**

```javascript
function frankenSplice(arr1, arr2, n) {
  // It's alive. It's alive!
  let newArr = arr2.slice();
  for (let i = 0; i < arr1.length; i++) {
    newArr.splice(n, 0, arr1[i]);
    n++;
  }
  return newArr;
}

frankenSplice([1, 2, 3], [4, 5, 6], 1);
```

### 13. Falsy Bouncer

Remove all falsy values from an array.

Falsy values in JavaScript are `false`, `null`, `0`, `""`, `undefined`, and `NaN`.

Hint: Try converting each value to a Boolean.

**My Solution:**

```javascript
function bouncer(arr) {
  // Don't show a false ID to this bouncer.
  return arr.filter(Boolean);
}

bouncer([7, "ate", "", false, 9]);
```

**Notes:** MDN says: "The filter() method creates a new array with all elements that pass the test implemented by the provided function." So it 'filters' the array and only returns the values that pass the test. `Boolean` returns `false` when passed any falsy values.

### 14. Where do I Belong 

Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

For example, `getIndexToIns([1,2,3,4], 1.5)` should return `1` because it is greater than `1` (index 0), but less than `2` (index 1).

Likewise, `getIndexToIns([20,3,5], 19)` should return `2` because once the array has been sorted it will look like `[3,5,20]` and `19` is less than `20` (index 2) and greater than `5` (index 1).

```javascript
function getIndexToIns(arr, num) {
  // Find my place in this sorted array.
  let newArr = arr.push(num); // 1. push num to arr
  let sortThisArr = arr.sort((a, b) => a - b); // 2. sort array by numbers
  return sortThisArr.indexOf(num);
}

getIndexToIns([40, 60], 50);
```

**Notes:** I wrote a plan with this one, which didn't quite work out. Then I figured out the steps were okay, but I had to order it differently. Remember this for the next ones! Sometimes it is the order of your plan which has to be overthought, not the plan itself...

### 15. Mutations

Return true if the string in the first element of the array contains all of the letters of the string in the second element of the array.

For example, `["hello", "Hello"]`, should return true because all of the letters in the second string are present in the first, ignoring case.

The arguments `["hello", "hey"]` should return false because the string "hello" does not contain a "y".

Lastly, `["Alien", "line"]`, should return true because all of the letters in "line" are present in "Alien".

```javascript
function mutation(arr) {
  
  for (let i = 0; i < arr.length; i++) {
    arr[i] = arr[i].toLowerCase();
    }

  let newArr = arr.splice(1); // turn the array into two arrays

  let secondElement = newArr[0].split("");
  let firstElement = arr[0].split("");
  
  return secondElement.every(x => firstElement.includes(x));
}

mutation(["hello", "hey"]);
```

**Notes:**  1. turn everything to lowercase; 2. split arr into two arrays; 3. compare if every element of secondElement is included in firstElement (every() returns a boolean).
