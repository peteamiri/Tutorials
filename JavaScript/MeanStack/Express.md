# Express

## More Information

* [ExpressJS Home](http://expressjs.com/)
* [FAQ](http://expressjs.com/en/starter/faq.html)
* [Routing](http://expressjs.com/en/guide/routing.html)
* [Github Site](https://github.com/expressjs)
* [Express Github](https://github.com/expressjs/express)
* [Examples](https://github.com/expressjs/express/tree/master/examples)
* [https://github.com/azat-co/expressjsguide](https://github.com/azat-co/expressjsguide)
* [Nodejs Express Framework Tutorial](http://www.tutorialspoint.com/nodejs/nodejs_express_framework.htm)
* [Tutorials: Build a complete mvc website with ExpressJs](https://code.tutsplus.com/tutorials/build-a-complete-mvc-website-with-expressjs--net-34168)
* [express-complete-tutorial-part-1/](https://codeforgeek.com/2014/10/express-complete-tutorial-part-1/)
* [Good Staarting Point](https://www.youtube.com/watch?v=k_0ZzvHbNBQ&list=PLillGF-RfqbYRpji8t4SxUkMxfowG4Kqp)
* [https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)
* [https://github.com/getify/You-Dont-Know-JS/blob/master/README.md](https://github.com/getify/You-Dont-Know-JS/blob/master/README.md)
* [http://htmldog.com/guides/html/](http://htmldog.com/guides/html/)
* [http://htmldog.com/guides/javascript/](http://htmldog.com/guides/javascript/)
* [http://htmldog.com/guides/css/](http://htmldog.com/guides/css/)
* [w3schools](https://www.w3schools.com/)

## Tutorials

* [https://glebbahmutov.com/blog/express-sessions/](https://glebbahmutov.com/blog/express-sessions/)
* [https://www.airpair.com/express/posts/expressjs-and-passportjs-sessions-deep-dive](https://www.airpair.com/express/posts/expressjs-and-passportjs-sessions-deep-dive)
* [https://glebbahmutov.com/blog/solid-expressjs-server/](https://glebbahmutov.com/blog/solid-expressjs-server/)
* [https://glebbahmutov.com/blog/tightening-node-project/](https://glebbahmutov.com/blog/tightening-node-project/)
* [https://github.com/if-itb/MEAN-Todo-Tutorial](https://github.com/if-itb/MEAN-Todo-Tutorial)
* [https://github.com/mrlynn/meanstore](https://github.com/mrlynn/meanstore)

## Installation

Global Installation
```
	npm install -g express
```
Local / Application level installation
```
	npm install --save express
```
Start the a project
```
	mkdir <Application Name>
	cd <Application Name>
```
To create Package.json
```
	npm init (reply to all the prompts)
	npm install --save express (adds the express as dependency to package.json)
```
Additional Packages you may need:
```
	$ npm install body-parser --save
	$ npm install cookie-parser --save
	$ npm install multer --save
```
* **body-parser** − This is a node.js middleware for handling JSON, Raw, Text and URL encoded form data.

* **cookie-parser** − Parse Cookie header and populate req.cookies with an object keyed by the cookie names.

* **multer** − This is a node.js middleware for handling multipart/form-data
The install -save will add the express to the project and install the express package in the node-module directory in your project directory.


The following is an example of a generated package.json,
```js
	{
	  "name": "SampleApp",
	  "version": "1.0.0",
	  "description": "this is a sample application",
	  "main": "app.js",
	  "scripts": {
	    "test": "echo \"Error: no test specified\" && exit 1"
	  },
	  "author": "",
	  "license": "ISC",
	  "dependencies": {
	    "express": "^4.15.3"
	  }
	}
```
## Creating the first Application

Add the following to the app.js file,
```js
	// Import express
	const express = require('express');

	// set express to a variable
	const app = express();

	// get the body-parse
	var bodyParser = require('body-parser');

	// Set up a Router
	app.get('/', function (req, res) {
 		 res.send('Hello World!');
	});

	// Start Listening on the given port
	app.listen(3000, function () {
  		console.log('Example app listening on port 3000!');
	});
```
run the application using the command line
```
	node app.js
```
or install the nodemon and run the app.js
```
	npm installl -g nodemon
	nodemon app.js
```
Then, load http://localhost:3000/ in a browser to see the string "Hello World!".

nodemon as the name indicates monitors all the files in project. As soon as it detects any changes it restart the application. This helps to see the effect of the changes to the application in almost real-time.

## Express Generator

Use the application generator tool, express-generator, to quickly create an application skeleton.

The express-generator package installs the express command-line tool. Use the following command to do so:
```
	$ npm install express-generator -g
```
Display the command options with the -h option:
```
	$ express -h

  	Usage: express [options] [dir]

	Options:

    -h, --help          output usage information
        --version       output the version number
    -e, --ejs           add ejs engine support
        --hbs           add handlebars engine support
        --pug           add pug engine support
    -H, --hogan         add hogan.js engine support
    -v, --view <engine> add view <engine> support (ejs|hbs|hjs|jade|pug|twig|vash) (defaults to jade)
    -c, --css <engine>  add stylesheet <engine> support (less|stylus|compass|sass) (defaults to plain css)
        --git           add .gitignore
    -f, --force         force on non-empty directory
```
Examples:
```
	$ express --view=pug myapp
	$ cd myapp
	$ npm install
	$ set DEBUG=myapp:* & npm start (or simply npm start)
```
Then, load http://localhost:3000/ in a browser to see the string "Welcome to Express".

The following is the generated app.js;
```js
	var express = require('express');
	var path = require('path');
	var favicon = require('serve-favicon');
	var logger = require('morgan');
	var cookieParser = require('cookie-parser');
	var bodyParser = require('body-parser');

	var index = require('./routes/index');
	var users = require('./routes/users');

	var app = express();

	// view engine setup
	app.set('views', path.join(__dirname, 'views'));
	app.set('view engine', 'pug');

	// uncomment after placing your favicon in /public
	//app.use(favicon(path.join(__dirname, 'public', 'favicon.ico')));
	app.use(logger('dev'));
	app.use(bodyParser.json());
	app.use(bodyParser.urlencoded({ extended: false }));
	app.use(cookieParser());
	app.use(express.static(path.join(__dirname, 'public')));

	app.use('/', index);
	app.use('/users', users);

	// catch 404 and forward to error handler
	app.use(function(req, res, next) {
	  var err = new Error('Not Found');
	  err.status = 404;
	  next(err);
	});

	// error handler
	app.use(function(err, req, res, next) {
	  // set locals, only providing error in development
	  res.locals.message = err.message;
	  res.locals.error = req.app.get('env') === 'development' ? err : {};

	  // render the error page
	  res.status(err.status || 500);
	  res.render('error');
	});

	module.exports = app;
```

Major Components of Express;

* Routing
* Middleware
* Viewer

### Common Porject Layout
```
	./myapp
	  ./public 		-- static files
	  ./modules 	-- modules I made for reusability
	  ./routes 		-- like controllers
	  ./log  		-- app log file
	  ./views 		-- ejs views
	  ./config 		-- config.development.js, config.global.js
	  ./templates 	-- email templates (text/html in ejs)
	  ./pid 		-- for server
	  ./init 		-- git post-receive hook for deploy
	  ./models 		-- mongoose schemas
```
## Express Methods

<table>
<tr>
<th>Property</th>
<th>Method Description</th>
</tr>
<tr>
<td>
app.set(name, value)</td><td>Sets app-specific properties
</tr>
<tr>
<td>
app.get(name)</td><td> Retrieves value set by app.set()
</td>
</tr>
<tr>
<td>
app.enable(name)</td><td> Enables a setting in the app
</td>
</tr>
<tr>
<td>
app.disable(name)</td><td> Disables a setting in the app
</td>
</tr>
<tr>
<td>
app.enabled(name)</td><td> Checks if a setting is enabled
</td>
</tr>
<tr>
<td>
app.disabled(name)</td><td> Checks if a setting is disabled
</td>
</tr>
<tr>
<td>
app.configure([env],callback)</td><td> Sets app settings conditionally based on the development environment
</td>
</tr>
<tr>
<td>
app.use([path], function)</td><td> Loads a middleware in the app
</td>
</tr>
<tr>
<td>
app.engine(ext, callback)</td><td> Registers a template engine for the app
</td>
</tr>
<tr>
<td>
app.param([name], callback)</td><td> Adds logic to route parameters
</td>
</tr>
<tr>
<td>
app.VERB(path, [callback...], callback)</td><td> Defines routes and handlers based on HTTP verbs
</td>
</tr>
<tr>
<td>
app.all(path, [callback...], callback)</td><td> Defines routes and handlers for all HTTP verbs
</td>
</tr>
<tr>
<td>
app.locals</td><td> The object to store variables accessible from
any view
</td>
</tr>
<tr>
<td>
app.render(view, [options],callback)</td><td> Renders view from the </td>
</tr>
<tr>
<td>
app.routes</td><td> A list of routes defined in the app
</td>
</tr>
<tr>
<td>
app.listen()</td><td> Binds and listen for connections
</tr>
</table>

## See also:

* [Expressjs: how to structure an application](https://stackoverflow.com/questions/5778245/expressjs-how-to-structure-an-application/7350875#7350875)
* [Expressjs sample Apps layout](https://stackoverflow.com/questions/13036286/express-js-sample-apps)
* [Actual Application](https://github.com/focusaurus/peterlyons.com)
* [Studynotes.org actual implementation](https://github.com/feross/studynotes.org)

### Basic routing

Routing refers to determining how an application responds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, and so on).

Each route can have one or more handler functions, which are executed when the route is matched.

Route definition takes the following structure:

	app.METHOD(PATH, HANDLER)

Where:

app is an instance of express. METHOD is an HTTP request method, in lowercase.
PATH is a path on the server.

* **GET** method requests a representation of the specified resource. Requests using GET should only retrieve data and should have no other effect. The W3C has published guidance principles on this distinction, saying, "Web application design should be informed by the above principles, but also by the relevant limitations.

* **HEAD** method asks for a response identical to that of a GET request, but without the response body. This is useful for retrieving meta-information written in response headers, without having to transport the entire content.

* **POST** method requests that the server accept the entity enclosed in the request as a new subordinate of the web resource identified by the URI. The data POSTed might be, for example, an annotation for existing resources; a message for a bulletin board, newsgroup, mailing list, or comment thread; a block of data that is the result of submitting a web form to a data-handling process; or an item to add to a database.

* **PUT** method requests that the enclosed entity be stored under the supplied URI. If the URI refers to an already existing resource, it is modified; if the URI does not point to an existing resource, then the server can create the resource with that URI.[15]

* **DELETE** method deletes the specified resource.

* **TRACE** method echoes the received request so that a client can see what (if any) changes or additions have been made by intermediate servers.

* **OPTIONS** method returns the HTTP methods that the server supports for the specified URL. This can be used to check the functionality of a web server by requesting '*' instead of a specific resource.

* **CONNECT** method converts the request connection to a transparent TCP/IP tunnel, usually to facilitate SSL-encrypted communication (HTTPS) through an unencrypted HTTP proxy.[17][18] See HTTP CONNECT tunneling.

* **PATCH**  method applies partial modifications to a resource.[19]

* **All** Additionally express offers all as a catch-all routing.


HANDLER is the function executed when the route is matched.
This tutorial assumes that an instance of express named app is created and the server is running. If you are not familiar with creating an app and starting it,
see the Hello world example.

The following examples illustrate defining simple routes.

Respond with Hello World! on the homepage:
```js
	app.get('/', function (req, res) {
	  res.send('Hello World!')
	})
```
Respond to POST request on the root route (/), the application’s home page:
```js
	app.post('/', function (req, res) {
	  res.send('Got a POST request')
	})
```
Respond to a PUT request to the /user route:
```js
	app.put('/user', function (req, res) {
	  res.send('Got a PUT request at /user')
	})
```
Respond to a DELETE request to the /user route:
```js
	app.delete('/user', function (req, res) {
	  res.send('Got a DELETE request at /user')
	})
```
For more details about routing, see the routing guide.
```js
	var express = require('express');
	var app = express();

	// This responds with "Hello World" on the homepage
	app.get('/', function (req, res) {
   		console.log("Got a GET request for the homepage");
   		res.send('Hello GET');
	})

	// This responds a POST request for the homepage
	app.post('/', function (req, res) {
   		console.log("Got a POST request for the homepage");
   		res.send('Hello POST');
	})

	// This responds a DELETE request for the /del_user page.
	app.delete('/del_user', function (req, res) {
   		console.log("Got a DELETE request for /del_user");
   		res.send('Hello DELETE');
	})

	// This responds a GET request for the /list_user page.
	app.get('/list_user', function (req, res) {
   		console.log("Got a GET request for /list_user");
   		res.send('Page Listing');
	})

	// This responds a GET request for abcd, abxcd, ab123cd, and so on
	app.get('/ab*cd', function(req, res) {
   		console.log("Got a GET request for /ab*cd");
   		res.send('Page Pattern Match');
	})

	// Listner to start Main Application Loop
	var server = app.listen(8081, function () {
   		var host = server.address().address
   		var port = server.address().port
   		console.log("Example app listening at http://%s:%s", host, port)
	})
```

## Viewers

Express Generator offers three viewer types when generating a code.
```
	$ express myapp ( for pug/Jade viewer engine)
	$ express --view=pug myapp ( for pug/Jad viewer engine)
	$ express --view=Jade myapp ( for pug/Jad viewer engine)
	$ express --view=ejs myapp ( for EJS viewer engine)
	$ express --view=hbd myapp ( for HandleBar viewer engine)
	$ express --view=twig myapp ( for pug viewer engine)
	$ express --view=vash myapp ( for s viewer engine)
```

The following sections discuss the three commonly used viewers, namely Pug/Jade,HandleBar, and finally EJS

### Jade / Pug

### EJC

### HandleBar


## Serving static files in Express

To serve static files such as images, CSS files, and JavaScript files, use the express.static built-in middleware function in Express.

Pass the name of the directory that contains the static assets to the express.static middleware function to start serving the files directly. For example, use the following code to serve images, CSS files, and JavaScript files in a directory named public:
```
	app.use(express.static('public'))
```
Now, you can load the files that are in the public directory:
```
	http://localhost:3000/images/kitten.jpg
	http://localhost:3000/css/style.css
	http://localhost:3000/js/app.js
	http://localhost:3000/images/bg.png
	http://localhost:3000/hello.html
```
Express looks up the files relative to the static directory, so the name of the static directory is not part of the URL.
To use multiple static assets directories, call the express.static middleware function multiple times:
```js
	app.use(express.static('public'))
	app.use(express.static('files'))
```
Express looks up the files in the order in which you set the static directories with the express.static middleware function.

**NOTE**: For best results, use a reverse proxy cache to improve performance of serving static assets.

To create a virtual path prefix (where the path does not actually exist in the file system) for files that are served by the express.static function, specify a mount path for the static directory, as shown below:
```js
app.use('/static', express.static('public'))
```
Now, you can load the files that are in the public directory from the /static path prefix.
```
	http://localhost:3000/static/images/kitten.jpg
	http://localhost:3000/static/css/style.css
	http://localhost:3000/static/js/app.js
	http://localhost:3000/static/images/bg.png
	http://localhost:3000/static/hello.html
```
However, the path that you provide to the express.static function is relative to the directory from where you launch your node process. If you run the express app from another directory, it’s safer to use the absolute path of the directory that you want to serve:
```js
	app.use('/static', express.static(path.join(__dirname, 'public')))
```
