---
layout: grimoire
title: Find Largest Values in a Sub-Arrays with JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
Sorting through nested arrays
#### First Principles:
* Arrays a `.sort()` method (https://tc39.es/ecma262/#sec-array.prototype.sort) that can called on an array, and optionally can take a comparator, where the difference of two items' values are compared
* Arrays have a `.map()` method for recomposing array values

#### Solutions
##### .map and .sort() method
```
const largestOfArrays = (arr) => {
  const returnArr = arr.map((arr) => {
    arr.sort((a, b) => b - a);
    return arr[0];
  });

  return returnArr;
};
```

#### Why I had to learn this
Algorithm study
