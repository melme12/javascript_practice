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
function Dog(name) {
  this.name = name;
}

let beagle = new Dog("Snoopy");

Dog.prototype.isPrototypeOf(beagle);  // => true

// Fix the code below so that it evaluates to true
Object.prototype.isPrototypeOf(Dog.prototype);
```

### 17. Use Inheritance So You Don't Repeat Yourself

The `eat` method is repeated in both `Cat` and `Bear`. Edit the code in the spirit of `DRY` by moving the `eat` method to the `Animal supertype`.

**My Solution:**
```javascript
function Cat(name) {
  this.name = name; 
}

Cat.prototype = {
  constructor: Cat, 
  eat: function() {
    console.log("nom nom nom");
  }
};

function Bear(name) {
  this.name = name; 
}

Bear.prototype = {
  constructor: Bear, 
  eat: function() {
    console.log("nom nom nom");
  }
};

function Animal() { }

Animal.prototype = {
  constructor: Animal,
  eat: function() {
    console.log("nom nom nom");
  }
};

Cat.prototype = {
  constructor: Cat
}

Bear.prototype = {
  constructor: Bear
}
```

### 18. Inherit Behaviors from a Supertype

Use `Object.create` to make two instances of `Animal` named `duck` and `beagle`.

**My Solution:**
```javascript
function Animal() { }

Animal.prototype = {
  constructor: Animal, 
  eat: function() {
    console.log("nom nom nom");
  }
};

// Add your code below this line

let duck = Object.create(Animal.prototype); // Change this line
let beagle = Object.create(Animal.prototype); // Change this line

duck.eat(); // Should print "nom nom nom"
beagle.eat(); // Should print "nom nom nom" 
```

### 19. Set the Child's Prototype to an Instance of the Parent

Modify the code so that instances of `Dog` inherit from `Animal`.

**My Solution:**
```javascript
function Animal() { }

Animal.prototype = {
  constructor: Animal,
  eat: function() {
    console.log("nom nom nom");
  }
};

function Dog() { }

// Add your code below this line

Dog.prototype = Object.create(Animal.prototype);
let beagle = new Dog();
beagle.eat();  // Should print "nom nom nom"
```

### 20. Reset an Inherited Constructor Property

Fix the code so `duck.constructor` and `beagle.constructor` return their respective constructors.

**My Solution:**
```javascript
function Animal() { }
function Bird() { }
function Dog() { }

Bird.prototype = Object.create(Animal.prototype);
Dog.prototype = Object.create(Animal.prototype);

// Add your code below this line
Bird.prototype.constructor = Bird;
Dog.prototype.constructor = Dog;

let duck = new Bird();
let beagle = new Dog();
```

### 21. Add Methods After Inheritance

Add all necessary code so the `Dog` object inherits from `Animal` and the `Dog's prototype` constructor is set to Dog. Then add a `bark()` method to the `Dog` object so that `beagle` can both `eat()` and `bark()`. The `bark()` method should print "Woof!" to the console.

**My Solution:**
```javascript
function Animal() { }
Animal.prototype.eat = function() { console.log("nom nom nom"); };

function Dog() { }

// Add your code below this line

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function() {
    console.log("Woof!");
}


// Add your code above this line

let beagle = new Dog();

beagle.eat(); // Should print "nom nom nom"
beagle.bark(); // Should print "Woof!"
```

### 22. Override Inherited Methods

Override the `fly()` method for `Penguin` so that it returns "Alas, this is a flightless bird."

**My Solution:**
```javascript
function Bird() { }

Bird.prototype.fly = function() { return "I am flying!"; };

function Penguin() { }
Penguin.prototype = Object.create(Bird.prototype);
Penguin.prototype.constructor = Penguin;

// Add your code below this line
Penguin.prototype.fly = function() {
    return "Alas, this is a flightless bird.";
}
// Add your code above this line

let penguin = new Penguin();
console.log(penguin.fly());
```

### 23. Use a Mixin to Add Common Behavior Between Unrelated Objects

Create a `mixin` named `glideMixin` that defines a method named `glide`. Then use the `glideMixin` to give both `bird` and `boat` the ability to glide.

**My Solution:**
```javascript
let bird = {
  name: "Donald",
  numLegs: 2
};

let boat = {
  name: "Warrior",
  type: "race-boat"
};

// Add your code below this line

let glideMixin = function(obj) {
    obj.glide = function() {
        console.log("Gliiiiiiiiiide");
    }
}

glideMixin(bird);
glideMixin(boat);
```

### 24. Use Closure to Protect Properties Within an Object from Being Modified Externally

Change how `weight` is declared in the `Bird` function so it is a private variable. Then, create a method `getWeight` that returns the value of `weight`.

**My Solution:**
```javascript

```
