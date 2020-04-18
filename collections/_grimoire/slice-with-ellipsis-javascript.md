---
layout: grimoire
title: Slice Words by Number with Ellipsis JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
manipulating strings
#### First Principles:
- slice() extracts a given number of starting at an index (inclusive) and ending at an index (exclusive) elements and returns a new array
#### Using for loop
```
const truncateString = (str, num) => {
  const cloneStr = str;
  let retStr = '';
  if (num < str.length) {
    const ellipsis = '...';
    retStr = cloneStr.slice(0, num) + ellipsis;
    console.log(retStr)
  } else {
    retStr = cloneStr;
  }

  return retStr;
};
```

#### Why I had to learn this
I am currently working through JavaScript Data Structures and Algorithms certification
