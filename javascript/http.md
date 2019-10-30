# HTTP

> HyperText Transfer Protocol

Contains details such as URL Structure, request headers, response codes, etc.

A protocol used to read and write "resources" (data) in a simple text-based manner.

## Request Module

`npm install request`

> npm package that will make HTTP requests simpler, and more professional than the net module

```js
const request = require('request');

request('http://www.google.com', (error, response, body) => {
  console.log('error', error);
  console.log('statusCode', response && response.statusCode);
  console.log('body', body); // prints the html from google.com
});
```

## JSON

> JavaScript Object Notation

Built on two structures: 
- A collection of name/value pairs
- An ordered list of values

```js
{
  "name": "New York City",
  "population": 8491079,
  "area_codes": [212, 347, 646]
}
```

### Serialization

The process which converts objexts (or data structures) into a format that can be stored or transmitted bewteen computers (typically as a string of text).

> `JSON.parse()` --> Parse a string as JSON, optionally transform the produced value and its properties, and return a value.

> `JSON.stringify()` --> Return a JSON string corresponding to the specified value.


## API

> Application Programming Interface

Sets the requirements that govern how one application can talk to another.

API's do this by "exposing" some of a program's internal function to the outside world.

```js
const request = require('request');

request('<url with options>', (error, response, body) => {
  console.log('error', error);
  console.log('statusCode', response && response.statusCode);
  console.log('body', body); // body contains the full "object" returned by the API
});
```

## Express

`npm install express`

> Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.

```js
const express = require('express');
const app = express();
const PORT = 8080;

app.get("/", (req, res) => {
  res.send("Hello!");
});

app.get("/hello", (req, res) => {
  res.send("<html><body>Hello World!</body></html>");
});

app.listen(PORT, () => {
  console.log(`Listening on port ${PORT}`);
});
```

* Define any number of "route" options

#### Route Parameters 

> Names URL segments that are used to capture the values specified at their position in the URL.

Route Path  --> /flights/:from-to

Request URL --> http://localhost:3000/flights/LAX-SFO

req.params  --> {} "from": "LAX", "to": "SFO" }

#### Response Methods
> Can send a response to the client, and terminate the request-response cycle

* res.end() --> end response process
* res.json() --> send a JSON response
* res.redirect() --> redirect a request
* res.send() --> send a response of various types

## EJS Template Engine

`npm install ejs`

> EJS is a simple templating language that lets you generate HTML markup with plain JavaScript.

#### File Structure

* views
  * partials
    * footer.ejs
    * header.ejs
    * head.ejs
  * pages
    * index.ejs
    * about.ejs
* package.json
* server.js

All .ejs template files are written in HTML and CSS

`<% include ../partials/header %>`
\
--> installs the header.ejs file into the desired page

`<h1><%= greeting %></h1>`
\
--> uses the value of the greeting variable from server.js

## Cookies

An HTTP server can tell a client to remember certain keys and values ("cookies") using the Set-Cookie header in an HTTP response. In all subsequent HTTP requests from the client to the server, these keys and values are included in the Cookie header. In essence, the server can ask a client to "keep reminding" the server of the client's identity (or other information) with every subsequent request. 

`npm install cookie-parser`

> Parse Cookie header and populate req.cookies with an object keyed by the cookie names.

`res.cookie('username', req.body.username);`
\
--> sets cookie with a key of username, and value associatd with req.body.username

`res.clearCookie('username');`
\
--> clears the cookie of the key/value associated with username