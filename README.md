MCAuth.js
=========

A [NodeJS](http://nodejs.org/) library for validating Minecraft account information.
Created for the serverside of [Miney](https://github.com/medsouz/Miney-Client).

Installation
------------

You can install using `npm install mcauth`.

Usage
-----

**hasPaid**
To check if a user has bought Minecraft you can use mcauth.hasPaid:
```javascript
var mcauth = require("mcauth");
mcauth.hasPaid("medsouz", function(paid){
	if(paid){
		console.log(username + ' has purchased Minecraft!');
	}else{
		console.log(username + ' has not purchased Minecraft.');
	}
});
```

**checkSessionId**
When a user connects to a server they use a string called a sessionId to connect, you can validate a sessionId using mcauth.checkSessionId:
```javascript
var mcauth = require("mcauth");
mcauth.checkSessionId("medsouz", "-SessionId Here-", function(valid){
	if(valid){
		console.log('Login is valid');
	}else{
		console.log('Login is invalid');
	}
});
```

**isNameValid**
To run a regexp check to make sure a username is a valid account name for Minecraft you can use mcauth.isNameValid:
```javascript
var mcauth = require("mcauth");
mcauth.isNameValid("medsouz", function(valid){
    if(valid){
        console.log('Username is valid');
    }else{
        console.log('Username has an invalid length or contains invalid characters.');
    }
});
```