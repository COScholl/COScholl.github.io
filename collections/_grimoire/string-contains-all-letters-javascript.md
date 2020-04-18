---
layout: grimoire
title: String Has All Letters in Another With JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
working with strings
#### First Principles:

#### using Set and .filter() methods
```
const mutation = (arr) => {
  const firstSet = [...new Set(arr[0].toLowerCase().split(''))];
  const secondSet = [...new Set(arr[1].toLowerCase().split(''))];
  if (firstSet.length < secondSet.length) return false;
  const checkArr = secondSet.filter((elem) => !firstSet.includes(elem));

  return !checkArr.length;
};
```

#### Why I had to learn this
I am currently working through JavaScript Data Structures and Algorithms certification
