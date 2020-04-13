---
layout: grimoire
title: Regular Expressions with JavaScript
technologies: JavaScript
subject: Regular Expressions
tagline: Flags
---

#### Use Case:
search patterns for strings
#### First Principles:
* the term _regular expressions_ is meant to indicate a standard textual syntax for representing patterns for matching text
* regular expressions, or _regexes_, can match string literals, and can use _metacharacters_ that add other rules for matching string literals
* regular expressions can be formally defined using set theory
	* see https://en.wikipedia.org/wiki/Regular_expression, _Formal language theory_
* the syntax for regular expressions is `/\<pattern>/\<modifiers>`
* regular expressions in JavaScript are objects, and can be also created with a class constructor using the `new RegExp('<pattern>', '<modifier>')` expression, or `new RegExp('/<pattern>/', '<modifier>')`, as well as assigning `/<pattern>/<modifiers>` to a variable
* the resulting RegExp object has methods that we can use to test our strings with
* strings that we want to test against regular expressions using JavaScript are piped into the test via these methods
```
let string = 'some string';
let regEx = /<pattern>/<modifiers>;
let otherRegex =  new RegExp('<pattern>', '<modifier>');
let test = regEx.test(string);
```
* other methods take the regular expressions as an input and are called on the string itself
```
let string = 'some string';
let regEx = /\<pattern>/\<modifiers>;
let otherRegex =  new RegExp('\<pattern>', '\<modifier>');
let match = string.match(regEx);
```
#### Intro to Regular Expressions
```
"Some people, when confronted with a problem, think ‘I know, I’ll use regular expressions.’ Now they have two problems." -Jamie Zawinski
```

This quote appropriately found at the start of chapter 9 of <u>Eloquent JavaScript</u> by Marijn Haverbeke.
##### Lazy matching
Regex is _greedy_ by default. It finds the longest possible part of a string that fits the regex pattern and returns that.
Finds the smallest possible part of the string that satisfies the regex pattern. Uses the `*?` character.
##### Character Classes
* placed within square brackets

	* `^` - not; exclude all the characters that follow the caret
##### Metacharacters
* `.` - wildcard; match any one character
* `-` - range; match any character withing range [\<start> - \<end>] (inclusive)
* `^` - beginning of string \| not; outside of character class: find regex at beginning of a string (/^\<pattern>/) | inside of a character class: exclude all the characters that follow the caret (/[^\<pattern>]/)
* `$` - end of string; search end of string for regex pattern (/\<pattern>$/)
* `+` - one or more consecutive; character appears at least once, but may be repeated
* `*` - zero or more consecutive; character appears any number of times (or not at all)
* `*?` - lazy match; return the smallest possible part of a string that matches the pattern provided
* `\w` - match alphanumeric characters and underscore
* `\W` - match all characters other than alphanumeric characters and underscore
* `\d` - match all numeric characters
* `\D` - match all characters other than numeric characters
* `\s` - match all 'white space characters'; matches carriage return (`\r`), horizontal tab (`\t`), form feed (`\f`), new line (`\n`), and vertical tab (`\v`)
* `{min, max}` - return number of characters that match pattern between min and max number of characters (inclusive)
* `{num}` - return exact number of matches
* `?` - zero plus match; check for possible existence of a match
* `<string>(?=<following string>)`- positive lookahead; match \<string> only if followed by \<following string>
* `<string>(?!<following string>)`- negative lookahead; match \<string> only if not followed by \<following string>
* `(<expression 1>),(<expression 2>),(<expression 3>),...,(<expression n>) = $1,$2,$3,...,$n` - capture group; For each capture group _(\<expression n>)_, a stand-in representation _\n_ can be placed within a larger expression to represent the parenthetic expression so that the parenthetic expression does not need to be written out again. A replacement string can use the _$n_ variable to save the capture group and re-arrange it

##### Methods
* `<regex>.test(<string>)` - returns `true` or `false`; test for match in a string
* `<string>.match(<regex>)` - returns an array or object containing matches (different output depending on whether or not the 'g' flag is used) or `null`;

	* when `g` flag is used, outputs array with all matched string literals
	* when no flag is used, outputs an object with length property of `1` and with structure:
	```
	[
		<first complete match>,
		index: <index of input string where first complete match starts>,
		input: <complete input string>
	]
	```
		* \<output>[0] returns \<first complete match>
		* \<output>.index returns \<index of input string where first complete match starts>
		* \<output>.input returns \<complete input string>

* `<string>.replace(<regex>, <replacement string>)`
##### Flags
* `i` - "ignore case" (RegExp.prototype.ignoreCase)
* `g` - "global search (find more than one instance)" (RegExp.prototype.global)

#### Why I had to learn this
I am currently working through the Learn Regular Expressions section of the JavaScript Data Structures and Algorithms certification
