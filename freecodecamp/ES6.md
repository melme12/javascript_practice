# Javascript Algorithms And Data Structures Certification (freeCodeCamp)

## [ES6](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/es6/)

### 1. Explore Differences Between the var and let Keywords

Update the code so it only uses the `let` keyword.

**My Solution:**
```javascript
let catName;
let quote;
function catTalk() {
  "use strict";

  catName = "Oliver";
  quote = catName + " says Meow!";

}
catTalk();
```

### 2. Compare Scopes of the var and let Keywords

Fix the code so that `i` declared in the if statement is a separate variable than `i` declared in the first line of the function. Be certain not to use the `var` keyword anywhere in your code.

This exercise is designed to illustrate the difference between how `var` and `let` keywords assign scope to the declared variable. When programming a function similar to the one used in this exercise, it is often better to use different variable names to avoid confusion.

**My Solution:**
```javascript
'use strict';
function checkScope() {
  let i = "function scope";
  if (true) {
   let i = "block scope";
    console.log("Block scope i is: ", i);
  }
  console.log("Function scope i is: ", i);
  return i;
}
```

### 3. Declare a Read-Only Variable with the const Keyword

Change the code so that all variables are declared using `let` or `const`. Use `let` when you want the variable to change, and `const` when you want the variable to remain constant. Also, rename variables declared with `const` to conform to common practices, meaning constants should be in all caps.

**My Solution:**
```javascript
function printManyTimes(str) {
  "use strict";

  // change code below this line

  const SENTENCE = str + " is cool!";
  for (let i = 0; i < str.length; i+=2) {
    console.log(SENTENCE);
  }

  // change code above this line

}
printManyTimes("freeCodeCamp");
```

### 4. Mutate an Array Declared with const

An array is declared as `const s = [5, 7, 2]`. Change the array to `[2, 5, 7]` using various element assignment.

**My Solution:**
```javascript
const s = [5, 7, 2];
function editInPlace() {
  "use strict";
  // change code below this line

  s[0] = 2;
  s[1] = 5;
  s[2] = 7;

  // change code above this line
}
editInPlace();
```

### 5. Prevent Object Mutation

In this challenge you are going to use `Object.freeze` to prevent mathematical constants from changing. You need to freeze the `MATH_CONSTANTS` object so that no one is able alter the value of `PI`, add, or delete properties .

**My Solution:**
```javascript
function freezeObj() {
  "use strict";
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  // change code below this line
  
  Object.freeze(MATH_CONSTANTS);

  // change code above this line
  try {
    MATH_CONSTANTS.PI = 99;
  } catch( ex ) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();
```

### 6. Use Arrow Functions to Write Concise Anonymous Functions

Rewrite the function assigned to the variable `magic` which returns a new `Date()` to use arrow function syntax. Also make sure nothing is defined using the keyword `var`.

**My Solution:**
```javascript
const magic = () => new Date();
```

### 7. Write Arrow Functions with Parameters

Rewrite the `myConcat` function which appends contents of `arr2` to `arr1` so that the function uses arrow function syntax.

**My Solution:**
```javascript
const myConcat = (arr1, arr2) => arr1.concat(arr2);

// test your code
console.log(myConcat([1, 2], [3, 4, 5]));
```

### 8. Write Higher Order Arrow Functions

Use arrow function syntax to compute the square of only the positive integers (decimal numbers are not integers) in the array `realNumberArray` and store the new array in the variable `squaredIntegers`.

**My Solution:**
```javascript
const realNumberArray = [4, 5.6, -9.8, 3.14, 42, 6, 8.34, -2];
const squareList = (arr) => {
  "use strict";
  // change code below this line

  const squaredIntegers = arr.filter((num) => num > 0 && num % parseInt(num) === 0).map((num) => Math.pow(num, 2));

  // change code above this line
  return squaredIntegers;
};

// test your code
const squaredIntegers = squareList(realNumberArray);
console.log(squaredIntegers);
```

**Notes:** Chained function: filter nums from arr that are bigger than 0 and an integer and for every of those num (.map()) use Math.pow(base, exponent).

### 9. Set Default Parameters for Your Functions

Modify the function `increment` by adding default parameters so that it will add 1 to `number` if `value` is not specified.

**My Solution:**
```javascript
const increment = (function() {
  "use strict";
  return function increment(number, value = 1) {
    return number + value;
  };
})();
console.log(increment(5, 2)); // returns 7
console.log(increment(5)); // returns 6
```

### 10. Use the Rest Operator with Function Parameters

Modify the function `sum` so that it uses the rest operator and it works in the same way with any number of parameters.

**My Solution:**
```javascript
const sum = (function() {
  "use strict";
  return function sum(...args) {
    return args.reduce((a, b) => a + b, 0);
  };
})();
console.log(sum(1, 2, 3)); // 6
```
