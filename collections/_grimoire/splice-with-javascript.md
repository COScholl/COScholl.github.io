---
layout: grimoire
title: Splice Array Into Another JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
working with arrays
#### First Principles:
- splice() returns a new array with spliced values, and modifies the original array
- splice() can be used to start at an index and remove _n_ number of elements
- splice() can be used to add elements to replace elements that were removed, or simply to add elements starting at an index
#### using .splice() and .forEach() methods
```
const frankenSplice = (arr1, arr2, n) => {
  let cloneArr1 = [...arr1];
  let cloneArr2 = [...arr2];
  cloneArr1.forEach((elem, idx) => cloneArr2.splice(n + idx, 0, elem));

  return cloneArr2;
};
```

#### Why I had to learn this
I am currently working through JavaScript Data Structures and Algorithms certification
