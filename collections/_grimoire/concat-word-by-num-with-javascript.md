---
layout: grimoire
title: Concatenate Words by Number with JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
evaluating strings
#### First Principles:

#### Using for loop
```
const repeatStringNumTimes = (str, num) => {
  if (num <= 0) return '';
  let retStr = '';
  for (let i = num; i > 0; i--) retStr += str;

  return retStr;
};
```

#### Why I had to learn this
I am currently working through JavaScript Data Structures and Algorithms certification
