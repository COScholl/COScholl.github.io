---
layout: grimoire
title: Find Longest Word in a String with JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
Sorting through data to find largest value
#### First Principles:
* JavaScript has a `.sort()` method (https://tc39.es/ecma262/#sec-array.prototype.sort) that can called on an array, and optionally can take a comparator, where the difference of two items' values are compared
* Only the greater value ever need be saved to memory
#### Solutions
##### .sort() method
```
const longestWordLen(str) {
  const strArr = str.split(' ');
  const sortedArr = strArr.sort((a, b) => b.length - a.length);

  return sortedArr[0].length;
};
```
##### .forEach()/loop method
```
const longestWordLen(str) {
  let strArr = str.split(' ');
  let longestStr = '';
  strArr.forEach((str) => {
    longestStr = longestStr.length > str.length ? longestStr : str;
  })

  /*
  alternately:

  for (let i = 0; i <= strArr.length -1; i++) {
    longestStr = longestStr.length > strArr[i].length ? longestStr : strArr[i];
  }
  */

  return longestStr.length;
};
```
##### Reduce Method
```
const factorial = (num) => {
  let strArr = str.split(' ');
  const retStr = strArr.reduce((longestStr = '', currStr) => {
    return longestStr.length > currStr.length ? longestStr : currStr;
  }, '');

  return retStr.length;
}
```
#### Why I had to learn this
Algorithm study
