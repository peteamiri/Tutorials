# NodeJS

Event-driven programming can be overwhelming for beginners, which can make Node.js difficult to get started with. But don't let that discourage you.

Node.js is only an environment; you have to do everything yourself.


### More information

* [NodeJS API documentation](https://nodejs.org/api)
* [NodeJS By Example](https://www.gitbook.com/book/nelsonic/node-js-by-example/details)
* [YouTube NodeJS Tutorial 1](https://www.youtube.com/playlist?list=PLillGF-RfqbYRpji8t4SxUkMxfowG4Kqp)
* [Wiki on Node.js](https://en.wikipedia.org/wiki/Node.js)
* [Tutorial](https://blog.risingstack.com/node-hero-tutorial-getting-started-with-node-js/)

**V8 Information**

* [Wiki Chrome_V8](https://en.wikipedia.org/wiki/Chrome_V8)
* [developers v8 guide](https://developers.google.com/v8/)
* [Youtube V8 engine](https://www.youtube.com/watch?v=hWhMKalEicY)
* [how-the-v8-engine-works](https://thibaultlaurens.github.io/javascript/2013/04/29/how-the-v8-engine-works/)

**NPM Information**

*[Wikipedia Npm](https://en.wikipedia.org/wiki/Npm_(software))

* [npmjs](https://www.npmjs.com/)

**YO**

* [Wikipedia on Yeoman](https://en.wikipedia.org/wiki/Yeoman_(software))
* [yeoman.io](http://yeoman.io/)


**GruntJS**

* [Wikipedia on Grunt](https://en.wikipedia.org/wiki/Grunt_(software))
* [gruntjs.com](https://gruntjs.com/)
* [github for gruntj](https://github.com/gruntjs/grunt)

** GulpJS**

* [Wiki on Gulp.js](https://en.wikipedia.org/wiki/Gulp.js)
* [gulpjs.com](https://gulpjs.com/)
* [github for gulpjs](https://github.com/gulpjs/gulp)
* [gulpjs docs](https://github.com/gulpjs/gulp/tree/master/docs)


## Server

The following is a sample Server Code

	// Load the 'http' module
	const http = require('http');

	// Use the 'http' module to create a new web server
	http.createServer((req, res) => {
		// Use the 'response' object to write the 'content-type' response header
		res.writeHead(200, {
			'Content-Type': 'text/plain'
		});

		// Use the 'response' object to write a response body and end the request
		res.end('Hello World');
	}).listen(3000);

	// Log the server status to the console
	console.log('Server running at http://localhost:3000/');

## Modules

The following is a sample code for Modules

	// Define a module variable
	const message = 'Hello';

	// Print message to the console
	exports.sayHello = function() {
		console.log(message);
	};

The following code is a sample of using Module

	// Load the 'hello' module
	const hello = require('./hello');

	// Use the 'hello' module sayHello() method
	hello.sayHello();


## Introduction

Node is a JavaScript environment running in Google's V8 JavaScript engine.

### Asynchronous Programming

Node.js uses a module architecture to simplify the creation of complex applications.

Chances are good that you are familiar with asynchronous programming; it is, after all, the "A" in Ajax. 

Every function in Node.js is asynchronous. Therefore, everything that would normally block the thread is instead executed in the background. This is the most important thing to remember about Node.js. For example, if you are reading a file on the file system, you have to specify a callback function that is executed when the read operation has completed.


**Node.js is only an environment** - meaning that you have to do everything yourself. 

There is not a default HTTP server, or any server for that matter. This can be overwhelming for new users, but the payoff is a high performing web app. One script handles all communication with the clients. This considerably reduces the number of resources used by the application. 


## Modules

Node.js uses a modular architecture to simplify the creation of complex applications. Modules are akin to libraries in C, or units in Pascal. Each module contains alogically related set of functions. For example, the http module contains functions specific to HTTP. Node.js provides a few core modules out of the box to help you access files on the file system, create HTTP and TCP/UDP servers, and perform other useful functions.

Including a module is easy; simply call the **require()** function, like this:

	var http = require('http');

The require() function returns the reference to the specified module. In the case of this code, a reference to the http module is stored in the http variable.

In the above code, we passed the name of a module to the require() function. This causes Node to search for a node_modules folder in our application's directory, and search for the http module in that folder. If Node does not find the node_modules folder (or the http module within it), it then looks through the global module cache. You can also specify an actual file by passing a relative or absolute path, like so:

	var myModule = require('./myModule.js');

Modules are encapsulated pieces of code. 

**The code within a module is mostly private** - meaning that the functions and variables defined within them are only accessible from the inside of the module. You can, however, expose functions and/or variables to be used outside of the module. To do so, use the exports object and populate its properties and methods with the pieces of code that you want to expose. Consider the following module as an example:

	var PI = Math.PI;
	
	exports.area = function (r) {
	  return PI * r * r;
	};
	
	exports.circumference = function (r) {
	  return 2 * PI * r;
	};

This code creates a PI variable that can only be accessed by **code contained within the module; it is not accessible outside of the module.** Next, two functions are created on the exports object. **These functions are accessible outside of the module because they are defined on the exports object.** As a result, PI is completely protected from outside interference. Therefore, you can rest assured that area() and circumference() will always behave as they should (as long as a proper value is supplied for the r parameter).

## Global Scope

**Node is a JavaScript environment running in Google's V8 JavaScript engine.** As such, we should follow the best practices that we use for client-side development. 

For example, we should avoid putting anything into the global scope. That, however, is not always possible. The global scope in Node is GLOBAL (as opposed to window in the browser), and you can easily create a global variable of function by omitting the var keyword, like this:

	globalVariable = 1;
	globalFunction = function () { ... };

Once again, globals should be avoided whenever possible. So be careful and remember to use var when declaring a variable.

## NodeJS Installation

Naturally, we need to install Node before we can write and execute an app. Installation is straight forward, if you use Windows or OS X; the nodejs.org website offers installers for those operating systems. For Linux, use any package manager. Open up your terminal and type:

	sudo apt-get update
	sudo apt-get install node

or:

	sudo aptitude update
	sudo aptitude install node

Node.js is in sid repositories; you may need to add them to your sources list:

	sudo echo deb http://ftp.us.debian.org/debian/ sid main > /etc/apt/sources.list.d/sid.list

**But be aware that installing sid packages on older systems may break your system.** Be careful, and remove /etc/apt/sources.list.d/sid.list after you finish installing Node.

## Installing New Modules

**Node.js has a package manager, called Node Package Manager (NPM).** It is automatically installed as part of the Node.js installation. You use **NPM** to install other new modules. To install a module, open your terminal/command line, navigate to the desired folder, and execute the following command:

	npm install module_name

It doesn't matter what OS you have; the above command will install the module you specify in place of module_name directry.

## The Hello World App

Naturally, our first Node.js script will print the text 'Hello World!' to the console. Create a file, called hello.js, and type the following code:

	console.log('Hello World!');

Now let's execute the script. Open the terminal/command line, navigate to the folder that contains hello.js, and execute the following command:

	node hello.js

You should see 'Hello World!' displayed in the console.

## HTTP Server example application

Let's move on to a more complicated application.Lets start with the following code. Read the comments and then the explanation below:

		// Include http module.
		var http = require("http");
		
		// Create the server. Function passed as parameter 
		// is called on every request made.
		// request variable holds all request parameters
		// response variable allows you to do anything with response sent 
		// to the client.
		http.createServer(function (request, response) {
			// Attach listener on end event.
			// This event is called when client sent all data and is 
			// waiting for response.
			request.on("end", function () {
				// Write headers to the response.
				// 200 is HTTP status code (this one means success)
				// Second parameter holds header fields in object
				// We are sending plain text, so Content-Type should 
				// be text/plain
				response.writeHead(200, {
					'Content-Type': 'text/plain'
				});
				// Send data and end response.
				response.end('Hello HTTP!');
			});
		// Listen on the 8080 port.
		}).listen(8080);

This code is very simple. You can send more data to the client by using the response.write() method, before calling response.end(). 

Save this code as http.js and type this into your console:

	node http.js

Open up your browser and navigate to http://localhost:8080. You should see the text "Hello HTTP!" in the page.

## Handling URL Parameters

As I mentioned earlier, we have to do everything ourselves in Node, including parsing request arguments. This is, however, fairly simple. Take a look at the following code:

	// Include http module, 
	var http = require("http"), 
	// And url module, which is very helpful in parsing request parameters. 
		url = require("url"); 
	
	// Create the server. 
	http.createServer(function (request, response) { 
		// Attach listener on end event. 
		request.on('end', function () { 
			// Parse the request for arguments and store them in _get variable. 
			// This function parses the url from request and returns object representation. 
			var _get = url.parse(request.url, true).query; 
			// Write headers to the response. 
			response.writeHead(200, { 
				'Content-Type': 'text/plain' 
			}); 
			// Send data and end response. 
			response.end('Here is your data: ' + _get['data']); 
		}); 
	// Listen on the 8080 port. 
	}).listen(8080);

This code uses the parse() method of the **url** module, a core Node.js module, to convert the request's URL to an object. 

The returned object has a query property, which retrieves the URL's parameters. Save this file as get.js and execute it with the following command:

	node get.js

Then, navigate to 

	http://localhost:8080/?data=put_some_text_here 

in your browser. Naturally, changing the value of the data parameter will not break the script.

## Reading and Writing Files

To manage files in Node, we use the **fs** module (a core module). We can read and write files using the fs.readFile() and fs.writeFile() methods, respectively. 

I will explain the arguments after the following code:

	// Include http module,
	var http = require("http"),
	// And mysql module you've just installed.
	var	fs = require("fs");
	
	// Create the http server.
	http.createServer(function (request, response) {
		// Attach listener on end event.
		request.on("end", function () {
			// Read the file.
			fs.readFile("test.txt", 'utf-8', function (error, data) {
				// Write headers.
				response.writeHead(200, {
					'Content-Type': 'text/plain'
				});
				// Increment the number obtained from file.
				data = parseInt(data) + 1;
				// Write incremented number to file.
				fs.writeFile('test.txt', data);
				// End response with some nice message.
				response.end('This page was refreshed ' + data + ' times!');
			});
		});
	// Listen on the 8080 port.
	}).listen(8080);


Save this as files.js. Before you run this script, create a file named test.txt in the same directory as files.js.

This code demonstrates the **fs.readFile()** and **fs.writeFile()** methods. Every time the server receives a request, the script reads a number from the file, increments the number, and writes the new number to the file. 

The fs.readFile() method accepts three arguments: 
* the name of file to read, 
* the expected encoding, 
* and the callback function.

Writing to the file, at least in this case, is much simpler. 
We don't need to wait for any results, although you would check for errors in a real application. 

The fs.writeFile() method accepts the file name and data as arguments. It also accepts third and fourth arguments (both are optional) to specify the encoding and callback function, respectively.

Now, let's run this script with the following command:

	node files.js

Open it in browser (http://localhost:8080) and refresh it a few times. Now, you may think that there is an error in the code because it seems to increment by two. 

This isn't an error. Every time you request this URL, two requests are sent to the server. The first request is automatically made by the browser, which requests favicon.ico, and of course, the second request is for the URL (http://localhost:8080).

Even though this behavior is technically not an error, it is behavior that we do not want. We can fix this easily by checking the request URL. Here is the revised code:

	// Include http module,
	var http = require("http");
	// And mysql module you've just installed.
	var	fs = require("fs");
	
	// Create the http server.
	http.createServer(function (request, response) {
		// Attach listener on end event.
		request.on('end', function () {
			// Check if user requests /
			if (request.url == '/') {
				// Read the file.
				fs.readFile('test.txt', 'utf-8', function (error, data) {
					// Write headers.
					response.writeHead(200, {
						'Content-Type': 'text/plain'
					});
					// Increment the number obtained from file.
					data = parseInt(data) + 1;
					// Write incremented number to file.
					fs.writeFile('test.txt', data);
					// End response with some nice message.
					response.end('This page was refreshed ' + data + ' times!');
				});
			} else {
				// Indicate that requested file was not found.
				response.writeHead(404);
				// And end request without sending any data.
				response.end();
			}
		});
	// Listen on the 8080 port.
	}).listen(8080);

Test it now; it should work as expected.

## Reading and Writing to TCP socket

Node also makes an excellent TCP server. Here is an example that responds to all TCP connections with the message "Hello World" and then closes the connection. sample file : hello-tcp.js


	// Load the net module to create a tcp server.
	var net = require('net');
	
	// Creates a new TCP server. The handler argument is 
	// automatically set as a listener for the 'connection' event
	var server = net.createServer(function (socket) {
	
	  // Every time someone connects, tell them hello 
	  // and then close the connection.
	  console.log("Connection from " + socket.remoteAddress);
	  socket.end("Hello World\n");
	});
	
	// Fire up the server bound to port 7000 on localhost
	server.listen(7000, "localhost");
	
	// Put a friendly message on the terminal
	console.log("TCP server listening on port 7000 at localhost.");

## Reading and Writing to Router

Often you won't be using the node built-in libraries because they are designed to be very low level. This makes node quick, nimble, and easy to maintain, but is usually not enough to get started on a real world application. 

My first node framework is node-router. This example shows an HTTP server that responds with "Hello World" to all requests to "/" and responds with a 404 error to everything else. Sample File : hello-router.js


	// Load the node-router library by creationix
	var server = require('node-router').getServer();
	
	//
	// Configure our HTTP server to respond 
	// with Hello World the root request
	//
	server.get("/", function (request, response) {
	  response.simpleText(200, "Hello World!");
	});
	
	// Listen on port 8080 on localhost
	server.listen(8000, "localhost");

In order to test this, you will need to install the node-router library. 

	npm --save install node-router

You can also put the node-router.js file in your application directory and reference it locally. This command will add the node-router to the node-module directory. 

## Accessing MySQL Databases

Most traditional server-side technologies have a built-in means of connecting to and querying a database. With Node.js, you have to install a library. For this tutorial, I've picked the stable and easy to use node-mysql. 

The full name of this module is mysql@2.0.0-alpha2 (everything after the @ is the version number). Open your console, navigate to the directory where you've stored your scripts, and execute the following command:

	npm install mysql@2.0.0-alpha2

This command will download and install the module, and it also creates the node_modules folder in the current directory. Now let's look at how we can use this in our code; see the following example:

	// Include http module, 
	var http = require('http'); 
	// And mysql module you've just installed. 
	var mysql = require("mysql"); 
		 
	// Create the connection. 
	// Data is default to new mysql installation and should be 
	// changed according to your configuration. 
	var connection = mysql.createConnection({ 
		user: "root", 
		password: "", 
		database: "db_name"
	}); 
	
	// Create the http server. 
	http.createServer(function (request, response) { 
		// Attach listener on end event. 
		request.on('end', function () { 
			// Query the database. 
			connection.query('SELECT * FROM your_table;', 
					function (error, rows, fields) { 
				response.writeHead(200, { 
					'Content-Type': 'x-application/json' 
				}); 
				// Send data as JSON string. 
				// Rows variable holds the result of the query. 
				response.end(JSON.stringify(rows)); 
			}); 
		}); 
	// Listen on the 8080 port. 
	}).listen(8080);

Querying the database with this library is easy; simply enter the query string and callback function. 

In a real application, you should check if there were errors (the error parameter will not be undefined if errors occurred) and send response codes dependent upon the success or failure of the query. Also note that we have set the Content-Type to x-application/json, which is the valid MIME type for JSON. The rows parameter contains the result of the query, and we simply convert the data in rows to a JSON structure using the JSON.stringify() method.

Save this file as mysql.js, and execute it (if you have MySQL installed, that is):

	node mysql.js

Navigate to http://localhost:8080 in your browser, and you should be prompted to download the JSON-formatted file.

## Express

Express is a very popular application framework for building and running Node.js applications. You can create a new Express application using the Express Generator tool. 

The Express Generator is shipped as an NPM module and installed by using the NPM command line tool npm. The following command will install globally on your computer:

	npm install -g express-generator

The -g switch installs the Express Generator globally on your machine so you can run it from anywhere.

We can now create a new Express application called myExpressApp by running:

	express myExpressApp

This creates a new folder called myExpressApp with the contents of your application. To install all of the application's dependencies (again shipped as NPM modules), go to the new folder and execute npm install:

	cd myExpressApp
	npm install

At this point, we should test that our application runs. The generated Express application has a package.json file which includes a start script to run node ./bin/www. This will start the Node.js application running.

From a terminal in the Express application folder, run:

	npm start

The Node.js web server will start and you can browse to http://localhost:3000 to see the running application.

## MongoDB And Mongoose

Node.js and MongoDB are a pair made for each other.The ability to use JSON across the board and JavaScript makes development very easy. 

This is why you get popular stacks like the MEAN stack that uses Node, Express (a Node.js framework), MongoDB, and AngularJS.

CRUD is something that is necessary in most applications. We have to create, read, update, and delete information all the time.

#### What is Mongoose

Mongoose is an object modeling package for Node that essentially works like an ORM. 

Mongoose establishes connections to the MongoDB and facilitates using the commands for CRUD simply and easily. To use mongoose, make sure that you add it to you Node project by using the following command:

	npm install mongoose --save

Since we have the package, we need to grab it in our project:

	var mongoose = require('mongoose');

We also have to connect to a MongoDB database (either local or hosted):

	mongoose.connect('mongodb://localhost/myappdatabase');

Before we can handle CRUD operations, we will need a mongoose Model. 
These models are constructors that we define. They represent documents which can be saved and retrieved from our database.

***Mongoose Schema*** : The mongoose Schema is what is used to define attributes for our documents.

***Mongoose Methods***: Methods can also be defined on a mongoose schema. These are methods

See the example bellow;

	// grab the things we need
	var mongoose = require('mongoose');
	var Schema = mongoose.Schema;

	// create a schema
	var userSchema = new Schema({
		  name: String,
		  username: { type: String, required: true, unique: true },
		  password: { type: String, required: true },
		  admin: Boolean,
		  location: String,
		  meta: {
		    age: Number,
		    website: String
		  },
		  created_at: Date,
		  updated_at: Date
	});

	// the schema is useless so far
	// we need to create a model using it
	var User = mongoose.model('User', userSchema);

	// make this available to our users in our Node applications
	module.exports = User;

This is how a Schema is defined. We must grab mongoose and mongoose.Schema. Then we can define our attributes on our userSchema for all the things we need for our user profiles. 

Also notice how we can define nested objects as in the meta attribute.

The allowed SchemaTypes are:

<ul>
<li><b>String</b></li>
<li><b>Number</b></li>
<li><b>Date</b></li>
<li><b>Buffer</b></li>
<li><b>Boolean</b></li>
<li><b>Mixed</b></li>
<li><b>ObjectId</b></li>
<li><b>Array</b></li>
</ul>

We will then create the mongoose Model by calling mongoose.model. We can also do more with this like creating specific methods. This is a good place to create a method to hash a password.

The following example shows how to create and use Custom Method

	// grab the things we need
	var mongoose = require('mongoose');
	var Schema = mongoose.Schema;

	// create a schema
	var userSchema ...

	// custom method to add string to end of name
	// you can create more important methods like name validations or formatting
	// you can also do queries and find similar users 
	userSchema.methods.dudify = function() {

	  // add some stuff to the users name
	  this.name = this.name + '-dude'; 

	  return this.name;
	};

	// the schema is useless so far
	// we need to create a model using it
	var User = mongoose.model('User', userSchema);

	// make this available to our users in our Node applications
	module.exports = User;

Now we have a custom model and method that we can call in our code:

	// if our user.js file is at app/models/user.js
	var User = require('./app/models/user');
	
	// create a new user called chris
	var chris = new User({
	  name: 'Chris',
	  username: 'sevilayha',
	  password: 'password' 
	});
	
	// call the custom method. this will just add -dude to his name
	// user will now be Chris-dude
	chris.dudify(function(err, name) {
	  
		if (err) throw err;
	  	console.log('Your new name is ' + name);
	});
	
	// call the built-in save method to save to the database
	chris.save(function(err) {
	  if (err) throw err;
	
	  console.log('User saved successfully!');
	});

This is a very useless custom method, but the idea for how to create a custom method and use it stands. We can use this for making sure that passwords are hashed before saving, having a method to compare passwords, find users with similar attributes, and more.

#### Run a Function Before Saving

We also want to have a created_at variable to know when the record was created. We can use the Schema pre method to have operations happen before an object is saved.

Here is the code to add to our Schema to have the date added to created_at if this is the first save, and to updated_at on every save:

	// on every save, add the date
	userSchema.pre('save', function(next) {
	  // get the current date
	  var currentDate = new Date();
	
	  // change the updated_at field to current date
	  this.updated_at = currentDate;
	
	  // if created_at doesn't exist, add to that field
	  if (!this.created_at)
	    this.created_at = currentDate;
	
	  next();
	});

Now on every save, we will add our dates. This is also a great place to hash passwords to be sure that we never save plaintext passwords.

We can also define more things on our models and schemas like statics and indexes. Be sure to take a look at the mongoose docs for more information.

#### Create

We'll be using the User method we created earlier. The built-in save method on mongoose Models is what is used to create a user:

	// grab the user model
	var User = require('./app/models/user');
	
	// create a new user
	var newUser = User({
	  name: 'Peter Quill',
	  username: 'starlord55',
	  password: 'password',
	  admin: true
	});
	
	// save the user
	newUser.save(function(err) {
	  if (err) throw err;
	
	  console.log('User created!');
	});

#### Read

There are many reasons for us to query our database of users. We'll need one specific user, all users, similar users, and many more scenarios. Here are a few examples:

Find All

	// get all the users
	User.find({}, function(err, users) {
	  if (err) throw err;
	
	  // object of all the users
	  console.log(users);
	});

Find One

	// get the user starlord55
	User.find({ username: 'starlord55' }, function(err, user) {
	  if (err) throw err;
	
	  // object of the user
	  console.log(user);
	});

Find By ID

	// get a user with ID of 1
	User.findById(1, function(err, user) {
	  if (err) throw err;
	
	  // show the one user
	  console.log(user);
	});

Querying

You can also use MongoDB query syntax.

	// get any admin that was created in the past month
	
	// get the date 1 month ago
	var monthAgo = new Date();
	monthAgo.setMonth(monthAgo.getMonth() - 1);
	
	User.find({ admin: true }).where('created_at').gt(monthAgo).exec(function(err, users) {
	  if (err) throw err;
	
	  // show the admins in the past month
	  console.log(users);
	});

#### Update

Here we will find a specific user, change some attributes, and then re-save them.

Get a User, Then Update

	// get a user with ID of 1
	User.findById(1, function(err, user) {
	  if (err) throw err;
	
	  // change the users location
	  user.location = 'uk';
	
	  // save the user
	  user.save(function(err) {
	    if (err) throw err;
	
	    console.log('User successfully updated!');
	  });
	
	});

Remember that since we created the function to change the updated_at date, this will also happen on save.

Find and Update

An even easier method to use since we dont have to grab the user, modify, and then save. We are just issuing a mongodb findAndModify command.

	// find the user starlord55
	// update him to starlord 88
	User.findOneAndUpdate({ username: 'starlord55' }, 
			{ username: 'starlord88' },
	 		function(err, user) {
	
	  if (err) throw err;
	
	  // we have the updated user returned to us
	  console.log(user);
	});

Find By ID and Update

	// find the user with id 4
	// update username to starlord 88
	User.findByIdAndUpdate(4, { username: 'starlord88' }, 
				function(err, user) {
	  if (err) throw err;
	
	  // we have the updated user returned to us
	  console.log(user);
	});

#### Delete

Get a User, Then Remove

	// get the user starlord55
	User.find({ username: 'starlord55' }, function(err, user) {
	  if (err) throw err;
	
	  // delete him
	  user.remove(function(err) {
	    if (err) throw err;
	
	    console.log('User successfully deleted!');
	  });
	});


Find and Remove

	// find the user with id 4
	User.findOneAndRemove({ username: 'starlord55' }, function(err) {
	  if (err) throw err;
	
	  // we have deleted the user
	  console.log('User deleted!');
	});

Find By ID and Remove

	// find the user with id 4
	User.findByIdAndRemove(4, function(err) {
	  if (err) throw err;
	
	  // we have deleted the user
	  console.log('User deleted!');
	});



### Sample code

This section provides a code sample using Mongoose

<hr>
api.js
<hr>


	/* The API controller
	   Exports 3 methods:
	   * post - Creates a new thread
	   * list - Returns a list of threads
	   * show - Displays a thread and its posts
	*/


	var Thread = require('../models/thread.js');
	var Post = require('../models/post.js');

	exports.post = function(req, res) {
	    new Thread({title: req.body.title, author: req.body.author}).save();
	}

	exports.list = function(req, res) {
	  Thread.find(function(err, threads) {
	    res.send(threads);
	  });
	}

	// first locates a thread by title, then locates the replies by thread ID.
	exports.show = (function(req, res) {
	    Thread.findOne({title: req.params.title}, function(error, thread) {
	        var posts = Post.find({thread: thread._id}, function(error, posts) {
	          res.send([{thread: thread, posts: posts}]);
	        });
	    })
	});

app.js
<hr>

	// The main application script, ties everything together.

	var express = require('express');
	var mongoose = require('mongoose');
	var app = module.exports = express.createServer();

	// connect to Mongo when the app initializes
	mongoose.connect('mongodb://localhost/norum');

	app.configure(function(){
	  app.use(express.bodyParser());
	  app.use(express.methodOverride());
	  app.use(app.router);
	});

	// set up the RESTful API, handler methods are defined in api.js
	var api = require('./controllers/api.js');
	app.post('/thread', api.post);
	app.get('/thread/:title.:format?', api.show);
	app.get('/thread', api.list);

	app.listen(3000);
	console.log("Express server listening on port %d", app.address().port);


post.js
<hr>
	// The Post model

	var mongoose = require('mongoose')
   		,Schema = mongoose.Schema
   		,ObjectId = Schema.ObjectId;

	var postSchema = new Schema({
    	thread: ObjectId,
    	date: {type: Date, default: Date.now},
    	author: {type: String, default: 'Anon'},
    	post: String
	});

	module.exports = mongoose.model('Post', postSchema);

thead.js
<hr>

	// The Thread model

	var mongoose = require('mongoose')
	  , Schema = mongoose.Schema;

	var threadSchema = new Schema({
	    title:  String,
	    postdate: {type: Date, default: Date.now},
	    author: {type: String, default: 'Anon'}
	});

	module.exports = mongoose.model('Thread', threadSchema);

### For More Information see:

* [Mongoose Home](http://mongoosejs.com/)
* [MongooseJS Docs](http://mongoosejs.com/docs/)

# Express

ExpressJS arguably is the most popular web framework in the NodeJS community. 

In this section we create a simple web application using ExpressJS and JadeS. 

Before we can code any application we need to install ExporessJS in our application environement. to install expresssJs, run the folowing command on the command line:

	npm --save install express

Generally, an ExpressJs application will have the following components;

<ul>
<li>creat and instance of app</li>
<li>create middleware</li>
<li>create routes</li>
<li>start listening on the given port</li>
</ul>

Now start coding the sample application;

	var http = require('http');
	var express = require('express');
	var app = express();

	app.set('view engine', 'jade');
	app.set('views', './views');

	app.get('/', function(req, res) {
  		res.render('index', {title: 'Welcome', message: 'Hello ExpressJS!'});
	});

	app.listen(3000);
	console.log('Running Express...');

Save the above in app.js.

Our above implementation assumes that we have a folder named "views". To run the code execute the followings on the command line:

	node app

Creating an Instance

	var http = require('http');
	var express = require('express');
	var app = express();

	app.listen(3000);
	console.log('Running Express...');

In the above code, you will require the express module so that we can use express for a variety of things. 

The last portion of the code will run the server and listen to port 3000.

Now, browse to; http://localhost:3000/. you will see the followings: 

	Cannot GET /

This is of course we don’t have anything to accept any request from /.

### Creating Routes

We will have to insert routes before the creation of the server.

	app.get('/', function(req, res) {
	  res.send('<h1>Welcome to ExpressJS!</h1>');
	});

If you haven’t stopped the server, you can stop and start it for our changes to take place. This will render Welcome to ExpressJS! on our browser.

	$ curl http://localhost:3000
	<h1>Welcome to ExpressJS!</h1>

Creating Views

Now let’s send a more serious response. We will use a view engine for our views.

	app.set('view engine', 'jade');
	app.set('views', './views');

We will be using jade as our view engine which is the easiest to implement with express. The next line tells our app that we have views in the views folder.

Now lets’ create our view in JadeJS

	html
	  head
	    title Welcome
	  body
	    #container
	      Hello ExpressJS!

Save the above code in a file named index.jade in the views folder.

As you can see our template looks a bit like slim, a really great templating engine used as an option in Rails development.

Replace our route with the following:

	app.get('/', function(req, res) {
 	 res.render('index');
	});

Our app would now render our view file, index.jade

Sending values to our View

Now to make our content more dynamic, we will be sending values to our view file.

	app.get('/', function(req, res) {
	  res.render('index', {'title': 'Welcome', 'message': 'Hello ExpressJS!'});
	});

The extra parameter of the render method makes the index value available as a variable in our view file. Now, let us change our view file.

	html
	  head
	    title #{title}
	  body
	    #container
	      p #{message}

This will in effect render something like this:

	<html>
	  <head>
	    <title>Welcome</title>
	  </head>
	  <body>
	    <div id="container">
	      <p>Hello ExpressJS!</p>
	    </div>
	  </body>
	</html>


## Conclusion

Every function in Node.js is asynchronous.

Node.js requires extra work, but the payoff of a fast and robust application is worth it. If you don't want to do everything on the lowest level, you can always pick some framework, such as >Express, to make it easier to develop applications.

Node.js is a promising technology and an excellent choice for a high load application. 

