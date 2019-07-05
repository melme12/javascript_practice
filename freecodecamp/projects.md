# Javascript Algorithms And Data Structures Certification (freeCodeCamp)

## [JavaScript Algorithms and Data Structures Projects](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/javascript-algorithms-and-data-structures-projects)

### 1. Palindrome Checker

Return `true` if the given string is a palindrome. Otherwise, return `false`.

A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.

**Note**
You'll need to remove all **non-alphanumeric characters** (punctuation, spaces and symbols) and turn everything into the same case (lower or upper case) in order to check for palindromes.

We'll pass strings with varying formats, such as `"racecar"`, `"RaceCar"`, and `"race CAR"` among others.

We'll also pass strings with special symbols, such as `"2A3*3a2"`, `"2A3 3a2"`, and `"2_A3*3#A2"`.

**My Solution:**
```javascript
function palindrome(str) {
  let updatedStr = str.toLowerCase().replace(/[^A-Za-z0-9]/g, '');
  let reverseString = updatedStr.split("").reverse().join("");
  
  if (updatedStr === reverseString) {
    return true;
  } else {
    return false;
  }
}

palindrome("eye");
```

### 2. Roman Numeral Converter

Convert the given number into a roman numeral.

All roman numerals answers should be provided in upper-case.

**My Solution:**
```javascript

```

