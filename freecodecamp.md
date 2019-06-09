# Javascript Algorithms And Data Structures Certification (freeCodeCamp)

## [Basic Algorithm Scripting](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/basic-algorithm-scripting/)

### 1. Convert Celsius to Fahrenheit

The algorithm to convert from Celsius to Fahrenheit is the temperature in Celsius times 9/5, plus 32.

You are given a variable celsius representing a temperature in Celsius. Use the variable fahrenheit already defined and assign it the Fahrenheit temperature equivalent to the given Celsius temperature. Use the algorithm mentioned above to help convert the Celsius temperature to Fahrenheit.

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

Remember to use Read-Search-Ask if you get stuck. Write your own code.

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

If the integer is represented with the letter n, a factorial is the product of all positive integers less than or equal to n.

Factorials are often represented with the shorthand notation n!

For example: 5! = 1 * 2 * 3 * 4 * 5 = 120

Only integers greater than or equal to zero will be supplied to the function.

Remember to use Read-Search-Ask if you get stuck. Write your own code.

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

Remember to use Read-Search-Ask if you get stuck. Write your own code.

**My Solution:**
```javascript

```
