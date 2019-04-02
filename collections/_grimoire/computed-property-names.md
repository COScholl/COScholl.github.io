---
layout: grimoire
title: Computed property names
technologies: Javascript
subject: Javascript object manipulation
tagline: What are those brackets for?
---

#### Use Case: 
manipulating properties and their values programatically
#### First Principles: 
* objects are collections of data
* objects are represented by curly braces 
	* `{}`
* an object is held in a computer's memory by tying the object to a *variable*
* a variable is a name that is declared by the keywords *const*, *let*, and *var* 
	* `let objectName = {};`
* objects contain information in the form of *values* that are accessed by identifiers called *properties*
	* `objectName = {
		property: 'value'
	};`
	* `console.log(objectName.property); // value`
* the variable that an object is bound to acts like an address to find the information in the object
* the two ways of calling the value of a property in an object are through *dot notation* and *bracket notation*
	* `objectName.propertyName`
	* `objectName['propertyName']`
* if a property that does not exist in the object is called on the object and given a value, it creates that property and value in the object

	* `objectName.anotherProperty = anotherValue;`
* when working with objects, it may be necessary to change these properties and values programatically
* in order to change properties and values without writing a new line of code for every property and value, *computed property names* can be used
* computed property names use variables wrapped in brackets to stand for properties so that they can be computed
	* `[variable]: 'value'`
* computed property names are new to JavaScript in the ES6 standard

#### Before Computed Property Names:
```
const key = 'propertyName';
const value = 'value';
const obj = {};
obj[key] = value;
console.log(obj); // {propertyName: 'value'}
```
The above as a function:
```
function giveObjValue(key, value) {
	const obj = {};
	obj[key] = value;
	return obj;
}
```

#### With Computed Property Names:
```
const key = 'propertyName';
const obj = {[key]: 'value'};
```
As a function:
```
function giveObjValue(key, value) {
	return {[key]: value};
}
```
#### Why Did I Have To Learn This?
I tried to create an anonymous function to take an array of two items and convert them into an object with the zeroeth index of the array as the property and the first index of the array as the value. Roughly, what I attempted to do was:

```
const array = ['zeroeth', 'first'];
const obj = {array[0]:array[1]}; // Uncaught SyntaxError: Unexpected token [
```
What I needed to do was:
```
const obj = {[array[0]]:array[1]}; // {zeroeth: "first"}
```
Later, I needed to take an array of objects where each object had two properties and reduce that array into one object where every property was the value of the the first property from the array objects, and had the value of the second property's value.

Let's break that sentence down:
* The array had multiple properties.
	* `[{...},{...},{...}]`
* Each object had two properties:
	* `{propertyOne: <value>, propertyTwo: <value>}`
* For each object in the array, propertyOne was the same, and propertyTwo was the same. The values that were held by these properties were different.
* The objects needed to be reduced into one object.
* The properties being reduced were the values of propertyOne, which were being given the values of propertyTwo.
* The result needed was one object with the reduced properties.
	* `const reduced = reduce(sorted, (accumulator, object) => (
	{[object.propertyOne]: object.propertyTwo, ...accumulator}
	), {});`