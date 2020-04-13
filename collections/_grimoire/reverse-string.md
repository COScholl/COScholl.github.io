---
layout: grimoire
title: Reverse Strings with JavaScript
technologies: JavaScript
subject: Algorithms
tagline: algorithm
---

#### Use Case:
Is there a use case other than wordplay?
#### First Principles:
* Strings and arrays are index-based data structures
* Strings are immutable
* Arrays are mutable
* Strings can be made into arrays with the `.split()` method, using `''` as a separator
* Arrays have a `.reverse()` method to reverse arrays in place:
```    
-	Let O be ? ToObject(this value).
- Let len be ? LengthOfArrayLike(O).
- Let middle be floor(len / 2).
- Let lower be 0.
- Repeat, while lower ≠ middle

  -  Let upper be len - lower - 1.
  -  Let upperP be ! ToString(upper).
  -  Let lowerP be ! ToString(lower).
  -  Let lowerExists be ? HasProperty(O, lowerP).
  -  If lowerExists is true, then

      -  Let lowerValue be ? Get(O, lowerP).

  -  Let upperExists be ? HasProperty(O, upperP).
  -  If upperExists is true, then

      -  Let upperValue be ? Get(O, upperP).

  -  If lowerExists is true and upperExists is true, then

      -  Perform ? Set(O, lowerP, upperValue, true).
      -  Perform ? Set(O, upperP, lowerValue, true).

  -  Else if lowerExists is false and upperExists is true, then

      -  Perform ? Set(O, lowerP, upperValue, true).
      -  Perform ? DeletePropertyOrThrow(O, upperP).

  -  Else if lowerExists is true and upperExists is false, then

      -  Perform ? DeletePropertyOrThrow(O, lowerP).
      -  Perform ? Set(O, upperP, lowerValue, true).

  -  Else,

			-	Assert: lowerExists and upperExists are both false.
      -  No action is required.

  -  Set lower to lower + 1.

- Return O.
```
* Arrays have a `.join()` method that is the opposite of `.split()` and also takes a separator to add in between the joined elements
* Strings have a `.substr()` method that takes <index> as an argument and returns a substring starting at the index of the original string provided as an argument
* Strings have a `charAt()` methods that takes <index> as an argument and returns the letter at the index argument provided

#### To Array and back to string
##### one-liner
`const reverseStr = (str) => str.split('').reverse().join('')`;
##### with loop
```
const reverseStr = (str) => {
	const strArr = str.split('');
	let revArr = [];
	for (let i = strArr.length; i >= 0; i--) {
		// loop iterator tied to degrading strArr
		revArr.push(strArr.pop());
	}

	return revArr.join('');
}
```

#### Looping over string backward and concatenate into new string
```
const reverseStr = (str) => {
  let newStr = '';
  for (let i = str.length -1; i >=0; i--) {
    newStr += str[i]
  }

  return newStr;
};
```
#### Recursive method
```
const reverseStr = (str) => {
  if (str === '')  return '';

  return reverseStr(str.substr(1)) + str.charAt(0);
};
```

#### Why I had to learn this
Algorithm study
