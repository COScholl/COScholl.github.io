---
layout: grimoire
title: String Has All Letters in Another With JavaScript
technologies: JavaScript
subject: Object Oriented Programming
tagline: classes
---

#### Use Case:

#### First Principles:

#### Differences between old constructors and new constructors
Class constructors are at heart functions that create objects.
```
function Bird(name = "Albert", color = "blue") {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}
```
The following is syntactic sugar around what is essentially the function above:
```
class Bird {
  constructor(name = "Albert", color = "blue") {
    this.name = name;
    this.color = color;
    this.numLegs = 2;
  }
}
```
#### How to use classes
An instance of a class must be declared and assigned to a variable in order to see the object created by the class constructor.
```
let albert = new Bird;
let sammy = new Bird("Sammy", "brown");
console.log(albert); // { name: 'Albert', color: 'blue', numLegs: 2 }
console.log(sammy); // { name: 'Sammy', color: 'brown', numLegs: 2 }
```
The resultant object can have its properties reassigned, as with any other object.
```
sammy.name = "Sam";
console.log(sammy); // { name: 'Sam', color: 'brown', numLegs: 2 }
```
#### Checking object is instance of the class
```
let crow = new Bird("Alexis", "black");
console.log(crow instanceof Bird); // true
```
#### Instances of classes are objects, and have Object methods
```
console.log(typeof crow); // object
// Object.hasOwnProperty(<property>) returns true or false for Object.property
let ownProps = [];

for(let property in canary) {
  crow.hasOwnProperty(property) ? ownProps.push(property) : ownProps;
}

console.log(ownProps); // [ 'name', 'color', 'numLegs' ]
```
#### There is a distinction to be made between prototype properties for the class and properties of the class instance object
```
class Bird {
  constructor(name = "Albert", color = "blue") {
    this.name = name;
    this.color = color;
  }
}

Bird.prototype.numLegs = 2;

let albatross = new Bird('Franklin', 'white');

console.log(albatross.name); // Franklin
console.log(albatross.color); // white
console.log(albatross.numLegs); // 2

console.log(albatross.hasOwnProperty('name')); // true
console.log(albatross.hasOwnProperty('color')); // true
console.log(albatross.hasOwnProperty('numLegs')); // false

console.log(Bird.prototype.hasOwnProperty('name')); // false
console.log(Bird.prototype.hasOwnProperty('color')); // false
console.log(Bird.prototype.hasOwnProperty('numLegs')); // true

console.log(Bird.prototype.name); // undefined
console.log(Bird.prototype.color); // undefined
console.log(Bird.prototype.numLegs); // 2
```
#### Iterate over all properties (from object and prototype)
```
let crow = new Bird("Alexis", "black");
console.log(typeof crow); // object
// Object.hasOwnProperty(<property>) returns true or false for Object.property
// prototype properties are still properties of the object, just not own properties.
let ownProps = [];
let prototypeProps = [];
for(let property in crow) {
  crow.hasOwnProperty(property)
    ? ownProps.push(property)
    : prototypeProps.push(property);
}
```
#### Understand constructor
The constructor is the function that defines the class.
Remember:
```
class Dog {
  constructor(name) {
    this.name = name;
  }
}
let pomeranian = new Dog('Dawg');
console.log(pomeranian.constructor); // [Function: Dog]
```
is the same as:
```
function Dog(name) {
  this.name = name;
}
let pomeranian = new Dog('Dawg');
console.log(pomeranian.constructor); // [Function: Dog]
```
The constructor equals the class name:
```
const joinDogFraternity = (candidate) => {
  return candidate.constructor === Dog ? true : false;
};
console.log(joinDogFraternity(pomeranian)); // true
```
#### Adding prototype properties to class _en masse_
One can assign an object to prototype for a class with all the properties intended for the class, all at once. However, this object will overwrite the `constructor` property, so it is important to add the constructor.
Adding properties one at a time will not replace the prototype object, so this method is fundamentally different.
```
class Dog {
  constructor(name) {
    this.name = name;
  }
}

Dog.prototype = {
  constructor: Dog,
  numLegs: 4,
  eat: () => {
    console.log("nom nom nom");
  },
  describe: () => {
    console.log("My name is " + this.name);
  }
}
```
#### .isPrototypeOf()
Just as the constructor indicates what class originates an object, that is the class object inherits the prototype of the class that defines it, the method `.isPrototypeOf()` can affirm the relationship of the constructed class to the class definition.
```
Dog.prototype.isPrototypeOf(pomeranian);
```
#### Object is the supertype for all classes and class prototypes
Object is the supertype for class, as class is the supertype of the class instance that it creates. This means that class and class instances inherit the .hasOwnProperty() method, and that .isPrototypeOf() can be used to show the chain of inheritance.
```
Object.prototype.isPrototypeOf(Dog.prototype);
Dog.prototype.isPrototypeOf(pomeranian);
```
#### Create a supertype
Create a class and then add the method or property that you want to see inherited by all the prototypes that follow:
```
// place supertype class above prototype classes in code base
function Animal() { }

Animal.prototype = {
    constructor: Animal,
    eat: () => console.log('nom nom nom')
};
```
Or;
```
// place supertype class above prototype classes in code base
class Animal {
  constructor() { }
}

Animal.prototype.eat = () => console.log('nom nom nom');

class Dog {
  constructor(name) {
    this.name = name;
  }
}
```
Then make an instance of the supertype:
```
let animal = new Animal();
```
Or the preferred method:
```
// create new object (Animal.prototype), and set Animal.prototype as the new object's prototype
let animal = Object.create(Animal.prototype);
```
Which can be extended make a class a prototype of the new supertype:
```
// Add to code base after `class Dog { constructor() { } }`
Dog.prototype = Object.create(Animal.prototype);
```
Finally, redefine constructor for prototypes of supertype to have their own constructors
```
Dog.prototype.constructor = Dog // otherwise, would be [Function: Animal]
```
This is the prototype chain.
```
class Animal{ constructor() { } };
Animal.prototype.eat = () => console.log("nom nom nom");

class Dog { constructor() { } };
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;
Dog.prototype.bark = () => console.log('Woof!');

let beagle = new Dog();
beagle.eat(); // nom nom nom
beagle.bark(); // Woof!
```
Properties inherited from the parent object can be overwritten
#### Mixins
'...[A] mixin is a class that contains methods for use by other classes without having to be the parent class for those other classes.' - https://en.wikipedia.org/wiki/Mixin

