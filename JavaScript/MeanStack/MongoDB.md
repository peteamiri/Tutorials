# MongoDB

### For more information See

* [Mongodb Manual](https://docs.mongodb.com/manual/)
* [Nosql Explained](https://www.mongodb.com/nosql-explained)
* [Wiki NoSQL](https://en.wikipedia.org/wiki/NoSQL)

## MongoDB Basics

* Schema
* Database
* Collections
* Documents

* MongoDB does not use Tables, instead it uses Documents. Documents are described in Json-like structured call **Bson**
* Due to lack of tables, it means there are no-relational, and you can not join tables.  

Primary difference between JSON and BSON is the quotation mark for both key-value.


## NoSQL Databases

## Basic Commands

Starting the database:

	mongod (mongodb deamon)

to connect to the database:

	mongo (shell a.k.a "MongoShell" to connect to the database)

Common Commands
	
	show dbs (lists the existing databases)
	use <database_name> (creates db if db not exists, uses it if exists)
	show collections (displays the existing document types in the given db)<co
	db.<collection-name>.find() (displays all the documents within a given collections)
	db.<collection-name>.find().pretty() (to make document more human readable)


system.indexes is a system generated document. It is created at the database creation time.

_id is a system generated field, it is created every time a document is added to a collection.  

	// Insert data into car collection
	db.car.insert({
	    name: 'honda',
	    make: 'accord',
	    year: '2010'
	})
	
	// Update the collection car set name--> ford where name is honda 
	db.car.update({
	    name: 'honda'
	    },
	    { $set: {
	     name: 'ford'
	    }
	})
	
	// Update the collection car set transmission --> automatic where name 
	// is /honda 
	db.car.update({
	    name: 'ford'
	    },
	    { $set: {
	     transmission: 'automatic'
	    }
	}, {$upsert: true})
	
	// Inserts a new document into collections
	db.users.insert({
    	name: 'jo',
    	email: 'me5@me.com',
    	password: '444',
    	role: 'admin'
	})

### Data Types


## MongoosJS
