---
layout: grimoire
title: Number Factorial with JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
Factorialize a number (_n_!) to count permutations
#### First Principles:
* factorials are defined as _n_! is the product of every positive integer less than or equal to _n_:
```
_n_! = _n_ x (_n_- 1) x (_n_- 2) x (_n_- 3) x ... x 3 x 2 x 1.
```
#### Solutions
##### Loop method
```
const factorial = (num) => {
  if (num <= 0) return 1;

  let factNum = 1;
  for(let i = num; i > 0; i--) {
    factNum *= i;
  }

  return factNum;
}
```
##### Recursive method
```
const factorial = (num) => {
  if (num <= 0) return 1;

  return factorial(num - 1) * num;
}
```
#### Why I had to learn this
Algorithm study
