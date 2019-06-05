# Codewars: 8kyu

## Content

1. [Function 3 - multiplying two numbers](#function-multiply)
1. [Even or Odd](#even-odd)
1. [Multiply](#multiply)
1. [Transportation on vacation](#transportation)
1. [Simple Fun #1: Seats in Theater](#seats-theater)
1. [Opposite number](#opposite-number)
1. [Convert a Number to a String!](#convert-number-to-string)
1. [Abbreviate a Two Word Name](#abbreviate)
1. [Convert boolean values to strings 'Yes' or 'No'.](#convert-boolean-strings)
1. [Count of positives / sum of negatives](#count-positives-sum-negatives)
1. [Hello, Name or World!](#hello-name-or-world)
1. [Grasshopper - Personalized Message](#grasshopper)
1. [Basic Mathematical Operations](#basic-math-operations)
1. [Reversed sequence](#reversed-seq)
1. [get ascii value of character](#ascii-value)
1. [All Star Code Challenge #18](#allstar-code-18)
1. [101 Dalmatians - squash the bugs, not the dogs!](#bugs-dogs)
1. [Beginner - Lost Without a Map](#beginner-lost-map)
1. [Is he gonna survive?](#survive)
1. [Is this my tail?](#tail)
1. [Removing Elements](#removing-elements)
1. [Keep Hydrated!](#hydrated)

## Solutions

### <div id="function-multiply" />1. Function 3 - multiplying two numbers

**Details:**

This function has to be called multiply and needs to take two numbers as arguments, and has to return the multiplication of the two arguments.

**Solution:**
```javascript
function multiply (a, b) {
  return (a * b);
}
```

### <div id="even-odd" />2. Even or Odd

**Details:**

Create a function (or write a script in Shell) that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.

**Solution:**
```javascript
function even_or_odd(number) {
  if (number % 2 == 0) {
  return "Even";
  } else {
  return "Odd";
  }
}
```

### <div id="multiply" />3. Multiply

**Details:**

The code does not execute properly. Try to figure out why.

**Solution:**
```javascript
function multiply(a, b) {
  return (a * b);
}
```

### <div id="transportation" />4. Transportation on vacation

**Details:**

After a hard quarter in the office you decide to get some rest on a vacation. So you will book a flight for you and your girlfriend and try to leave all the mess behind you.

You will need a rental car in order for you to get around in your vacation. The manager of the car rental makes you some good offers.

Every day you rent the car costs $40. If you rent the car for 7 or more days, you get $50 off your total. Alternatively, if you rent the car for 3 or more days, you get $20 off your total.

Write a code that gives out the total amount for different days(d).


**Solution:**
```javascript
function rentalCarCost(d) {
  if (d >= 7) {
    return (d * 40 - 50);
  } else if (d >= 3) {
    return (d * 40 - 20);
  } else {
    return (d * 40);
  }
}
```

### <div id="seats-theater" />5. Simple Fun #1: Seats in Theater

**Details:**

Your friend advised you to see a new performance in the most popular theater in the city. He knows a lot about art and his advice is usually good, but not this time: the performance turned out to be awfully dull. It's so bad you want to sneak out, which is quite simple, especially since the exit is located right behind your row to the left. All you need to do is climb over your seat and make your way to the exit.

The main problem is your shyness: you're afraid that you'll end up blocking the view (even if only for a couple of seconds) of all the people who sit behind you and in your column or the columns to your left. To gain some courage, you decide to calculate the number of such people and see if you can possibly make it to the exit without disturbing too many people.

Given the total number of rows and columns in the theater (nRows and nCols, respectively), and the row and column you're sitting in, return the number of people who sit strictly behind you and in your column or to the left, assuming all seats are occupied.

**Solution:**
```javascript
function seatsInTheater(nCols, nRows, col, row) {
  //coding and coding..
  return (nCols - col + 1) * (nRows - row);
  
}
```

### <div id="opposite-number" />6. Opposite number

**Details:**

Very simple, given a number, find its opposite.

Examples:

```javascript
1: -1
14: -14
-34: 34
```

But can you do it in 1 line of code and without any conditionals?

**Solution:**
```javascript
function opposite(number) {
  return (number * -1);
}
```

### <div id="convert-number-to-string" />7. Convert a Number to a String!

**Details:**

We need a function that can transform a number into a string. What ways of achieving this do you know?

**Solution:**
```javascript
function numberToString(num) {
  return num.toString();
}
```

### <div id="abbreviate" />8. Abbreviate a Two Word Name

**Details:**

Write a function to convert a name into initials. This kata strictly takes two words with one space in between them.
The output should be two capital letters with a dot seperating them.

It should look like this:

Sam Harris => S.H

Patrick Feeney => P.F

**Solution:**
```javascript
function abbrevName(name){
  var nam = name.split(' ');
  return nam[0].charAt(0).toUpperCase()+'.' + nam[1].charAt(0).toUpperCase();
}
```

### <div id="convert-boolean-strings" />9. Convert boolean values to strings 'Yes' or 'No'.

**Details:**

Complete the method that takes a boolean value and return a `"Yes"` string for `true`, or a `"No"` string for `false`.

**Solution:**
```javascript
function boolToWord(bool){
  if (bool == true) {
  return "Yes";
  } else {
  return "No";
  }
}
```

### <div id="count-positives-sum-negatives" />10. Count of positives / sum of negatives

**Details:**

Given an array of integers.
Return an array, where the first element is the count of positives numbers and the second element is sum of negative numbers.
If the input array is empty or null, return an empty array.

**Solution:**
```javascript
function countPositivesSumNegatives(input) {
    if (input === null || input.length === 0) {
        return [];
    }
    var finalArray = [0, 0];
    for (var i = 0; i < input.length; i++) {
      if (input[i] <= 0) {
        finalArray[1] += input[i];
      } else {
        finalArray[0] += 1;
        }
    }
    return finalArray;
}
```

### <div id="hello-name-or-world" />11. Hello, Name or World!

**Details:**

Define a method `hello` that `returns` "Hello, Name!" to a given `name`, or says Hello, World! if name is not given (or passed as an empty String).
Assuming that `name` is a `String` and it checks for user typos to return a name with a first capital letter (Xxxx).

**Solution:**
```javascript
function hello(name) {
if (name === "" || name == undefined) {
  return "Hello, World!";
  } else {
  return 'Hello, ' + name.charAt(0).toUpperCase() + name.slice(1).toLowerCase() + '!';
  }
}
```

### <div id="grasshopper" />12. Grasshopper - Personalized Message

**Details:**

Create a function that gives a personalized greeting. This function takes two parameters: `name` and `owner`.
Use conditionals to return the proper message:
======= case | return --- | --- name equals owner | 'Hello boss' otherwise | 'Hello guest'

**Solution:**
```javascript
function greet (name, owner) {  
  return (name === owner) ? "Hello boss" : "Hello guest";
}
```

### <div id="basic-math-operations" />13. Basic Mathematical Operations

**Details:**

Your task is to create a function that does four basic mathematical operations.
The function should take three arguments - operation(string/char), value1(number), value2(number).
The function should return result of numbers after applying the chosen operation.

**Solution:**
```javascript
function basicOp(operation, value1, value2) {
  switch(operation) {
    case "+":
    return (value1 + value2);
    break;
    case "-":
    return (value1 - value2);
    break;
    case "*":
    return (value1 * value2);
    break;
    case "/":
    return (value1 / value2);
    break;
    }
}
```

### <div id="reversed-seq" />14. Reversed sequence

**Details:**

Get the number n `(n>0)` to return the reversed sequence from n to 1.
Example : n=5 >> [5,4,3,2,1]

**Solution:**
```javascript
const reverseSeq = n => {
  var result = [];
  for (var i = n; i > 0; i--) {
    result.push(i);
    }
  return result;
}
```

### <div id="ascii-value" />15. get ascii value of character

**Details:**

get ascii value of character
write a function getASCII which inputs a character and returns the corresponding ascii value for that character. Example : getASCII('A') => 65

**Solution:**
```javascript
function getASCII(c){
  return c.charCodeAt(0);
}
```

### <div id="allstar-code-18" />16. All Star Code Challenge #18

**Details:**

This Kata is intended as a small challenge for my students
All Star Code Challenge #18
Create a function called that accepts 2 string arguments and returns an integer of the count of occurrences the 2nd argument is found in the first one.
If no occurrences can be found, a count of 0 should be returned.

**Solution:**
```javascript
function strCount(str, letter){  
  return (str.split(letter).length - 1);
}
```

### <div id="bugs-dogs" />17. 101 Dalmatians - squash the bugs, not the dogs!

**Details:**

Your friend has been out shopping for puppies (what a time to be alive!)... He arrives back with multiple dogs, and you simply do not know how to respond!
By repairing the function provided, you will find out exactly how you should respond, depending on the number of dogs he has.
The number of dogs will always be a number and there will always be at least 1 dog.

**Solution:**
```javascript
function howManyDalmatians(number) {
  var dogs = ["Hardly any", "More than a handful!", "Woah that's a lot of dogs!", "101 DALMATIANS!!!"];  
  var respond = number <= 10 ? dogs[0] : number <= 50 ? dogs[1] : number === 101 ? dogs[3] : dogs[2];  
  return respond;  
}
```

### <div id="beginner-lost-map" />18. Beginner - Lost Without a Map

**Details:**

Given an array of integers, return a new array with each value doubled.
For example:
`[1, 2, 3] --> [2, 4, 6]`
For the beginner, try to use the `map` method - it comes in very handy quite a lot so is a good one to know.

**Solution:**

```javascript
function maps(x){
  return x.map((item) => item * 2);
}
```

### <div id="survive" />19. Is he gonna survive?

**Details:**

A hero is on his way to the castle to complete his mission. However, he's been told that the castle is surrounded with a couple of powerful dragons! each dragon takes 2 bullets to be defeated, our hero has no idea how many bullets he should carry.. Assuming he's gonna grab a specific given number of bullets and move forward to fight another specific given number of dragons, will he survive?
Return True if yes, False otherwise :)

**Solution:**

```javascript
function hero(bullets, dragons){
  return bullets >= dragons * 2
}
```

### <div id="tail" />20. Is this my tail?

**Details:**

Some new animals have arrived at the zoo. The zoo keeper is concerned that perhaps the animals do not have the right tails. To help her, you must correct the broken function to make sure that the second argument (tail), is the same as the last letter of the first argument (body) - otherwise the tail wouldn't fit!
If the tail is right return true, else return false.
The arguments will always be strings, and normal letters.

**Solution:**

```javascript
function correctTail(body, tail) {
  var sub = body.substr(body.length - tail.length);
  if (sub === tail) {
    return true;
    } else {
      return false;
  }
}
```

### <div id="removing-elements" />21. Removing Elements

**Details:**

Take an array and remove every second element out of that array. Always keep the first element and start removing with the next element.

**Solution:**
```javascript
function removeEveryOther(arr){
  return arr.filter((x, i) => i % 2 === 0);
}
```

### <div id="removing-elements" />22. Keep Hydrated!

**Details:**

Nathan loves cycling.
Because Nathan knows it is important to stay hydrated, he drinks 0.5 litres of water per hour of cycling.
You get given the time in hours and you need to return the number of litres Nathan will drink, rounded to the smallest value.
For example:
time = 3 ----> litres = 1
time = 6.7---> litres = 3
time = 11.8--> litres = 5

**Solution:**
```javascript
function litres(time) {
  let litre = time * 0.5;
  return Math.floor(litre);
}
```