One method is create a wrapper function that adds the property to any instance of a class or object being passed in.
```
let flyMixin = (obj) => {
  obj.fly = () => console.log('I'm flying!');
};

flyMixin(classInstance);
```
Otherwise, a mixin could be an object with properties and methods that can be copied into the class or object using Object.assign(_target_, _source_).
```
let flyMixin = { fly: () => console.log('I'm flying!') };

Object.assign(classInstance, flyMixin);
```
#### Closures and protecting properties
When a property is declared in a constructor with `this`, it is available by making a direct call to that property. When a variable is declared in the constructor, however, that is private. Any method that is instantiated to return that variable would be privileged.
```
class Bird {
  constructor() {
    let secret = 'Only my flock may know';
    let password = 'password123';
    this.revealSecret = (psswd) => (psswd === password) ? console.log(secret) : console.log('...');
  }
}

let sparrow = new Bird();
sparrow.revealSecret('password123'); // Only my flock may know
sparrow.revealSecret('tell me your secret!'); // ...
```
#### Immediately Invoked Function Expression
```
(() => console.log('A cozy nest is ready'))()
```
Or
```
(function (){
    console.log('A cozy nest is ready');
})()
```
IIFE for mixins:
```
let mixinModule = (() => {
  return {
    isCuteMixin: (obj) => {
      obj.isCute = () => true;
    },
    singMixin: (obj) => {
      obj.sing = () => console.log("Singing to an awesome tune");
    }
  }
})();

class Bird {
  constructor() { }
}

let sparrow = new Bird();

mixinModule.isCuteMixin(sparrow);
console.log(sparrow.isCute()); // true
```
#### Why I had to learn this
I am currently working through the Learn Regular Expressions section of the JavaScript Data Structures and Algorithms certification
