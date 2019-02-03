# MeanStack

MEAN is an acronym made up of commonly used technologies for an all JavaScript web stack. You don’t have to use this combination and there are many alternative choices, especially on the client-side such as Backbone, Ember etc.

This particular combination of tools has generated a lot of traction in the enterprise area and is framework based, making it a good place to start.

The key components are:

* MongoDB (Database)
* ExpressJS (Web Framework)
* AngularJS (Front-end Framework)
* NodeJS (Application Server)
* Passport
* Jade


### For more information See

* [MeanJS](http://meanjs.org/)
* [MeanJS Docs](http://meanjs.org/docs.html)
* [Introduction to MeanStack](https://www.ibm.com/developerworks/library/wa-mean1/index.html)
* [Mean Stack Tutorial For Beginners](http://fullstacktutorials.net/mean-stack-tutorial-for-beginners/)
* [Various Crash Courses](https://www.youtube.com/playlist?list=PLillGF-RfqbYeckUaD1z6nviTp31GLTH8)
* [Youtube Tutorial](https://www.youtube.com/playlist?list=PLillGF-RfqbZMNtaOXJQiDebNXjVapWPZ)
* [mherman.org](http://mherman.org/blog/2014/12/31/node-and-mongoose-a-primer/)
* [Learn Jade](http://learnjade.com/)
* [learn jade](http://learnjade.com/tour/intro/)

Stack Information

* [mongodb](https://www.mongodb.com/)
* [ExpressJS](https://expressjs.com/)
* [Angular](https://angular.io/)
* [NodeJS](https://nodejs.org/)
* [npmJS](https://www.npmjs.com/)
* [github](https://github.com/)

Wiki

* [MongoDB](https://en.wikipedia.org/wiki/MongoDB)
* [Express.js](https://en.wikipedia.org/wiki/Express.js)
* [AngularJS](https://en.wikipedia.org/wiki/AngularJS)
* [Node.js](https://en.wikipedia.org/wiki/Node.js)
* [NPM](https://en.wikipedia.org/wiki/Npm_(software))
* [GitHub](https://en.wikipedia.org/wiki/GitHub)

* This is a good resource [hackhands.com](https://hackhands.com/how-to-get-started-on-the-mean-stack/)

#The MEAN Stack

* MongoDB - Database. MongoDB is a document-oriented NoSQL database. It stores data in JSON-like format and performs SQL-like queries against it.

* Express - Web framework that runs on NodeJS which allows us to build web applications and APIs endpoints. It provides HTML template solutions (jade, ejs, handlebars, etc.) and CSS precompilers (less, stylus, compass, etc.).
Middlewares are added to ExpressJS stack using app.use, app.get, app.delete, app.post, or app.update.

* AngularJS - Frontend framework.

* Node.js - Server platform. It's Javascript running outside the browser.

These are some of the advantages of a MEAN stack:

* Single language is used in the whole application
* Support for the MVC pattern
* JSON is used for transfering data
* Node.js's huge module library
* Open source so you can tweak it to your preferences

##1. MongoDB

MongoDB is the leading NoSQL database.

* What is NoSQL?
	* [wikipedia](https://en.wikipedia.org/wiki/NoSQL)
* Why NoSQL?

Store data in the distributed systems to make the Cloud work
Handle the unstructured data for social networking sites to work
Change database schemas rapidly as demands evolve while adopting Agile model

##2. Express

Express is a node framework that makes the developer’s job much easier in creating Node projects.

Express and Node go hand in hand. Express code is typically part of the Node code.

Express.js is a minimal and flexible Node.js web application framework, providing a robust set of features for building single-page and multi-page, and hybrid web applications, as well as web-services. It is relatively minimal with many features available as plugins.

Express.js systems are highly configurable, which allows developers to pick freely whatever libraries they need for a particular project.

Express.js is a web framework based on the core Node.js **http** module and Connect (http://www.senchalabs.org/ connect/) components. The components are called middleware and they are the cornerstones of the framework philosophy configuration over convention.

### 2.1 Middleware

Middleware is a stack of processors that runs on a request made to the server. We can have any number of middleware that will process the request one by one in a serial fashion. We may alter the request input, log output, add data and pass it to the **next()** middleware in the chain.

##3. Angular 2

Angular is a front-end component that implements single page application (SPA).

SPA is a very important and hot concept in the web development industry. SPA gives the ability to run the most of the application in the client browser.

##4. Node.js

Node.js is a platform for running JavaScript on the server side;

* It provides environement for JavaScript runtime to easily building fast, scalable network applications.
* It uses an event-driven, non-blocking I/O model that makes it lightweight and efficient.
* It is perfect for data-intensive real-time applications that run across distributed devices.

It is literally the same JavaScript engine (named V8) that runs inside of Google Chrome, except that with Node.js, we can run JavaScript from the command line instead of in our browser.

Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine for easily building fast, scalable network applications.

While Node has become a popular choice among developers to build powerful web applications, it is also poised to replace Java, PHP, Ruby, etc.

Typically Node runs in the server as the back end.

Actually, JavaScript the programming language has no native capabilities for Document Object Model (DOM) manipulation or for making Ajax requests. Browsers provide DOM APIs so that we can do that sort of thing with JavaScript, but outside of the browser JavaScript loses those capabilities.

Node.js is really two things: a runtime environment and a library.

Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.

event-driven means that we can register some function to some event and that function will then be executed once the event is triggered. Here is an example (code from Delving into Node.js and Express web framework):

* See [hackhands.com](https://hackhands.com/delving-node-js-express-web-framework/)

Node.js was created by Ryan Dahl and it's basically a platform built on Chrome's JavaScript runtime called V8, whose greatest advantage over other JavaScript engines is the compiling of JavaScript code to native machine code before executing it. It uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.

### None blocking
Node.js is built upon libuv, a cross-platform library that abstracts **apis/syscalls** for asynchronous (non-blocking) input/output provided by the supported OSes (Unix, OS X and Windows at least).

**Asynchronous IO:**
In this programming model open/read/write operation on devices and resources (sockets, filesystem, etc.) managed by the file-system don't block the calling thread (as in the typical synchronous c-like model) and just mark the process to be notified when new data or events are available.

In case of a web-server-like app, the process is then responsible to figure out which request/context the notified event belongs to and proceed processing the request from there. Note that this will necessarily mean you'll be on a different stack frame from the one that originated the request to the OS as the latter had to yield to a process' dispatcher in order for a single threaded process to handle new events.

Node.js tackles the problem leveraging JavaScript's language features called closures.

Every function that requests IO has a signature like function(...parameters..., callback) and needs to be given a callback that will be invoked when the requested operation is completed.

**Closure: **

Javascript's support for closures allows us to use variables we've defined in the outer (calling) function inside the body of the callback - this allows to keep state between different functions that will be invoked by the node runtime independently.
```js
	function parent() {
	    var message = 'Hello Javascript Closure';
	    function child() {
	        alert (message);
	    }
	    return child;
	}
	var closureObj = parent();

	closureObj(); //this will alert Hello Javascript Closure
```
The parent() function returns the child() function, and the child() function is called after the parent() function has already been executed.

A closure is not only the function, but also the environment in which the function was created (which may be counter intuitive because usually the parent() function's local variables should only exist while the function is being executed).

In this case, the closureObj() is a closure object that consists of the child() function and the environment variables that existed when the closure was created, including the message variable.

##5. NPM – Public Repository

The open source projects/modules/utilities and its documentation are kept in the NPM “Node.js package manager”.

Use npm to install, share, and distribute code; manage dependencies in your projects; and share & receive feedback with others.

NPM is the largest ecosystem of open source libraries in the world.

It is used to install/share code, manage dependencies in your projects, and share/receive feedback with others.

Any time a Node project is used, the common code base will be downloaded from NPM.

* [NPM Docs](https://docs.npmjs.com/)


##6. Github

NPM is closely linked to Github, the largest open source community in the world.

There are millions of open source projects on GitHub. GitHub is mostly used for code. In addition to source code, GitHub also supports many other features
including:

* Documentation
* Issue tracking

Most of the NPM codes are stored in the Github.

# Passport

Passport is authentication middleware for Node. It is designed to serve for a singule purpose: authenticate requests.

In modern web applications, single sign-on using an OAuth provider such as Facebook or Twitter has become a popular authentication method. Services that expose an API often require token-based credentials to protect access.

Passport recognizes that each application has unique authentication requirements. Authentication mechanisms, known as ***strategies***, are packaged as individual modules. Applications can choose which strategies to employ, without creating unnecessary dependencies.

	app.post('/login', passport.authenticate('local',
					{ successRedirect: '/',
                      failureRedirect: '/login' }));

## Strategies

[Use this as a starting point](http://www.bogotobogo.com/MEAN-Stack/MEAN-Stack-MongoDB-ExpressJS-AngularJS-NodeJS-Authentication-Passport-App.php)
[http://mherman.org](http://mherman.org/blog/2015/01/31/local-authentication-with-passport-and-express-4/#.VhFrFurd88o)

[hackhands.com](https://hackhands.com/mongodb-crud-mvc-way-with-passport-authentication/)

### passport-local Passport strategy
Let's create a project - passport-local

# Jade

The Jade templating language is an elegant and practical language heavily influenced by Haml. Originally it was created in nodejs as a module but is now implemented in many languages: Node, Python, Scala, Ruby, Java, and PHP.
