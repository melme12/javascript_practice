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
