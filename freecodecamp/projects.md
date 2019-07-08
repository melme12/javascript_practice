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
function telephoneCheck(str) {

  let regex = /^(1\s*)*(\d{3}(\s|\-)*|\(\d{3}\)(\s)*)\d{3}(\s|\-)*\d{4}$/;

  return regex.test(str);
}

telephoneCheck("555-555-5555");
```
**Notes:** I found [Regex Pal](https://www.regexpal.com) when looking for regex and it's magic!

### 5. Cash Register

Design a cash register drawer function `checkCashRegister()` that accepts purchase price as the first argument (`price`), payment as the second argument (`cash`), and cash-in-drawer (`cid`) as the third argument.

`cid` is a 2D array listing available currency.

The `checkCashRegister()` function should always return an object with a `status` key and a `change` key.

Return `{status: "INSUFFICIENT_FUNDS", change: []}` if cash-in-drawer is less than the change due, or if you cannot return the exact change.

Return `{status: "CLOSED", change: [...]}` with cash-in-drawer as the value for the key change if it is equal to the `change` due.

Otherwise, return `{status: "OPEN", change: [...]}`, with the change due in coins and bills, sorted in highest to lowest order, as the value of the `change` key.

**My Solution:**
```javascript
function checkCashRegister(price, cash, cid) {
  
  // what and how much is in the drawer?
  const drawer = [
    {
      name: 'HUNDRED',
      value: 100,
      total: cid[8][1],
      amount: (cid[8][1] / 100).toFixed(2)
    },
    {
      name: 'TWENTY',
      value: 20,
      total: cid[7][1],
      amount: (cid[7][1] / 20).toFixed(2)
    },
    {
      name: 'TEN',
      value: 10,
      total: cid[6][1],
      amount: (cid[6][1] / 10).toFixed(2)
    },
    {
      name: 'FIVE',
      value: 5,
      total: cid[5][1],
      amount: (cid[5][1] / 5).toFixed(2)
    },
    {
      name: 'ONE',
      value: 1,
      total: cid[4][1],
      amount: (cid[4][1]).toFixed(2)
    },    
    {
      name: 'QUARTER',
      value: 0.25,
      total: cid[3][1],
      amount: (cid[3][1] / 0.25).toFixed(2)
    },
    {
      name: 'DIME',
      value: 0.1,
      total: cid[2][1],
      amount: (cid[2][1] / 0.1).toFixed(2)
    },
    {
      name: 'NICKEL',
      value: 0.10,
      total: cid[1][1],
      amount: (cid[1][1] / 0.05).toFixed(2) //.toFixed()?
    },
    {
      name: 'PENNY',
      value: 0.01,
      total: cid[0][1],
      amount: (cid[0][1] / 0.01).toFixed(2)
    }
  ];

  // Total amount in the register
  const registerTotal = drawer.reduce(function (total, currentValue) { return total + currentValue.total; }, 0).toFixed(2);

  // Amount of change needed
  const changeNeeded = parseFloat(cash - price).toFixed(2);

  // Empty Register Status Form
  let cashRegister = { status: '', change: 'hello' };
  
  // Register Status
  const registerStatus = { closed: 'CLOSED', insufficientFunds: 'INSUFFICIENT_FUNDS', open: 'OPEN' };

  //this sets the status
  cashRegister.status = setRegisterStatus(changeNeeded, registerTotal);
  function setRegisterStatus(changeNeeded, registerTotal) {
    if (Number(changeNeeded) > Number(registerTotal)) {
      return registerStatus.insufficientFunds;
    }
    if (Number(changeNeeded) < Number(registerTotal)) {
      return registerStatus.open;
    } 
    return registerStatus.closed;
  }
 
  //this sets an empty array for insufficient funds and returns it
  if (cashRegister.status === registerStatus.insufficientFunds) {
    cashRegister.change = [];
    return cashRegister;
  }

  //get Change
  cashRegister.change = getCustomersChange(changeNeeded, cid);

  function getCustomersChange(changeNeeded, changeInDrawer) {
    let change = [];

    for (let i = 0; i < changeInDrawer.length; i++) {
      const coinName = drawer[i].name;
      const coinValue = drawer[i].value;
      let coinAmount = drawer[i].amount;

      let coinsToReturn = 0;

      while (changeNeeded >= coinValue && coinAmount > 0) {
        changeNeeded -= coinValue;
        changeNeeded = changeNeeded.toFixed(2);
        coinAmount--;
        coinsToReturn++;
      }

      if (coinsToReturn > 0) {
        change.push([coinName, (coinsToReturn * coinValue)]);
      }
    }
    return change;  
  }

  // Total amount in the register
  function getTotalCashRegisterChange(changeInDrawer) {
    let total = 0;
    for (let x of changeInDrawer) {
      total += x[1];
    }
    return total.toFixed(2);
  };

  if (changeNeeded > getTotalCashRegisterChange(cashRegister.change)) {
    cashRegister.status = registerStatus.insufficientFunds;
    cashRegister.change = [];
  }

  if (cashRegister.status === registerStatus.closed) {
    cashRegister.change = [...cid];
  }

  return cashRegister;
}

checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]);
```
**Notes:** This challenge took me two days, it was HARD. I read all I could find about it, until I found a way that worked for me.

And in the end: [https://twitter.com/Peter_shirley/status/1147273341461356544?s=20](https://twitter.com/Peter_shirley/status/1147273341461356544?s=20)
