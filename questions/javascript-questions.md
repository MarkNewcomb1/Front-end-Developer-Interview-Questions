# JS Questions:

* Explain event delegation

_It allows you to add event listeners on the parent instead of a child node. Then the event listener looks through the bubbled events to find a match on child elements. Like so:_

```javascript
document.getElementById("parent-list").addEventListener("click", function(e) {
	// e.target is the clicked element!
	// If it was a list item
	if(e.target && e.target.nodeName == "LI") {
		// List item found!  Output the ID!
		console.log("List item ", e.target.id.replace("post-", ""), " was clicked!");
	}
});
```

* Explain how `this` works in JavaScript

_It refers to the object it belongs to._

* Explain how prototypal inheritance works

_All JavaScript objects get properties and methods from a protoype. Array objects inherit from Array.prototype. A prototype is a working object instance._

* What do you think of AMD vs CommonJS?

_They're both module definition APIs, but AMD is more suited for the browser, because module dependencies can be loaded asynchronously. CommonJS is better for server side because of its synchronous nature._

* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?

  _ It needs parentheses wrapped around it:_

  ```javascript
    (function foo(){ })();
  ```
* What's the difference between a variable that is: `null`, `undefined` or undeclared?

_Null is an explicit value you set, undefined is the value  a variable is initialized with when it's declared with the var keyword but not assigned a value. Undeclared is one that doesn't use the var keyword, so it gets created on the global object._

  * How would you go about checking for any of these states?

_use `typeof`._

* What is a closure, and how/why would you use one?

_It's a function that's inside another function that has access to the three scopes - its own scope, the outer function scope, and the global scope. Closures are great for using the outer function as a factory for creating functions that are related._

* Can you describe the main difference between a `forEach` loop and a `.map()` loop and why you would pick one versus the other?

_Map is faster and creates a new array, whereas forEach mutuates the original array. Really depends on what you're doing._

* What's a typical use case for anonymous functions?

_They're function expressions instead of statements, so they're more flexible. Like say, inside a map function. What you want to do to each item in the array is a function, but that function is anonymous._

* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?

_Native objects are ones supplied by JavaScript itself, like String, Array, Number. Host objects are supplied by the browser, like window and document._

* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
* What's the difference between `.call` and `.apply`?

_Both can be called on functions, which they run in the context of the first argument. In call the subsequent arguments are passed in to the function as they are, while apply expects the second argument to be an array that it unpacks as arguments for the called function._

* Explain `Function.prototype.bind`.

_bind creates a new method that sets the `this` keyword to the provided value._

* What's the difference between feature detection, feature inference, and using the UA string?
* Explain Ajax in as much detail as possible.
* What are the advantages and disadvantages of using Ajax?
* Explain how JSONP works (and how it's not really Ajax).
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".

_JavaScript moves all declarations to the top of the current scope._

* Describe event bubbling.
* Describe event capturing.
* What's the difference between an "attribute" and a "property"?

_An attribute is in the HTML itself, like checked. A property is in JavaScript's DOM object. So:_

```
<input type="checkbox" checked=true/>

$('input').prop('checked'); // returns true
$('input').attr('checked'); // returns "checked"
```

* Why is extending built-in JavaScript objects not a good idea?
* Difference between window load event and document DOMContentLoaded event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary operator, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.

_A mutable object is an object whose state can be modified after it is created. An immutable object is an object whose state cannot be modified after it is created._


  * What is an example of an immutable object in JavaScript?

  _Just call Object.freeze on it._
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?
* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
* What are the differences between variables created using `let`, `var` or `const`?
* What are the differences between ES6 class and ES5 function constructors?
* Can you offer a use case for the new arrow `=>` function syntax? How does this new syntax differ from other functions?
* What advantage is there for using the arrow syntax for a method in a constructor?
* What is the definition of a higher-order function?
* Can you give an example for destructuring an object or an array?

_Unpacking values from an array into distinct variables:_

```javascript
var a, b, rest;
[a, b] = [10, 20];

console.log(a);
// expected output: 10

console.log(b);
// expected output: 20

[a, b, ...rest] = [10, 20, 30, 40, 50];

console.log(rest);
// expected output: [30,40,50]

```
* ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
* Can you give an example of a curry function and why this syntax offers an advantage?

_Currying is the process of taking a function with multiple arguments and turning it into a sequence of functions each with only a single argument. It creates reusable code._

* What are the benefits of using `spread syntax` and how is it different from `rest syntax`?
* How can you share code between files?
* Why you might want to create static class members?
