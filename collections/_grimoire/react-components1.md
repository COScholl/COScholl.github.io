---
layout: grimoire
title: React Elements and Components Without JSX
technologies: Javascript, ReactJS
subject: React basics
tagline: What exactly IS a React component
---

#### React: It's Got Market Share

In an article at <a 
href="https://www.techrepublic.com/article/programming-languages-javascript-developers-reveal-their-favorite-frameworks-platforms-and-tools/">Tech Republic</a> published today,
I read that 57% of JavaScript developers surveyed <a href="https://javascriptsurvey.com/">here</a> write React code. Of those who
do not, 15% are considering using React for future projects. React is easy to get up and running using `create-react-app`, and you can 
get immediate feedback on your local instance as you develop your application. This makes it an attractive library for developing. 

Now, I am not the sharpest tool in the shed, and when it comes to programming, I like for things to be consistent so that I can just focus on solving problems. The thing about React, its components, and JavaScript in general, is that things grow and change pretty quickly.  So, if you are like me, when you have a problem to solve, you go to Google or DuckDuckGo and hunt for examples. This means that if you have a React problem to solve, you might find React components written with ES5 or ES6 syntax, or, you might find JSX examples or React.createElement( ) methods. Now, this might not be a problem for you, but as a JavaScript and React novice, my inclination is to want specific guidelines to follow. But, guess what? No such luxury will be afforded, so, the only thing to do, is learn what a React component is, and the different ways to write components so that one can translate approaches to the way that they work.

#### Use Case: 

I am trying to solve a problem in React. I use different references, since some authors assume their audience knows certain things, and other authors assume other things of their audience. By cross-referencing a limited set of resources, it is easier to get context for a problem that might be presented in each of the resources. I am currently using the React docs online at <a href="https://reactjs.org/docs/">https://reactjs.org/docs/</a>, as well as *Learning React*{:.underlineTitle} by Eve Porcello and Alex Banks that I bought with a Humble Bundle. *Learning React*{:.underlineTitle} builds up a base of knowledge using React.createElement( ), and then teaches JSX in chapter 5. The React docs focus on JSX. When searching online for code that looks like a problem I am trying to solve, I might find code witten with or without JSX. Therefore, it will be useful to have a strong understanding of how React components work, and to be able to translate between different syntax.

#### First Principles
* <a name="what-is-react">**What is React?**</a> React is a library that updates the DOM for the programmer instead of working with the DOM API directly. With React, we build a set of instructions for React to create the *user interface*. This set of instructions is a *virtual DOM* made up of React elements. These React elements are JavaScript objects.
* <a name="what-is-a-react-element">**What is a React element?**</a> A React element is the smallest entity for building React applications. React elements are objects, and they describe what will be displayed on the screen. The *React DOM* library takes these React elements as instructions to update the DOM. React elements are *immutable*, so once the element is created, its state, or the state of its children, cannot be changed. To display a change to an element, the DOM would have to be re-rendered on change, which means there would need to be some way to manage the state of those changes.
* **An example of a React element**
	* ```
		React.createElement(
			"h1", 
			null, 
			"The Header Foo"
		);
		```
	* In the above example, the *React.createElement( )* method tells React DOM to instruct the DOM to build the element `<h1>The Header Foo</h1>`
	* The structure of the method's arguments are *(HTML element, element attributes, value of element to display)*
	* To create attributes for the element, the argument will be an object that uses the attribute as the property key, and its value will be the property value.
	* Example: 
```
		React.createElement(
			"h1", 
			{
				id: 'title', 
				style: {color: 'red'}
			},
			"The Header Foo"
		});
```
		or
		```<h1 id="title" style="color: red">The Header Foo</h1>```
* **What does the React Docs have to say about *React.createElement*?** 
	* ```
		React.createElement(
  			type,
  			[props],
  		 	[...children]
		 )
		```
	* Attributes are collectively called *props*, short for *properties*
	* My description of the `[...children]` argument was *value of element to display*, and here we see that it can mean all of the children elements of a given element.
		* Example:
```
			React.createElement(
				"ul",
				null,
				React.createElement("li", null, "foo"),
				React.createElement("li", null, "bar"),
				React.createElement("li", null, "baz"),
				React.createElement("li", null, "fizz"),
				React.createElement("li", null, "buzz")
			);
```
		* Every argument after *[props]* ends up in an array that React sets to the value `props.children` in the React element object that React uses to send instructions to React DOM
		* The resulting React element for the example above would look something like:
```
			{
				"type": "ul",
				"props": {
					"children": [
						{ "type": "li", "props": { "children": "foo" } ... },
						{ "type": "li", "props": { "children": "bar" } ... },
						{ "type": "li", "props": { "children": "baz" } ... },
						{ "type": "li", "props": { "children": "fizz" } ... },
						{ "type": "li", "props": { "children": "buzz" } ... },
					]
					...
				}
			}
```
* **Does it make sense to write a whole new element for each child in an element tree?** Not necessarily. The values for the children could come from an array and be mapped to each child.
	* <a name="map-children">Example<a>:
```
		const items = [
			"foo",
			"bar",
			"baz",
			"fizz",
			"buzz"
		];

		React.createElement(
			"ul",
			{className: "things"},
			items.map((thing, value) =>
			React.createElement("li", {key: value}, thing)
			)
		);
```
* **What about React Components?** Components are reusable code that define parts of the user interface (*UI*  ). A component is made of React elements, and is defined by its functionality, reusing the same DOM structure to display different data.
* **Three ways to create components**
	* the *createClass* function
	* ES6 classes
	* stateless functional components

	> 
	> React.createClass( ) has been deprecated since 2016.
	> To use this syntax, it is necessary to import a
	> separate library 'create-react-class' from npm or yarn.
	>

 * **createClass** The first means of programming a React component when it was introduced in 2013.
	* Example:
