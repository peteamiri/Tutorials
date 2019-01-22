# JavaScript

It is one of the most used programming language.

## Document approach

This document will try to use code examples to describe various concepts. 

### For More information

* [Wikipedia](https://en.wikipedia.org/wiki/JavaScript)
* [JavaScrip Video](https://www.youtube.com/watch?v=v2ifWcnQs6M&list=PL62E185BB8577B63D)

## General

* ServerSide 
* ClientSide

## Language Standard

### Comments
### Identifiers
### Variables
#### Scope
### Operations
### Logical Operators
### Statements
#### Conditional Statements
#### Flow Control Statements
### Functions
### Classes

# JavScript 

Event-driven programming can be overwhelming for beginners, which can make Node.js difficult to get started with. But don't let that discourage you.


## Introduction

To start using Node.js, you must first understand the differences between Node.js and traditional server-side scripting environments (eg: PHP, Python, Ruby, etc).

Node is a JavaScript environment running in Google's V8 JavaScript engine.


#### Comments

	// Everything from the // to end of line is ignored(*)

	//
	// Comment
	//

	/*
	** Sample multi-line Comments
	*/

you can also creat comments that can be used to generate documentation.

#### JavaScript Literals
Literal refer to any constants that can be directly referenced

**Todo** definition of Literals

	"Sample Text";
	1.0;
	1;
	

#### JavaScript Variables

All JavaScript variables must be identified with unique names. These unique names are called identifiers.

Identifiers can be short names (not  recommended) 

	x 
	y 

or more descriptive names (helps to understand the code and comprehend the logic better)
 
	age 
	sum 
	totalVolume

Of course more descriptive names are recommended, it helps the code t be more understandable. 
 
The general rules for constructing names for variables (unique identifiers) are:

* Names can contain letters, digits, underscores, and dollar signs.
* Names must begin with a letter or $ and _ 
* Names are <b>case sensitive</b> (y and Y are different variables)
* Reserved words (like JavaScript keywords) cannot be used as names


For example, here is the code for a simple Node.js application:

	var x=5; // Everything from the // to end of line is ignored(*) 
	var thingamajig = 123.45; // another variable

	var thisIsAString = 'This is a string'; 
	var alsoAString = '25';
	var isANumber = 25;
	
	var isEqual = (alsoAString==isANumber);	  // This is true, they are both 25.
	var isEqual = (alsoAString===isANumber);  // False one is a number, the other 										  // a string. 
	var concat=alsoAString + isANumber;		  // concat is now 2525
	
	var addition=isANumber + isANumber;	// addition is now 50 
	var alsoANumber=3.05;	            // is equal to 3.05 (usually).
	var floatError=0.06+0.01;           // is equal to 0.06999999999999999 var anExponent=1.23e+3;	                // is equal to 1230
	var hexadecimal = 0xff;	            // is equal to 255. 
	var octal = 0377;	                // is equal to 255.
	var isTrue = true;	                // This is a boolean, 
										// it can be true or false. 
	var isFalse= false;	                // This is a boolean, 
										// it can be true or false 

	var isArray = [0, 'one', 2, 3, '4', 5]; // This is an array.
	var four = isArray[4];       // assign a single array element to a variable.
	                             // in this case four = '4'

	var isObject = { 'color': 'blue',	// This is a Javascript object 'dog': 					'bark',
					'array': [0,1,2,3,4,5],
		            'myfunc': function () { alert('do something!'); }
	               }

	var dog = isObject.dog;	// dog now stores the string 'bark'; 

	isObject.myfunc();      // creates an alert box with the value "do  								// something!" 
	
	/*
	** A function that is assigned to a variable
	*/
	var someFunction = function() {
		return "I am a function!";
	}
	
	/*
	** a function can be reassigned to another variable
	*/
	var alsoAFunction = someFunction; //No () so alsoAFunction becomes a function
	
	var result = alsoAFunction();   // alsoAFunction is executed here because ()
	                                // executes the function so result stores the
									// return value of the function which is
									// "I am a function!"


	/* 
	** Anything following double slashes is an English-language comment.
	** Read the comments carefully: they explain the JavaScript code.
	**
	*/
 
	/*
	** variable is a symbolic name for a value.
	** Variables are declared with the var keyword:
	*/
	var x; // Declare a variable named x.

	/*
	** Values can be assigned to variables with an = sign
	*/
	x = 0; // Now the variable x has the value 0

	x // => 0: A variable evaluates to its value.
	
	/*
	** JavaScript supports several types of values
	** The variable can be reassigned to various Data Types
	*/
	x = 1;             // Numbers.
	x = 0.01;          // Just one Number type for integers and reals.
	x = "hello world"; // Strings of text in quotation marks.
	x = 'JavaScript';  // Single quote marks also delimit strings.
	x = true;          // Boolean values.
	x = false;         // The other Boolean value.
	x = null;          // Null is a special value that means "no value".
	x = undefined;     // Undefined is like null.
	
	var x = 5;
	var y = 6;
	var z = x + y;

	var i, a, b, c, max;
	max = 1000000000;
	var d = Date.now();
	var msg = 'Hello World';
	console.log(msg);

	/*
	** flow control statements
	*/
	for (i = 0; i < max; i++) {
    	a = 1234 + 5678 + i;
    	b = 1234 * 5678 + i;
    	c = 1234 / 2 + i;
	}

	console.log(Date.now() - d);

### Variable Scope

	var global = 'this is global';

	/*
	**
	*/
	function scopeFunction() {
		alsoGlobal = 'This is also global!';
		var notGlobal = 'This is private to scopeFunction!';

		function subFunction() {
		alert(notGlobal); // We can still access notGlobal in this child
						  // function.

		stillGlobal = 'No var keyword so this is global!'; 
		var isPrivate = 'This is private to subFunction!';
	}

	console.log(stillGlobal); // This is an error since we haven't executed 
	
	subfunction subFunction();	// execute subfunction
	
	console.log(stillGlobal); // This will output 'No var keyword 
							  // so this is global!' 
	console.log(isPrivate);   // This generate an error since 
						      // isPrivate is private to
							  // subfunction().

	console.log(global);   // outputs: 'this is global'

	}
	console.log(global);        // outputs: 'this is global'
	console.log(alsoGlobal);	// generates an error since 
								// we haven't run scopeFunction yet.

	 
	scopeFunction(); 
	console.log(alsoGlobal);  // outputs: 'This is also global!'; 
	console.log(notGlobal);   // generates an error.

## Array
This section describes arrays

	billingMethod = new Array(5)

	colors = new Array()
	colors[99] = "midnightblue"

	musicTypes = new Array(25)
	musicTypes[0] = "R&B"
	musicTypes[1] = "Blues"
	musicTypes[2] = "Jazz"


	msgArray = new Array()
	msgArray[0] = "Hello"
	msgArray[99] = "world"
	// The following statement is true,
	// because defined msgArray[99] element.
	if (msgArray.length == 100)
	myVar="The length is 100."

	myVar="Multidimensional array test; "
	a = new Array(4)
	for (i=0; i < 4; i++) {
		a[i] = new Array(4)
		Core JavaScript Reference 1.5:
		for (j=0; j < 4; j++) {
			a[i][j] = "["+i+","+j+"]"
		}
	}
	for (i=0; i < 4; i++) {
		str = "Row "+i+":"
		for (j=0; j < 4; j++) {
			str += a[i][j]
		}
		myVar += str +"; "
	}

	alpha=new Array("a","b","c")
	numeric=new Array(1,2,3)
	alphaNumeric=alpha.concat(numeric) // creates array ["a","b","c",1,2,3]

	a = new Array("Wind","Rain","Fire")
	myVar1=a.join()      // assigns "Wind,Rain,Fire" to myVar1
	myVar2=a.join(", ")  // assigns "Wind, Rain, Fire" to myVar1
	myVar3=a.join(" + ") // assigns "Wind + Rain + Fire" to myVar1

## Objects

	/*
	**  JavaScript's most important data type is the object.
	** An object is a collection of name/value pairs, 
	** or a string to value map.
	*/
	var book = { 
		// Objects are enclosed in curly braces.
		topic: "JavaScript", // The property "topic" has value "JavaScript".
		fat: true // The property "fat" has value true.
	}; // The curly brace marks the end of the object.
	

	/*
	**  Access the properties of an object with . or []:
	*/
	book.topic // => "JavaScript"
	book["fat"] // => true: another way to access property values.
	book.author = "Flanagan"; // Create new properties by assignment.
	book.contents = {}; // {} is an empty object with no properties.
	
	/*
	** JavaScript also supports arrays (numerically indexed lists) of values:
	*/
	var primes = [2, 3, 5, 7]; // An array of 4 values, delimited with [ and ].
	primes[0] // => 2: the first element (index 0) of the array.
	primes.length // => 4: how many elements in the array.
	primes[primes.length-1] // => 7: the last element of the array.
	primes[4] = 9; // Add a new element by assignment.
	primes[4] = 11; // Or alter an existing element by assignment.
	
	var empty = []; // [] is an empty array with no elements.
	empty.length // => 0
	
	/*
	** Arrays and objects can hold other arrays and objects:
	*/
	var points = [   // An array with 2 elements.
		{x:0, y:0},  // Each element is an object.
		{x:1, y:1}
	];
	
	var data = {                // An object with 2 properties
		trial1: [[1,2], [3,4]], // The value of each property is an array.
		trial2: [[2,3], [4,5]]  // The elements of the arrays are arrays.
	};

	myCar = [
			{
			color:"red", 
			wheels:4, 
				engine:{
					cylinders:4, 
					size:2.2
				}
			}, 
			2,
			"cherry condition", 
			"purchased 1997"
			]
	
	newCar = [
				{
					color:"red", 
					wheels:4, 
					engine:{
						cylinders:4, 
						size:2.2
					}
				}, 
				2
			]
			myCar[0].color = red newCar[0].color = red
	
	//The new color of my Honda is purple
	myCar[0].color = purple
	newCar[0].color = purple

## Operations

	/*
	** Operators act on values (the operands) to produce a new value.
	** Arithmetic operators are the most common:
	*/
	3 + 2 // => 5: addition
	3 - 2 // => 1: subtraction
	3 * 2 // => 6: multiplication
	3 / 2 // => 1.5: division
	points[1].x - points[0].x // => 1: more complicated operands work, too
	"3" + "2"                 // => "32": + adds numbers, concatenates strings
	
	/*
	** JavaScript defines some shorthand arithmetic operators
	*/
	var count = 0; // Define a variable
	count++;       // Increment the variable
	count--;       // Decrement the variable
	count += 2;    // Add 2: same as count = count + 2;
	count *= 3;    // Multiply by 3: same as count = count * 3;
	count          // => 6: variable names are expressions, too.
	
	/*
	** Equality and relational operators test whether two values are equal,
	** unequal, less than, greater than, and so on. 
	** They evaluate to true or false.
	*/
	var x = 2, y = 3; // These = signs are assignment, not equality tests
	x == y            // => false: equality
	x != y            // => true: inequality
	x < y             // => true: less-than
	x <= y            // => true: less-than or equal
	x > y             // => false: greater-than
	x >= y            // => false: greater-than or equal
	"two" == "three"  // => false: the two strings are different
	"two" > "three"   // => true: "tw" is alphabetically greater than "th"
	false == (x > y)  // => true: false is equal to false
	
	/*
	** Logical operators combine or invert boolean values
	*/
	(x == 2) && (y == 3)  // => true: both comparisons are true. && is AND
	(x > 3) || (y < 3)    // => false: neither comparison is true. || is OR
	!(x == y)             // => true: ! inverts a boolean value

## Flow Control Statements

	/*
	** flow control statements
	*/
	for (i = 0; i < max; i++) {
    	a = 1234 + 5678 + i;
    	b = 1234 * 5678 + i;
    	c = 1234 / 2 + i;
	}

	/*
	** Example of a While Loop
	*/
	while(n > 1) { // Repeat statements in {} while expr in () is true
		product *= n; // Shortcut for product = product * n;
		n--; // Shortcut for n = n - 1
	} // End of loop

	/*
	** Example of a Single Line for loop
	*/
	for(i=2; i <= n; i++) // Automatically increment i from 2 up to n
		product *= i;     // Do this each time. {} not needed for 
						  // the first-line in a loop



## Functions

	/*
	** The following is a simple function declearation
	*/
	function whirlymajig(jabberwocky) {	
		/* 
		** Here we take the jabberwocky and insert 
		** it in the gire-gimble,
		** taking great care to observe the ipsum lorum!	
		** For bor-rath-outgrabe!
		** We really should patent this! 
		*/
		return (jabberwocky*2);
	}

	/* 
	** Functions are parameterized blocks of 
	** JavaScript code that we can invoke.
	** Define a function named "plus1" with parameter "x"
	*/
	function plus1(x) { 
		return x+1; // Return a value one larger than the value passed in
	} // Functions are enclosed in curly braces

	/*
	** the following line will invoke the function 
	** defined above
	*/
	plus1(y)    // => 4: y is 3, so this invocation returns 3+1
	
	/*
	** Functions are values and can be assigned to vars
	*/
	var square = function(x) { 
		return x*x; // Compute the function's value
	}; // Semicolon marks the end of the assignment.
	
	/* 
	** This is how to reference a function assigned to a variable
	*/
	square(plus1(y)) // => 16: invoke two functions in one expression0

	/* 
	** When functions are assigned to the properties of an object, we call
	** them "methods". All JavaScript objects have methods:
	*/
	var a = [];    // Create an empty array
	a.push(1,2,3); // The push() method adds elements to an array
	a.reverse();   // Another method: reverse the order of elements
	
	/*
	** We can define our own methods, too. 
	** The "this" keyword refers to the object
	** on which the method is defined: 
	** in this case, the points array from above.
	**
	** Define a method to compute distance between 	points
	*/
	points.dist = function() { 
		var p1 = this[0];      // First element of array we're invoked on
		var p2 = this[1];      // Second element of the "this" object
		var a = p2.x-p1.x;     // Difference in X coordinates
		var b = p2.y-p1.y;     // Difference in Y coordinates
		return Math.sqrt(a*a + // The Pythagorean theorem
			b*b);              // Math.sqrt() computes the square root
	};
	
	points.dist() // => 1.414: distance between our 2 points


	/* 
	** JavaScript statements include conditionals and loops using the syntax
	** of C, C++, Java, and other languages.
	*/
	function abs(x) { // A function to compute the absolute value
		if (x >= 0) { // The if statement...
			return x; // executes this code if the comparison is true.
		} // This is the end of the if clause.
		else { // The optional else clause executes its code if
			return -x; // the comparison is false.
		} // Curly braces optional when 1 statement per clause.
	} // Note return statements nested inside if/else.
	
	/*
	** This function to compute factorials
	*/
	function factorial(n) { 
		var product = 1; // Start with a product of 1
		while(n > 1) { // Repeat statements in {} while expr in () is true
			product *= n; // Shortcut for product = product * n;
			n--; // Shortcut for n = n - 1
		} // End of loop
		return product; // Return the product
	}

	factorial(4) // => 24: 1*4*3*2
	
	/*
	** Another version using a different loop
	*/
	function factorial2(n) {  
		var i, product = 1;   // Start with 1
		for(i=2; i <= n; i++) // Automatically increment i from 2 up to n
			product *= i;     // Do this each time. {} not needed for 
							  // the first-line in a loop
		return product;       // Return the factorial
	}

	/*
	** This will invoke the function
	*/
	factorial2(5) // => 120: 1*2*3*4*5

	/*
	** Compare two values
	*/
	function compare(a, b) {
		if (a is less than b by some ordering criterion)
			return -1
		if (a is greater than b by the ordering criterion)
			return 1
		// a must be equal to b
		return 0
	}
	/*
	** Same funtionality with more optimized code
	*/
	funcction compareNumbers(a, b) {
		return a - b
	}
	
	/* Assigne value to an array
	** then write it and then sort it
	** and then write it again
	*/
	a = new Array();
	a[0] = "Ant";
	a[5] = "Zebra";
	/*
	** Formate a string from an array
	*/
	function writeArray(x) {
		for (i = 0; i < x.length; i++) {
			console.log(x[i]);
			if (i < x.length-1) 
				console.log(", ");
		}
	}
	/*
	** write the array then sort it
	** and then rewrite it
	*/
	writeArray(a);
	a.sort();
	console.log("\n\n");
	writeArray(a);

	/* 
	** the following is the output of the above code
	** ant, null, null, null, null, zebra
	** ant, null, null, null, null, zebra
	*/

	/* 
	** More examples
	*/
	stringArray = new Array("Blue","Humpback","Beluga")
	numericStringArray = new Array("80","9","700")
	numberArray = new Array(40,1,5,200)
	mixedNumericArray = new Array("80","9","700",40,1,5,200)
	
	function compareNumbers(a, b) {
		return a - b
	}
	
	document.write("<B>stringArray:</B> " + stringArray.join() +"<BR>")
	document.write("<B>Sorted:</B> " + stringArray.sort() +"<P>")
	document.write("<B>numberArray:</B> " + numberArray.join() +"<BR>")
	document.write("<B>Sorted without a compare function:</B> " + numberArray.sort() + "<BR>")
	document.write("<B>Sorted with compareNumbers:</B> " +
	numberArray.sort(compareNumbers) +"<P>")

	document.write("<B>numericStringArray:</B> " + numericStringArray.join()
	+"<BR>")

	document.write("<B>Sorted without a compare function:</B> " +
	numericStringArray.sort() +"<BR>")

	document.write("<B>Sorted with compareNumbers:</B> " +
	numericStringArray.sort(compareNumbers) +"<P>")
	document.write("<B>mixedNumericArray:</B> " + mixedNumericArray.join()
	+"<BR>")
	document.write("<B>Sorted without a compare function:</B> " +
	mixedNumericArray.sort() +"<BR>")
	document.write("<B>Sorted with compareNumbers:</B> " +
	mixedNumericArray.sort(compareNumbers) +"<BR>")

	/* 
	**************************************************************
	The following is the output of the above code snippet

	stringArray: Blue,Humpback,Beluga
	Sorted: Beluga,Blue,Humpback
	numberArray: 40,1,5,200
	Sorted without a compare function: 1,200,40,5
	Sorted with compareNumbers: 1,5,40,200
	numericStringArray: 80,9,700
	Sorted without a compare function: 700,80,9
	Sorted with compareNumbers: 9,80,700
	mixedNumericArray: 80,9,700,40,1,5,200
	Sorted without a compare function: 1,200,40,5,700,80,9
	Sorted with compareNumbers: 1,5,9,40,80,200,700

	************************************************************
	*/