---
layout: grimoire
title: Create Vector from Array with JavaScript
technologies: JavaScript
subject: arrays
tagline: algorithm
---

#### Use Case:
working with arrays
#### First Principles:

#### using for loop
```
const chunkArrayInGroups = (arr, size) => {
  let arrClone = [...arr];
  const chunkSize = Math.floor(arr.length / size);
  let retVector = [];
  for (let i = 0; i < chunkSize; i++) {
    retVector.push(arrClone.slice(0, size));
    arrClone = arrClone.slice(size);
  }
  if (arrClone.length) retVector.push(arrClone);

  return retVector;
};
```
#### Recursive solution
```
const chunkArrayInGroups = (arr, size) => {
  if (arr.length <= size) return [arr];

  return [arr.slice(0, size)].concat(chunkArrayInGroups(arr.slice(size), size));
};
```
#### using .reduce() method
```
const chunkArrayInGroups = (arr, size) => {
  return arr.reduce((accum) => {
    let chunk = [arr.slice(0, size)];
    arr = arr.slice(size);

    return accum = chunk[0].length ? accum.concat(chunk) : accum;
  }, []);
};
```

#### Why I had to learn this
I am currently working through the Learn Regular Expressions section of the JavaScript Data Structures and Algorithms certification
