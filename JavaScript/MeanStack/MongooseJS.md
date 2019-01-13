# MongooseJS

### For more information See

* [MongooseJS Home Page](http://mongoosejs.com/)
* [Mongoose NPM Page](https://www.npmjs.com/package/mongoose)

## NodeJS Modules

The following Modules are usually added to a NodeJS application:

* Express
* Mongoose
* body-parser

The following commands are used to start an application

	npm init
	npm install --save express mongoose body-parser

## MongooseJS Applications

Following Steps steps:

* require the package in the NodeJS
* create a schema
* create an Object
* export the schema for other modules to use

The following is an example:

	var mongoose = require("mongoose");
	var schema = mongoose.Schema;

	var sampleObject = new schema({
		name : String,
		keyword: Array,
		published : Boolean
	});
	
	module.export = mongoose.model('Book',sampleObject);
 

To establish connection to the MongoDB:

* create a variable pointing to the instance of MongoDB
* DBname is a name of schema you are using
* connect to the database:


The followings is an example;


	var myDB = "mongodb://localhost/DBname";
	mongoose.connect(myDB);


## Mongoose Schema