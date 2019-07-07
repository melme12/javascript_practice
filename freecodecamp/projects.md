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
function convertToRoman(num) {
  var romanNums = [[1000, 'M'], [900, 'CM'], [500, 'D'], [400, 'CD'], [100, 'C'], [90, 'XC'], [50, 'L'], [40, 'XL'], [10, 'X'], [9, 'IX'], [5, 'V'], [4, 'IV'], [1, 'I']];

  if (num === 0) {
    return '';
  }
  for (var i = 0; i < romanNums.length; i++) {
    if (num >= romanNums[i][0]) {
      return romanNums[i][1] + convertToRoman(num - romanNums[i][0]);
    }
  }
}

convertToRoman(36);
```

### 3. Caesars Cipher

One of the simplest and most widely known ciphers is a `Caesar cipher`, also known as a `shift cipher`. In a `shift cipher` the meanings of the letters are shifted by some set amount.

A common modern use is the ROT13 cipher, where the values of the letters are shifted by 13 places. Thus 'A' ↔ 'N', 'B' ↔ 'O' and so on.

Write a function which takes a ROT13 encoded string as input and returns a decoded string.

All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on.

**My Solution:**
```javascript
function rot13(str) {
  
  const inputLetter = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
  const outputLetter = 'NOPQRSTUVWXYZABCDEFGHIJKLM';

  const LetterIndex = ( x => inputLetter.indexOf(x) );

  const translate = ( x => LetterIndex(x) > -1 ? outputLetter[LetterIndex(x)] : x );

  return str.split('').map(translate).join('');

}

rot13("SERR PBQR PNZC");
```
**Notes:** I tried to accomplish the ROT13 with regex first and pushing it to an array with an if statement. I would like to try this approach again.

### 4. Telephone Number Validator

Return `true` if the passed string looks like a valid US phone number.

The user may fill out the form field any way they choose as long as it has the format of a valid US number. The following are examples of valid formats for US numbers (refer to the tests below for other variants):

```javascript
555-555-5555
(555)555-5555
(555) 555-5555
555 555 5555
5555555555
1 555 555 5555
```

For this challenge you will be presented with a string such as `800-692-7753` or `8oo-six427676;laskdjf`. Your job is to validate or reject the US phone number based on any combination of the formats provided above. The area code is required. If the country code is provided, you must confirm that the country code is `1`. Return `true` if the string is a valid US phone number; otherwise return `false`.

**My Solution:**
```javascript

```
