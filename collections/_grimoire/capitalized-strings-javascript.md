---
layout: grimoire
title: Return Title Cased String JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
working with strings
#### First Principles:

#### Using .forEach() and .slice() with .toUpperCase() and .toLowerCase() methods
```
const titleCase = (str) => {
  const strArr = str.split(' ');
  const retArr = [];
  strArr.forEach((word) => {
    let initial = word;
    let final  = word;
    initial = initial.slice(0, 1).toUpperCase();
    final = final.slice(1).toLowerCase();
    retArr.push(initial + final);
  })

  return retArr.join(' ');
};
```
#### Using .map() and .slice() with .toUpperCase() and .toLowerCase() methods
```
const titleCase = (str) => {
  const strArr = str.toLowerCase().split(' ');
  const retArr = strArr.map((word) => {
    return (word.slice(0, 1).toUpperCase() + word.slice(1));
  }).join(' ');

  return retArr;
};
```
#### Using .charAt() and .subStr() and .map()
```
const titleCase = (str) => {
  return str.toLowerCase().split(' ').map((word) => {
    return (word.charAt(0).toUpperCase() + word.slice(1));
  }).join(' ');
};
```

#### Why I had to learn this
I am currently working through JavaScript Data Structures and Algorithms certification