```
		const AllTheThings = React.createClass({
			displayName: "AllTheThings",
			render( ) {
				return React.createElement(
					"ul",
					null,
					React.createElement("li", null, "foo"),
					React.createElement("li", null, "bar"),
					React.createElement("li", null, "baz"),
					React.createElement("li", null, "fizz"),
					React.createElement("li", null, "buzz")
				);
			}
		});

		const list = React.createElement(AllTheThings, null, null);

		ReactDom.render(
			list,
			document.getElementById('react-container')
		)
```
	* From the example, we can see that React elements are the basic building block of React components. So much so, that a component is treated like an element itself for ReactDom to render. This is not suprising, since in JavaScript, a class is an object as well.

	* The property `displayName` sets a value that helps debug issues with your components. The default error messages will call your component `Component`. Chances are, there will be more than one component. Setting *displayName* will help to target the component that has issues.

		* The role of *displayName* with ES6 classes and with functional components is something that I will have to explore at another time.

	* Another way of approaching this problem is to re-write the class with all the element children values in an array, which are then mapped as children of the first element in the class, like in the previous <a href="#map-children">example</a>.
```
		const AllTheThings = React.createClass({
			displayName: "AllTheThings",
			render( ) {
				return React.createElement(
					"ul",
					{className: "things"},
					this.props.items.map((thing, value) =>
						React.createElement("li", {key: value}, thing)
					)
				);
			}
		});

		const items = [
			"foo",
			"bar",
			"baz",
			"fizz",
			"buzz"
		];

		const list = React.createElement(AllTheThings, { items }, null);

		ReactDom.render(
			list,
			document.getElementById('react-container')
		);
```
	* This example shows a few interesting things that need some clarification. 
		* The first is that  the array `items` is used as the props for the React element `list`. Since props are an object, the variable *items* is imported into *list* as `{ items }`.
		* The second thing to look at is how the class uses the array *items*. The ReactDom.render( ) calls `React.createElement(AllTheThings, { items }, null);` which is set to the variable *list*. The variable *list* is declared with props `{ items }`. Each of *items*, *list* and the class *AllTheThings* were declared with `const`, so their scopes are not shared with the global scope. This means that passing the value of `props.items` will be `undefined` unless `{ items }` is referred to by `props.items`. To make the strings in *items* available to the map( ) function, we need the keyword `this` to callback to the `props.items` from the React element assigned to the variable *list*.

	* The resulting ReactDom would look something like this:

```
	<AllTheThings items = [ ... ]>
		<ul className="things">
			<li key="0">foo</li>
			<li key="1">bar</li>
			<li key="2">baz</li>
			<li key="3">fizz</li>
			<li key="4">buzz</li>
		</ul>
	</AllTheThings> 
```

>
> A React component is an object, and can take custom **methods**.
> ```
>	renderListItem(thing, value) {
> 		return React.createElement(
>			"li", 
>			{ key: value }, 
>			thing)
> 	}
>```
> could be defined in the class and used by the map( ) function in this way: `this.props.items.map(this.renderListItem)`

* **ES6 Classes** *React.Component* is the base class from which all classes are created in React. By using the syntactic sugar of ES6 classes, we can extend the React component class. The syntax inside the class declaration is the same as it would be using React.createClass( ), but there is no *displayName* declaration.

```
	class AllTheThings extends React.Component {

		renderListItem(thing, value) {
			return React.createElement("li", { key: value }, thing)
 		}	

 		render() {
 			return React.createElement("ul", {className: "things"},
 				this.props.items.map(this.renderListItem)
 			)
 		}
	}
```
* **Stateless Functional Components** This type of component is not an object, like the previous component examples. Therefore, there is no *this* scope.
	* Simple, pure functions that are the easiest and most efficient way to use components.
	* Functional components take in props and return DOM elements.
	* If you need to encapsulate functionality or have a *this* scope, then stateless functional components are not the way to go.
	* Examples:
	```
	const AllTheThings = props =>
		React.createElement("ul", {className: "things"},
			props.items.map((thing, value) =>
				React.createElement("li", { key: value }, thing)
			)
		)
	```
	or
	```
	const AllTheThings = ({items}) =>
		React.createElement("ul", {className: "things"},
			props.items.map((thing, value) =>
				React.createElement("li", { key: value }, thing)
			)
		)
	```
* **Back to the Beginning** All the way back <a href="#what-is-a-react-element">here</a> I talked about the immutability of React elements and touched on the need for ReactDOM to re-render every time that an element were to change. <a href="#what-is-react">Before that</a>, I mentioned that ReactDOM kept programmers from needing to work with the DOM API directly. The reason for that is ReactDOM renders the DOM in place and updates only minimal changes needed to update the DOM, instead of tearing it down and rebuilding the DOM. By making sure that React elements remain immutable, those DOM elements will stay static and not need to be torn down and re-rendered. As we can see in the last few examples of React components, the elements themselves were created to take props. It is the props that are mutable, and that means that ReactDOM only has to re-render the elements whose props have changed.
* **One last thing** Instead of using *React.createElement( )*, there is an alternative method for creating methods called *factories*. If I get a chance to explore that in detail- if there is a need to explore that at all- I will create a separate post.

#### Why Did I Have To Learn This?
Professional development requires that I learn how React works, and not just how to manipulate a code base that already exists. In order to gain more context into how the code base that I work with actually functions, and to gain insight into how to improve the code, I need to understand the ins and outs of React.