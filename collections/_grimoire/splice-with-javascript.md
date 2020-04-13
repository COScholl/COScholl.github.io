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
I am currently working through the Learn Regular Expressions section of the JavaScript Data Structures and Algorithms certification
