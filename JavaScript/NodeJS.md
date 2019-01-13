# Ecma 262

[http://www.ecma-international.org/publications/files/ECMA-ST/Ecma-262.pdf](http://www.ecma-international.org/publications/files/ECMA-ST/Ecma-262.pdf)

[https://docs.microsoft.com/en-us/scripting/javascript/javascript-language-reference](https://docs.microsoft.com/en-us/scripting/javascript/javascript-language-reference)

[http://es6-features.org/#Lexicalthis](http://es6-features.org/#Lexicalthis)
[https://google.github.io/styleguide/javascriptguide.xml#JavaScript_Language_Rules](https://google.github.io/styleguide/javascriptguide.xml#JavaScript_Language_Rules)

[https://github.com/rwaldron/idiomatic.js](https://github.com/rwaldron/idiomatic.js)
[http://speakingjs.com/es5/index.html](http://speakingjs.com/es5/index.html)
[https://google.github.io/styleguide/jsguide.html](https://google.github.io/styleguide/jsguide.html)
#Use of Semicolon in JavaScript

# Modules

This section provides an overview of the `module.exports` and `exports` in Node.js.

> Note: This post covers using modules in Node. If you want to learn how you can use modules inside of the browser, read: Understanding JavaScript Modules: Bundling & Transpiling


## What is a Module

A module encapsulates related code into a single unit of code. This is very similar to `lib` in 'C' and `namespaces` or `packages` in Java Language. You can create a module, this can be interpreted as moving all related functions into a single file. Let’s illustrate this point with an example involving an application built with Node.js. Imagine that we created a file called `greetings.js` and it contains the following two functions:

```javascript
	// greetings.js
	sayHelloInEnglish = function() {
		return "Hello";
	};

	sayHelloInSpanish = function() {
		return "Hola";
	};
```

## Exporting a Module

The utility of greetings.js increases when its encapsulated code can be utilized in other files. So let’s refactor greetings.js to achieve this goal. To comprehend what is actually happening, we can follow a three-step process:

1) Imagine that this line of code exists as the first line of code in greetings.js:
```javascript
	// greetings.js
	var exports = module.exports = {};
```
2) Assign any expression in greetings.js that we want to become available in other files to the exports object:

	// greetings.js
	// var exports = module.exports = {};
	exports.sayHelloInEnglish = function() {
		return "HELLO";
	};

	exports.sayHelloInSpanish = function() {
		return "Hola";
	};

In the code above, we could have replaced exports with module.exports and achieved the same result. If this seems confusing, remember that exports and module.exports reference the same object.

3) This is the current value of module.exports:

	module.exports = {
		sayHelloInEnglish: function() {
		  return "HELLO";
		},

		sayHelloInSpanish: function() {
	  	return "Hola";
		}
	};

## Importing a Module

Let's import the publicly available methods of greetings.js to a new file called main.js. This process can be described in three steps:

1) The keyword require is used in Node.js to import modules. Imagine that this is how require is defined:
```js
	var require = function(path) {
		// ...
		return module.exports;
	};
```
2) Let's require greetings.js in main.js:
```js
	// main.js
	var greetings = require("./greetings.js");
```
The above code is equivalent to this:
```js
	// main.js
	var greetings = {
		sayHelloInEnglish: function() {
		  return "HELLO";
	},
		sayHelloInSpanish: function() {
		  return "Hola";
		}
	};
```
3) We can now access the publicly available methods of greetings.js as a property of our greetings variable in main.js.
```js
	// main.js
	var greetings = require("./greetings.js");

	// "Hello"
	greetings.sayHelloInEnglish();

	// "Hola"
	greetings.sayHelloInSpanish();
```

## Important Points

The keyword `require` returns an object, which references the value of `module.exports` for a given file. If a developer unintentionally or intentionally re-assigns `module.exports` to a different object or different data structure, then any properties added to the original `module.exports` object will not be accessible.

An example will help elaborate this point:
```js
	// greetings.js
	// var exports = module.exports = {};

	exports.sayHelloInEnglish = function() {
		return "HELLO";
	};

	exports.sayHelloInSpanish = function() {
		return "Hola";
	};

	/*
	* this line of code re-assigns
	* module.exports
	*/
	module.exports = "Bonjour";
	Now let’s require greetings.js in main.js:

	// main.js
	var greetings = require("./greetings.js");
```

At this moment, nothing is different than before. We assign the variable greetings to any code that is publicly available in `greetings.js`.

The consequence of re-assigning `module.exports` to a data structure other than its default value is revealed when we attempt to invoke `sayHelloInEnglish` and `sayHelloInSpanish`:
```js
	// main.js
	// var greetings = require("./greetings.js");
	/*
	** TypeError: object Bonjour has no
	** method 'sayHelloInEnglish'
	*/
	greetings.sayHelloInEnglish();

	/*
	* TypeError: object Bonjour has no
	* method 'sayHelloInSpanish'
	*/
	greetings.sayHelloInSpanish();
```

To understand why these errors are occuring, let’s log the value of greetings to a console:
```js
	// "Bonjour"
	console.log(greetings);
```
At this point, we are trying to access the methods `sayHelloInEnglish` and `sayHelloInSpanish` on the string “Bonjour.” module.exports, in other words, is no longer referencing the default object that contain those methods.

## Conclusion

Importing and exporting modules is a ubiqutous task in Node.js. I hope that the difference between exports and module.exports is clearer. Moreover, if you ever encounter an error in accessing publicly available methods in the future, then I hope that you have a better understanding of why those errors may occur.

## For more information see also

* [https://www.sitepoint.com/understanding-module-exports-exports-node-js/](https://www.sitepoint.com/understanding-module-exports-exports-node-js/)

## See also

* [http://2ality.com/2011/04/modules-and-namespaces-in-javascript.html](http://2ality.com/2011/04/modules-and-namespaces-in-javascript.html)

# jsdoc
The following command will install the jsdoc
```
  npm install -g jsdoc
```

```js
	/**
	* This is a description
	* @namespace My.Namespace
	* @method myMethodName
	* @param {String} str - some string
	* @param {Object} obj - some object
	* @param {requestCallback} callback - The callback that handles the response.
	* @return {bool} some bool
	*/
	function SampleFunction (str, obj, callback) {
	   var isTrue = callback(str, obj); // do some process and returns true/false.
	   return isTrue ;
	}
```
jsdoc can be run at commandline
```
	jsdoc app.js
```
this command will creat an `out` directory and create the document in the given directory.

## See Also

* [http://usejsdoc.org/](http://usejsdoc.org/)
* [https://dzone.com/articles/introduction-jsdoc](https://dzone.com/articles/introduction-jsdoc)
* [https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/javascript/](https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/javascript/)
* [http://2ality.com/2011/08/jsdoc-intro.html](http://2ality.com/2011/08/jsdoc-intro.html)
* [https://github.com/dwyl/learn-jsdoc](https://github.com/dwyl/learn-jsdoc)
* [https://www.eventbrite.com/engineering/commenting-javascript-code-with-jsdoc/](https://www.eventbrite.com/engineering/commenting-javascript-code-with-jsdoc/)
* [https://en.wikipedia.org/wiki/JSDoc](https://en.wikipedia.org/wiki/JSDoc)
* [https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler](https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler)

# JavaScript variable(identifier) names

All JavaScript variables also refered to as identifiers must be identified with unique names.
* Identifiers can be short names (like x and y) or
* more descriptive names (age, sum, totalVolume).

The general rules for constructing names for variables (unique identifiers) are:
* An identifier must start with $, _, or any character (upper or lower case) in the Unicode categories
* Variable Names can contain letters, digits, underscores, and dollar signs.
* Variable Names can not be a reserved words.
* Variable Name can be a unicode.
* Variable Name cannot start with a number(digit 0-9), as the subsequent characters number is a valid value.

# Coercion

JavaScript is a loosely typed language, as opposed to strongly typed languages like C++. This means that JavaScript variables have no predetermined type. Instead, the type of a variable is the type of its value. This behavior allows you to treat a value as if it were of a different type.

In JavaScript, you can perform operations on values of different types without causing an exception. The JavaScript interpreter implicitly converts, or coerces, one of the data types to that of the other, then performs the operation. The rules for coercion of string, number, and Boolean values are the following:

* If you add a number and a string, the number is coerced to a string.
* If you add a Boolean and a string, the Boolean is coerced to a string.
* If you add a number and a Boolean, the Boolean is coerced to a number.

In the following example, a number added to a string results in a string.
```js
	var x = 2000;
	var y = "Hello";
	// The number is coerced to a string.
	x = x + y;
	document.write(x);
	// Output:
	// 2000Hello
```
Strings are automatically converted to equivalent numbers for comparison purposes. To explicitly convert a string to an integer, use the parseInt function. To explicitly convert a string to a number, use the parseFloat function

# Arrow functions (=>)

# lint Code
lint referes to a generic tools that are used to flag improper or suspicious usage in code written in any programming language.
in JavaScript, there are currently various tools that provide same functionality with slight variations;

* eslint
* jsHint
* JSCS
* JSLint
* Validator pro

(https://www.slant.co/topics/2411/~javascript-linting-tools)(https://www.slant.co/topics/2411/~javascript-linting-tools)

They are presented in the order of their popularity. This section concentrated on the `eslint` since it is, currenlty, the mode populer lint tool.

## eslint

To install eslint globally on the machine.
```
	npm install -g eslint
```
you can use eslint at the command line.

examples of eslint
```
	express <project name>
	cd <project name>
	npm install
	eslint --init
	eslint app.js
```
## for more information see

* (https://eslint.org/docs/user-guide/command-line-interface)(https://eslint.org/docs/user-guide/command-line-interface)

# JavaScript debug

to start debug use the following commands:
```
	exporess <project name>
	cd <project name>
	npm install
	set DEBUG=* & node app
```
See npm debug

## for more information see

* (https://www.npmjs.com/package/debug)(https://www.npmjs.com/package/debug)

# this keyword

The this keyword behaves differently in JavaScript compared to other language. In Object Oriented languages, the this keyword refers to the current instance of the class. In JavaScript the value of this is determined mostly by the invocation context of function ( context.function() ) and where it is called.

## See also

* [http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/](http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/)

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

* [https://toddmotto.com/understanding-the-this-keyword-in-javascript/](https://toddmotto.com/understanding-the-this-keyword-in-javascript/)

# Standardjs

Not much found of this yet. It removed all the `;` from the code. My prefered choice is to add `;`. To make the matter worst, this utility does not allow any configuration.

[https://standardjs.com/](https://standardjs.com/)

# Unit Testing tools

## See for more information

* [https://hashnode.com/post/what-is-the-best-javascript-unit-testing-framework-ciijnqkfu023tlc53ez0mkl6y](https://hashnode.com/post/what-is-the-best-javascript-unit-testing-framework-ciijnqkfu023tlc53ez0mkl6y)

* [https://stackoverflow.com/questions/36861328/how-to-choose-between-jasmine-and-mocha-frameworks-while-testing-an-angular-js-a](https://stackoverflow.com/questions/36861328/how-to-choose-between-jasmine-and-mocha-frameworks-while-testing-an-angular-js-a)

## Mochajs

Mocha delivers the Test Driven Capabilities to a NodeJS project.

To install Mocha,
```
	npm install -g Mocha
```
To run the Mocha run the following at the command prompt:
```
	mocha
```
The test case will reside in the `<project directory>/test` directory. The Mocha will run tall test cases in this directory and provide a summary.
```js
	var assert = require("assert"); // node.js core module

	describe('Array', function(){
	describe('#indexOf()', function(){
	  it('should return -1 when the value is not present', function(){
	    assert.equal(-1, (1,2,3).indexOf(4)); // 4 is not present in this array so indexOf returns -1
	  })
	})
	});
```

### For more information See

This is a good starting point make sure you will follow to travis and Istanbul.

* [https://mochajs.org/](https://mochajs.org/)

* [http://chaijs.com/](http://chaijs.com/)

* [https://github.com/ideaq/learn-mocha](https://github.com/ideaq/learn-mocha)

* [https://www.distelli.com/docs/tutorials/automated-mocha-tests-for-node/](https://www.distelli.com/docs/tutorials/automated-mocha-tests-for-node/)

* [http://mherman.org/blog/2015/09/10/testing-node-js-with-mocha-and-chai/#.Wa8Cd_mGOos](http://mherman.org/blog/2015/09/10/testing-node-js-with-mocha-and-chai/#.Wa8Cd_mGOos)

* [https://scotch.io/tutorials/test-a-node-restful-api-with-mocha-and-chai](https://scotch.io/tutorials/test-a-node-restful-api-with-mocha-and-chai) This is very detailed

* [https://nicolas.perriault.net/code/2013/testing-frontend-javascript-code-using-mocha-chai-and-sinon/](https://nicolas.perriault.net/code/2013/testing-frontend-javascript-code-using-mocha-chai-and-sinon/)

* [http://stackabuse.com/testing-node-js-code-with-mocha-and-chai/](http://stackabuse.com/testing-node-js-code-with-mocha-and-chai/)

* [http://www.andrewsouthpaw.com/2015/01/08/beginners-guide-to-testing-with-mocha-chai/](http://www.andrewsouthpaw.com/2015/01/08/beginners-guide-to-testing-with-mocha-chai/)

## Jasmine

## QUnit

## Chai

# Code Coverate

## Istanbul
Istanbul is a unit test code coverage profiler.

### for more information see

* [https://github.com/dwyl/learn-istanbul](https://github.com/dwyl/learn-istanbul)

# Continious Integration

Currently, jenkins is a leader in providing cross-platform CI capabilities.

## travis
Travis is very similar to Jenkins. However, it is much simpler and easier to setup and learn. I am not sure this is same as travise-ci. The travise-ci runs from a propriotary server from the cloud. (Not recommended)

### for more information see

* [https://github.com/dwyl/learn-travis](https://github.com/dwyl/learn-travis)
* [https://docs.travis-ci.com/user/getting-started/](https://docs.travis-ci.com/user/getting-started/)
