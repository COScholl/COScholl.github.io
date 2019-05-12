---
layout: grimoire
title: Array Methods, Vanilla and Lodash
technologies: Javascript, Lodash
subject: Basics and Cross-Browser compatability
tagline: Elements! Indices! Arrays! Go!
---

***This page is under threat of constant update, since I will be looking to describe and work with every array method that I can uncover with the docs. Last update was: 5/12/2019***

#### What is this page about?

I will be adding method after method for arrays in JavaScript, looking at browser support for each method, and comparing these vanilla JS methods (using ES6) to the library <a href="https://lodash.com/">Lodash</a>. This will be updated periodically as a long-term practice for staying fresh with basics and exploring the docs more fully at <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array"> MDN</a>.

#### What is an array in JavaScript?

Arrays are a type of JavaScript object, but they are considered <a href="https://tc39.github.io/ecma262/#exotic-object">*exotic objects*</a>, since the "semantics for accessing and manipulating their properties" differ from *ordinary objects*. The exotic semantics for accessing and manipulating array properties are focused around *property keys*. The property keys of an array are known as an index, and an <a href="https://tc39.github.io/ecma262/#array-index">*array index*</a> is an <a href="https://tc39.github.io/ecma262/#integer-index">*integer index*</a> whose "whose numeric value *i* is in the range *+0 ≤ i < 2<sup>32</sup> - 1*." This nonnegative range less than 2<sup>32</sup> is the value range of the non-configurable *length* property of an array. This length property increases and decreases as *elements* are added or removed from an array, and is always numerically greater than the highest index of the array. Elements are properties that have a property name that is an array index.


The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Syntax">syntax</a> of an array in JavaScript is [*element<sub>0</sub>*, *element<sub>1</sub>*, ... , *element<sub>n</sub>*]. Each element of the array has its index, starting at 0, and incrementing by 1 for every element in the array.

##### Short Version:

Arrays in JavaScript are objects, but they are unique objects, whose property keys are ordered indices, and have an order starting at index 0 and going up to index of 4,294,967,295. An array has a property of *length*, which is the total number of elements that are in the array. That means that an array can have a possible length of 0 (an empty array, with no elements), up to 4,294,967,296 (a maxxed-out array). If an array has one element, that element exists at index 0, and the array will have a length of 1.



#### Why did I have to learn this?

These are the basics, and it pays to sharpen the saw. Also, Lodash is a library that we use at work, and I need to familiarize myself with it, and how it differs from standard ES6 methods.