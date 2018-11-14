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

### <div id="hello-name-or-world" />11. Hello, Name or World!

### <div id="grasshopper" />12. Grasshopper - Personalized Message

### <div id="basic-math-operations" />13. Basic Mathematical Operations

### <div id="reversed-seq" />14. Reversed sequence

### <div id="ascii-value" />15. get ascii value of character

### <div id="allstar-code-18" />16. All Star Code Challenge #18

### <div id="bugs-dogs" />17. 101 Dalmatians - squash the bugs, not the dogs!

### <div id="beginner-lost-map" />18. Beginner - Lost Without a Map

### <div id="survive" />19. Is he gonna survive?

### <div id="tail" />20. Is this my tail?
