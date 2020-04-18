---
layout: grimoire
title: Object Oriented Programming and JavaScript
technologies: JavaScript
subject: Object Oriented Programming
tagline: classes
---

#### Use Case:

#### First Principles:
"JavaScript is a scripting language created by Brendan Eich at Netscape that supports Prototype-Based Programming, Object-Oriented Programming, and Functional Programming. It was originally called LiveScript, but the name was changed to JavaScript for marketing reasons... There is now a standardized version, EcmaScript [http://www.ecma-international.org/]. " -https://wiki.c2.com/?JavaScript

- JavaScript is a programming language
- JavaScript is an Object-Oriented Programming language

  - JavaScript does not have classes in the sense of many compiled languages, but features prototypes as a means of class inheritance from parent objects to child objects

- JavaScript is a scripting language


##### Closures
A closure in JavaScript is essentially the concept that functions have access to references to their surrounding state. So, when a function is created, it has its own internal properties, and it can use properties from its parent scope. A closure is the combination of lexical scoping and function creation.

In some other programming languages, the local variables within a function exist only as long as the function needs them at execution.

"Closures are useful in that they let you associate data (the lexical environment) with a function that operates on that data." -https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

JavasScript does not offer private methods with its classes. In some languages, you can declare methods as private. When a private methods is declared, only other methods in the same class can call the private methods. Private methods restrict access to code and manage global namespace. Closures can be used to emulate private methods using the Module Design Pattern.

##### The Module Design Pattern
The Module Design Pattern means instantiating a function as an Immediately Invoked Function Expression, in which variables are "privately" bound to the scope within the function body, and are only accessible from the methods that are returned by the function.

#### Classes
"A class is an abstract data type. It describes a family of objects that have the same set of methods and properties. It also defines these properties and methods... An instance is the instantiation of a class. It is one of the members of the family that the class represents.

JavaScript, being a prototype-based language, does not distinguish between classes and instances. It has only objects, which are similar to instances. An object is a real, particular entity... Any object can also specify its own properties and methods, adding or overriding its existing ones."
-http://webreference.com/js/tips/010215.html

JavaScript is not truly a class-based language in the vein of Java, but a prototype-based language that uses class syntax. The difference is that objects in a protoype-based language are cloned and extended, and there is no class definition separate from the constructor. A constructor function is the class definition, and will create a new object with all of the properties that are defined within the constructor. A new instance of a class inherits its properties from the class as a prototype of the class, extending the class with its own properties. A class in JavaScript is a member of the set of things that it defines.

A class-based language there is a distinction between the class and an instance of the class. The class definition defines constructors, which are used to instantiate a new instance of the class, whose properties are created at instantiation. A class is not part of the set of things that it defines.

JavaScript still uses class syntax in that it instantiates classes using the `new` keyword, and with ES6, offers the `class` keyword keyword for declaring classes without using a function declaration syntax and an `extends` keyword for automagically extending properties of the parent class into the child class.

https://en.wikipedia.org/wiki/Class-based_programming
https://en.wikipedia.org/wiki/Prototype-based_programming
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Details_of_the_Object_Model

##### Performance for creating class methods
When creating a new JavaScript class, it is more performant to add the method to the class prototype than to define the method in the class constructor.

```
ClassName.prototype.method = () => someThingToReturn;
```

#### Scripting languages
Scripting languages are programming languages that can be used within
Some general properties of scripting languages are:
- Source code is present at run time in a production system
- It is interpreted instead of compiled
- Explicit compilation is not needed
- Does not usually require type declaration
- Built in types
- Interface to the underlying operating system
- Can interface between other languages

https://wiki.c2.com/?ScriptingLanguage

#### Why I had to learn this
I am so tired of people disagreeing on what JavaScript is and isn't, while using buzzwords instead of examples. I hope to add to this as I learn more.
