# Codewars: 7kyu

## Content

1. [String ends with?](#string-ends-with)

## Solutions

### <div id="string-ends-with" />1. String ends with?

**Details:**

Complete the solution so that it returns true if the first argument(string) passed in ends with the 2nd argument (also a string).

Examples:
```javascript
solution('abc', 'bc') // returns true
solution('abc', 'd') // returns false
```

**Solution:**
```javascript
function solution(str, ending){
  // TODO: complete
  var regex = new RegExp(ending + "$", 'gi');
  return regex.test(str);
}
```

**Notes:** This task is part of the [Codewars Chingu Challenges](https://www.codewars.com/collections/chingu-challenge).
