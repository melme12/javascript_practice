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

```
