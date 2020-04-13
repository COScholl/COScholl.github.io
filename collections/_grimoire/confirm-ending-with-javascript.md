---
layout: grimoire
title: Confirm Ending with JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
evaluating strings
#### First Principles:

#### Using .slice() method
```
const confirmEnding = (str, target) => {
  const cloneStr = str;
  const numFinals = target.length;
  const strFinals = cloneStr.slice(str.length - numFinals);

  return strFinals === target;
};
```
#### Using .substring() method
```
const confirmEnding = (str, target) => {
	const cloneStr = str;
  const numFinals = target.length;
	const strFinals = cloneStr.substring(str.length - numFinals);

  return strFinals === target;
};
```
#### Using .substr() method
```
const confirmEnding = (str, target) => {
	const cloneStr = str;
  const numFinals = target.length;
	const strFinals = cloneStr.substr(str.length - numFinals, numFinals);

  return strFinals === target;
};
```
#### Using .endsWith() method
```
const confirmEnding = (str, target) => {
	const cloneStr = str;

  return cloneStr.endsWith(target);
};
```
#### Why I had to learn this
I am currently working through the Learn Regular Expressions section of the JavaScript Data Structures and Algorithms certification
