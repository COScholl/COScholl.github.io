---
layout: grimoire
title: New Prototype Method Declaration
technologies: JavaScript
subject: Object Oriented Programming
tagline: Sometimes the old ways are better
---

#### Use Case:
Making a function that takes a string into a String.prototype method

#### First Principles:
- Built-in JavaScript primitives are still objects that have methods
- All objects' methods can be modified
- New properties and methods can be added to objects
- Arrow functions do not have their own `this`, `arguments`, `super`, or `new.target`
- Arrow functions take `this` from their enclosing lexical context
- Arrow functions are not suitable for methods, and they cannot be used as constructors
- A method defined with an arrow function will return global scope when `this` is called
- Function declarations that are not arrow functions define their own `this`
- A method defined with a function declaration (`{ foo: function() { return this; } }`) or shorthand syntax (`{ foo() { return this; } }`) will return `this` from the object scope to which the method belongs

##### Example
Create a function that operates on a string to reverse the characters of that string.
```
const reverse = (str) => str.split('').reverse().join('');

reverse('abc'); // "cba"
```
Make this function into a method of String.prototype
```
String.prototype.reverse = function() {return reverse(this.valueOf());}

'abc'.reverse(); // "cba"
```

Direct Method definitions:
`<object>.<property> = ...`:
```
String.prototype.reverse = function() { return this.valueOf().split('').reverse().join(''); }
```
`Object.assign`:
```
Object.assign(
  String.prototype,
  {
    reverse: function() { return this.valueOf().split('').reverse().join(''); }
  }
);
```
`Object.defineProperty`:
```
Object.defineProperty(String.prototype, 'reverse', {
  reverse: function() { return this.valueOf().split('').reverse().join(''); }
});
```

#### Why I had to learn this
This was something that I saw recently while studying for code challenges. It fits with study of classes from last week.

#### Sources
https://dmitripavlutin.com/when-not-to-use-arrow-functions-in-javascript/
