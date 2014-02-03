## JavaScript Questions:

### Explain event delegation

**google**: avoid event been added to specific node, instead been added to parent node, and find the specific child node in event bubbling on that parent.

benefit:

1. if append a new child node, no need to rebind another event. new DOM can be created dynamically on the fly.
2. less event binding, save memory, especially for webapps.


### Explain how `this` works in JavaScript

**try**: this refers the current object. when it is used in a function. this associate with the object where the function is invoked.

**google**: evaluates to the value of the ThisBinding of the current execution context. if function is all by `obj.func()`, this will refer to `obj`, if `func.call(obj)` (apply, bind), this refer to `obj`, otherwise, refers to `window`


### Explain how prototypal inheritance works

**try**: assign objectA's prototype to another objectB. it makes inheritance happened. In another word, if property is not found in objectA, it will go to objectB in the use of JavaScript's prototype-chaining machinism. So if still not found in objectB, JavaScript will go to objectB's prototype, say, Object till the end.


### How do you go about testing your JavaScript

**try**: simplest way is console.log(); or better ways like a assert function that log different message by boolean argument, or using a test framework like Jasmine to write test case first. like Behavior-driven development.

**google**: first write unit testable code, then use testing framework like QUnit to write unit test case. 
> http://coding.smashingmagazine.com/2012/06/27/introduction-to-javascript-unit-testing/


### AMD vs. CommonJS?

**try**: they different stardard for js module loader, AMD is aync load, good for browser side environment, like RequireJS. CommonJS use sync approche, good for server-side js module loading, used by Node.js module.

**google**: AMD use `exports` objects to expose the API of a module, use `require()` to fetch dependency. RequireJS use `define()` to decare dependency before been loaded.


### What's a hashtable?

**try**: hashtable is a associated array, a set of key-value pair. every object in js is a hashtable.

**google**: used by table['key'] or table.key, different is key can be dynamically generated in the first approche. 


### Explain why the following doesn't work as an IIFE: function foo(){ }();.
#### What needs to be changed to properly make it an IIFE?

**try**: because function foo(){ } will be first interpreted as a function declare, then the invoke symbol () will not refer that function. `(function foo(){})()` will do.

**google**: function foo(){} is statement. It will not excuted like a expression. also, `()` will be a grouping operate without expression in it, so a SyntaxError will be thown. Any way that make parser think `function` is not statement but an expression will work it a IIFE, like 
```
(function foo(){})();
(function foo(){}());
var i = function foo(){}();
!function foo(){}();
true, function foo(){}();
new function(){}();
```


### What's the difference between a variable that is: null, undefined or undeclared?
#### How would you go about checking for any of these states?

**try**: null is define variable be not assigned to any value. undefined happend when refering to a variable not exist. to check null, use `myVal == null`, to check undefined, use `typeof myVal == 'undefined'`.

**google**:  `null` is the assignment value of variable, it can be assign to variable as a reprsentation of no value. `undefined` is type of an declared varialbe that has not yet been assign to a value. `undeclared` means the variable does not exist at all, which will cause error.
aside: `undefined` is also a global variable that can be modified. So lots of library rewrite the `library` in case it is been modified.


### What is a closure, and how/why would you use one?

**try**: closure is a function inside another function. inner function can get access to outer function, but outer cannot. If inner funnction that is using outer function's variable is being used, the variable in the outer function will stay in memory even it is returned. Besides, property in the outer function cannot be accessed directly from outside, only by the inner function. This feature comes to the hidden property.

**google**: a closure is a function called in one context that remembers variables defined in another context – the context in which it was defined. Besides, it is unwise to unnecessary defined function inside a function, because it waste speed and memory. 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Closures


### What's a typical use case for anonymous functions?

**try**: solove the loop error. 

```
// problem
var obj = {};
for (var i = 0; i < 10; i++ ) {
	obj[i] = function(){
		console.log("ret: " + i);
	};
}
obj[0]();

// correction
var obj = {};
for (var i = 0; i < 10; i++ ) {
	obj[i] = (function(index){
		return function(){
			console.log("ret: " + index);
		}
	})(i);
}
obj[0]();

```


### Explain the "JavaScript module pattern" and when you'd use it.
#### Bonus points for mentioning clean namespacing.
#### What if your modules are namespace-less?

