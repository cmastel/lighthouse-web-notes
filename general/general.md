# General Notes

## eslint
`eslint file_name.js` uses ESLint to check the javascript formatting of file_name.js

## MarkDown
MarkDown Cheat Sheet:
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet


## Keyboard Shortcuts
`CMD + CTRL + SPACE` access emoji keyboard

`CMD + ~` switch between open windows of the same app (i.e. Chrome)

`CMD + CTRL + F` (VS Code) to find (search) in all files of an open project

`CMD + T` opens a new tab (Terminal, Chrome, Finder)

`CMD + W` closes the current tab (Chrome, VS Code)

`CMD + OPT + Left/Right` moves between tabs in an open window (Chrome, VS Code, Terminal)


## CRUD and BREAD

**C**reate --> Add new record { HTTP: POST, SQL: INSERT }
\
**R**ead --> Retrieve the value of a record { HTTP: GET, SQL: SELECT }
\
**U**pdate --> Update a record's value { HTTP: PUT, SQL: UPDATE }
\
**D**elete --> Delete a record { HTTP: DELETE, SQL: DELETE }

*or*

**B**rowse --> photoApp.com/photos
\
**R**ead --> photoApp.com/photos/:id
\
**E**dit --> photoApp.com/photos/:id/edit
\
**A**dd --> photoApp.com/photos/upload
\
**D**elete --> photoApp.com/photos/:id/delete

Above paths for photoApp can correspond to HTTP Express Routes

## REST

> Represational State Transfer

REST is a set of conventions and practices in web development that deals with accessing and manipulating resources over HTTP.

A resource can be an abstraction of an object or data. In practice, resources are referenced using a URL.

`/users/1` --> a collection (group of resources) is typically defined, where a single unit (id) is then part of.



## URL

> Uniform Resource Locator

A URL is a specifc type of Uniform Resource Identifier (URI)

`URI = scheme:[//authority]path[?query][#fragment]`

* scheme --> i.e. http, ftp, mailto


## Algorithms

Complexity is the number of elementary operations that a function takes to complete. Typically based on "worst-case" scenario.

examples of elementary operations:
- let x = a;
- c = a + b;
- console.log(aReallyLargeString);

Complexity can be calculated for functions:
```js
let result = 0; // 1

for (
  let i = 0; // 1
  i < array.length; // n + 1
  i++ // n
) {
  let number = array[i]; // n
  result += number; // n
}

console.log(result); // 1
```
--> Total complexity = 4n + 4

Static complexity --> No increase in time regardless of the amount of data
\
Linear complexity --> Time increases directly in relation to amount of data (i.e. looking at each value of an array)
\
Logarithmic --> Time increases less and less the larger a dataset grows, also call **Binary** algorithm (ripping a phone book)
\
Quadratic --> Time increases exponentially (n<sup>2</sup>), typically from nested for loops


### Big O Notation

> When we evaluate an algorithm using Big O notation, we only care about arbitrarily large input.

2n<sup>2</sup> + 6n + 10 --> O(n<sup>2</sup>)

- Remove constants
- Remove non-dominant terms
- 