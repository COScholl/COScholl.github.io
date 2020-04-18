---
layout: grimoire
title: Return First Element of Array with Condition JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
working with arrays
#### First Principles:

#### Using for loop
```
const findElement = (arr, func) => {
  let num = 0;
  for(let i = 0; i < arr.length; i++) {
    if (func(arr[i])) {
      num = arr[i];
      break;
    }
    num = undefined;
  };

  return num;
}
```
#### Using .some() method
```
const findElement = (arr, func) => {
  let num = 0;
  arr.some((elem) => {
  return num = func(elem) ? elem : undefined;
  });

  return num;
}
```

#### Why I had to learn this
I am currently working through JavaScript Data Structures and Algorithms certification
