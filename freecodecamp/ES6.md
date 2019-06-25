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

### 11. Use the Spread Operator to Evaluate Arrays In-Place

Copy all contents of `arr1` into another array `arr2` using the spread operator.

**My Solution:**
```javascript
const arr1 = ['JAN', 'FEB', 'MAR', 'APR', 'MAY'];
let arr2;
(function() {
  "use strict";
  arr2 = [...arr1]; // change this line
})();
console.log(arr2);
```

### 12. Use Destructuring Assignment to Assign Variables from Objects

Use destructuring to obtain the average temperature for tomorrow from the input object `AVG_TEMPERATURES`, and assign value with key `tomorrow` to `tempOfTomorrow` in line.

**My Solution:**
```javascript
const AVG_TEMPERATURES = {
  today: 77.5,
  tomorrow: 79
};

function getTempOfTmrw(avgTemperatures) {
  "use strict";
  // change code below this line
  const { tomorrow: tempOfTomorrow } = avgTemperatures;
  // change code above this line
  return tempOfTomorrow;
}

console.log(getTempOfTmrw(AVG_TEMPERATURES)); // should be 79
```

**Notes:** At first I tried to destructure AVG_TEMPERATURES just as the task says. Since it didn't work, a look into the forum revealed I was supposed to destructe `avgTemperatures` (the parameter), rather than the global variable. It seems to be a bug in the challenge text which will be fixed soon (completed the challenge in June 2019).

### 13. Use Destructuring Assignment to Assign Variables from Nested Objects

Use destructuring assignment to obtain `max` of `forecast.tomorrow` and assign it to `maxOfTomorrow`.

**My Solution:**
```javascript
const LOCAL_FORECAST = {
  today: { min: 72, max: 83 },
  tomorrow: { min: 73.3, max: 84.6 }
};

function getMaxOfTmrw(forecast) {
  "use strict";
  // change code below this line

  const { tomorrow: { max: maxOfTomorrow } } = forecast;
  // change code above this line

  return maxOfTomorrow;
}

console.log(getMaxOfTmrw(LOCAL_FORECAST)); // should be 84.6
```

### 14. Use Destructuring Assignment to Assign Variables from Arrays

Use destructuring assignment to swap the values of `a` and `b` so that `a` receives the value stored in `b`, and `b` receives the value stored in `a`.

**My Solution:**
```javascript
let a = 8, b = 6;
(() => {
  "use strict";
  // change code below this line
  [a, b] = [b, a];
  // change code above this line
})();
console.log(a); // should be 6
console.log(b); // should be 8
```

### 15. Use Destructuring Assignment with the Rest Operator to Reassign Array Elements

Use destructuring assignment with the rest operator to perform an effective `Array.prototype.slice()` so that `arr` is a sub-array of the original array `source` with the first two elements omitted.

**My Solution:**
```javascript
const source = [1,2,3,4,5,6,7,8,9,10];
function removeFirstTwo(list) {
  "use strict";
  // change code below this line
  const [a, b, ...arr] = list;
  // change code above this line
  return arr;
}
const arr = removeFirstTwo(source);
console.log(arr); // should be [3,4,5,6,7,8,9,10]
console.log(source); // should be [1,2,3,4,5,6,7,8,9,10];
```

### 16. Use Destructuring Assignment to Pass an Object as a Function's Parameters

Use destructuring assignment within the argument to the function `half` to send only `max` and `min` inside the function.

**My Solution:**
```javascript
const stats = {
  max: 56.78,
  standard_deviation: 4.34,
  median: 34.54,
  mode: 23.87,
  min: -0.75,
  average: 35.85
};
const half = (function() {
  "use strict"; // do not change this line
  // change code below this line
  return function half({ max, min }) {
    // use function argument destructuring
    return (stats.max + stats.min) / 2.0;
  };
  // change code above this line

})();
console.log(stats); // should be object
console.log(half(stats)); // should be 28.015
```

### 17. Create Strings using Template Literals

Use template literal syntax with backticks to display each entry of the `result` object's `failure` array. Each entry should be wrapped inside an li element with the class attribute `text-warning`, and listed within the `resultDisplayArray`.

**My Solution:**
```javascript

```
