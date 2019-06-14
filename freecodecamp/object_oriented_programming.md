# Javascript Algorithms And Data Structures Certification (freeCodeCamp)

## [Object Oriented Programming](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/object-oriented-programming)

### 1. Create a Basic JavaScript Object

Create a `dog` object with `name` and `numLegs` properties, and set them to a string and a number, respectively.

**My Solution:**
```javascript
let dog = {
  name: 'Hasso',
  numLegs: 3
};
```

### 2. Use Dot Notation to Access the Properties of an Object

Print both `properties` of the `dog` object below to your console.

**My Solution:**
```javascript
let dog = {
  name: "Spot",
  numLegs: 4
};
// Add your code below this line

console.log(dog.name);
console.log(dog.numLegs);
```

### 3. Create a Method on an Object

Using the dog `object`, give it a method called `sayLegs`. The method should return the sentence "This dog has 4 legs.

**My Solution:**
```javascript
let dog = {
  name: "Spot",
  numLegs: 4,
  sayLegs: function() {
    return "This dog has " + dog.numLegs + " legs."
  }
};

dog.sayLegs();
```

### 4. Make Code More Reusable with the this Keyword

Modify the `dog.sayLegs` method to remove any references to `dog`. Use the `duck` example for guidance.

**My Solution:**
```javascript
let dog = {
  name: "Spot",
  numLegs: 4,
  sayLegs: function() {return "This dog has " + this.numLegs + " legs.";}
};

dog.sayLegs();
```

### 5. Define a Constructor Function

Create a `constructor`, `Dog`, with properties `name`, `color`, and `numLegs` that are set to a string, a string, and a number, respectively.

**My Solution:**
```javascript
function Dog () {
  this.name = "Hasso";
  this.color = "white";
  this.numLegs = 3;
}
```

### 6. Use a Constructor to Create Objects

Use the `Dog` constructor from the last lesson to create a new instance of `Dog`, assigning it to a variable `hound`.

**My Solution:**
```javascript
function Dog() {
  this.name = "Rupert";
  this.color = "brown";
  this.numLegs = 4;
}
// Add your code below this line

let hound = new Dog();
```

### 7. Extend Constructors to Receive Arguments

Create another `Dog` constructor. This time, set it up to take the parameters `name` and `color`, and have the property `numLegs` fixed at 4. Then create a new `Dog` saved in a variable `terrier`. Pass it two strings as arguments for the `name` and `color` properties.


**My Solution:**
```javascript
function Dog(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 4; // this script forces me to lie, only 3 legs for Hasso
}

let terrier = new Dog('Hasso', 'white');
```

### 8. Verify an Object's Constructor with instanceof

Create a new instance of the `House` constructor, calling it `myHouse` and passing a number of bedrooms. Then, use `instanceof` to verify that it is an instance of `House`.

**My Solution:**
```javascript
function House(numBedrooms) {
  this.numBedrooms = numBedrooms;
}

// Add your code below this line

let myHouse = new House(3);
myHouse instanceof House;
```

### 9. Understand Own Properties

Add the `own` properties of `canary` to the array `ownProps`.

**My Solution:**
```javascript
function Bird(name) {
  this.name = name;
  this.numLegs = 2;
}

let canary = new Bird("Tweety");
let ownProps = [];
// Add your code below this line

for (let property in canary) {
  if (canary.hasOwnProperty(property)) {
    ownProps.push(property);
  }
}
```

### 10. Use Prototype Properties to Reduce Duplicate Code

Add a `numLegs` property to the `prototype` of `Dog`.

**My Solution:**
```javascript
function Dog(name) {
  this.name = name;
}

Dog.prototype.numLegs = 4;

// Add your code above this line
let beagle = new Dog("Snoopy");
```

### 11. Iterate Over All Properties

Add all of the `own` properties of `beagle` to the array `ownProps`. Add all of the `prototype` properties of `Dog` to the array `prototypeProps`.

**My Solution:**
```javascript
function Dog(name) {
  this.name = name;
}

Dog.prototype.numLegs = 4;

let beagle = new Dog("Snoopy");

let ownProps = [];
let prototypeProps = [];

// Add your code below this line 

for (let property in beagle) {
  if (beagle.hasOwnProperty(property)) {
    ownProps.push(property);
  } else {
    prototypeProps.push(property);
  }
}
console.log(ownProps);
console.log(prototypeProps);
```

### 12. Understand the Constructor Property

Write a `joinDogFraternity` function that takes a `candidate` parameter and, using the `constructor` property, return `true` if the candidate is a `Dog`, otherwise return `false`.

**My Solution:**
```javascript
function Dog(name) {
  this.name = name;
}

// Add your code below this line
function joinDogFraternity(candidate) {
  if (candidate.constructor === Dog) {
    return true;
  } else {
    return false;
  }
}

```

### 13. Change the Prototype to a New Object

Add the property `numLegs` and the two methods `eat()` and `describe()` to the `prototype` of `Dog` by setting the `prototype` to a new object.

**My Solution:**
```javascript
function Dog(name) {
  this.name = name; 
}

Dog.prototype = {
  // Add your code below this line
  numLegs: 4,
  eat: function() {
    console.log("dog food");
  },
  describe: function() {
    console.log("Hello World!");
  }
};
```

### 14. Remember to Set the Constructor Property when Changing the Prototype

Define the `constructor` property on the `Dog` prototype.

**My Solution:**
```javascript
function Dog(name) {
  this.name = name; 
}

// Modify the code below this line
Dog.prototype = {
  constructor: Dog,
  numLegs: 2, 
  eat: function() {
    console.log("nom nom nom"); 
  }, 
  describe: function() {
    console.log("My name is " + this.name); 
  }
};
```

### 15. Understand Where an Object’s Prototype Comes From

Use `isPrototypeOf` to check the `prototype` of `beagle`.

**My Solution:**
```javascript
function Dog(name) {
  this.name = name;
}

let beagle = new Dog("Snoopy");

// Add your code below this line

Dog.prototype.isPrototypeOf(beagle);
```

### 16. Understand the Prototype Chain

Modify the code to show the correct prototype chain.

**My Solution:**
```javascript

```