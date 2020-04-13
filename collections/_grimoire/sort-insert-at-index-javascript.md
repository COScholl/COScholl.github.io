---
layout: grimoire
title: Find Insert Index for Value JavaScript
technologies: JavaScript
subject: array manipulation
tagline: algorithm
---

#### Use Case:
working with arrays

#### First Principles:

#### using for loop
```
const getIndexToIns = (arr, num) => {
  const cloneArr = arr.sort((a, b) => a - b);
  let retNum = 0;
  if (cloneArr.includes(num)) return cloneArr.indexOf(num);
  if (num > cloneArr[cloneArr.length - 1]) return cloneArr.length;
  for (let i = 0; i < cloneArr.length; i++) {
    if (num > cloneArr[i - 1] && num < cloneArr[i]) {
      retNum = i;
    }
  }

  return retNum;
}
```

#### using .filter() method
```
const getIndexToIns = (arr, num) => {
  // filter all values that are not greater than num and get length
 return arr.filter((val) => num > val).length;
}
```
#### Things that I did not consider
Initially, I did not consider adding _num_ to the array and then sorting to find index. In retrospect, this seems like the most natural answer.

I had initally thought about how to reduce the number of elements after sorting, and I could have approached the problem with less complexity, since I initially conceived of something fairly complicated.

#### Why I had to learn this
I am currently working through the Learn Regular Expressions section of the JavaScript Data Structures and Algorithms certification
