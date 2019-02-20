
DBAS - Database As a Service or Hosting Yourself

MongoDB Deployment - mLab

Cloud Provider - AWS

Figure out Connections String 

-> variables.env.sample to mongodb from mLab
To connect using a driver via the standard MongoDB URI

create a db user with username and password
Overview
The various methods by which you can connect to your mLab-hosted database are described here: https://docs.mlab.com/connecting/#connect-string
We also provide some troubleshooting advice for issues you might encounter while trying to establish a connection.


Markdown: https://guides.github.com/features/mastering-markdown/

#MogoDB GUI: mongo db compass

//For Offline Work  - Install MongoDB on Computer - use home-brew
Homebrew is a free and open-source software package management system that simplifies the installation of software on Apple's macOS operating system and Linux.
	brew update
	brew install mongodb
	mongo --version

In terminal runs mongoDB locally on computer: mongod

#REVIEWING THE STARTER FILES

Built on Express - unopinionated, minimalist web framework
Mongoos -> Mongo

##start.js -> imports mongoose, checks node version, dotenv package: environmental variables - where store sensitive information: passwords, tokens, should never go in GitHub repo because based on environment you are on
->variables.env


##npm start 
-> package.json has scripts that are run see "start" scripts -> kick off node process that starts with start.js 
and npm run watch process watch package called nodemon to monitor files anytime change to JS files, will restart the whole server again...every
and run assets webpack 

#On Port 7777, in browser http://localhost:7777/

#Express - Routing
When people go to a url need to do actions.
1.Import Express. const express = require('express');
2.Grab router off of express. const router = express.Router();
3.Define all of your routes -> index.js -> const routes = require(./routes/index);
	app.use('/',routes); //go to forward slash anything then hit routes

##Router 
(Express) When user goes to url, app needs to do things
//import express and router
Get url with a callback function that is run whenever anyone visits specific url. This function will give you 3 things: 
1. request -> an object with information coming in that returns; 
2. response -> an object with methods for sending data back to the user;
3. next -> middlewear file

```javascript
//import express and router
const express = require('express');
const router = express.Router();
//define routes ... 
router.get('/', (req,res)=> { 
	//everytime you console.log in express, will see result in terminal
	console.log('Hey!!!');
	const wes = { name: 'Wes', age: 100 };
	//res.send('Hey! It works!');
	//push data out as json
	res.json(wes);
	//can pull data from url as part of the request
	//req.query -> all query parameters
	//res.send(req.query.paramterNeeded);
});
module.exports = router;
//importing routes from this exported file
```

#Information on Node
Node.js came into existence when the original developers of JavaScript extended it from something you could only run in the browser to something you could run on your machine as a standalone application.

Both your browser JavaScript and Node.js run on the V8 JavaScript runtime engine. This engine takes your JavaScript code and converts it into a faster machine code. Machine code is low-level code which the computer can run without needing to first interpret it.

Node.js® is a JavaScript runtime built on Chrome’s V8 JavaScript engine.
Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient.

I/O refers to input/output. It can be anything ranging from reading/writing local files to making an HTTP request to an API.

Consider a scenario where we request a backend database for the details of user1 and user2 and then print them on the screen/console. The response to this request takes time, but both of the user data requests can be carried out independently and at the same time.

Non-blocking I/O
On the other hand, using a non-blocking request, you can initiate a data request for user2 without waiting for the response to the request for user1. You can initiate both requests in parallel.

This non-blocking I/O eliminates the need for multi-threading since the server can handle multiple requests at the same time.

- What is event-driven programming? Basically, it’s a different way of thinking about your program flow. The flow of your program is defined by the events that are taking place. (see below for more details)
- What is I/O? Input/Output
- Difference between blocking & non-blocking software development Blocking methods execute synchronously and non-blocking methods execute asynchronously.

##Environmental Variables
Shouldn't go in github repo. Is based on environment you are on, needs to work everywhere app is run. Externalize all environment specific aspects of your app and keep your app encapsulated. Use any place code will change based on the environment. Node provides acess to all existing environment variables by creating an env object as property of the process global object. 
console.log(process.env); 
//Outputs all node.js process is aware of. 
IE: Which HTTP port to listen on
What path and folder your files are located in, that you want to serve
Pointing to a development, staging, test, or production database
Other examples might be URLs to server resources, CDNs for testing vs. production, and even a marker to label your app in the UI by the environment it lives in.

##ES6 Promieses Async & Await
