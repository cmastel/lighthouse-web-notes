# Javascript General

## Contents
* [Command Line Arguments](##command-line-arguments)
* [Template Literal](##template-literals)
* [Conditional (ternary) Operator](##conditional-(ternary)-operator)
* [Looping Through Objects](##looping-through-objects)
* [array.map()](##array.map())
* [array.filter()](##array.filter())
* [Callback Functions](##callback-functions)
* [Modules](##modules)
* 



## Command Line Arguments 
```javascript
const args = process.argv
```
`args` is then an array that contains the Command Line Arugments


## Template Literals
```javascript
console.log(`This is a string and a ${variable}.`);
```
Outputs the (already defined) variable into the string. Can include multiple variables into a single console.

## Conditional (ternary) Operator
```javascript
console.log(condition $ trueValue : falseValue)
```
This operator is frequently used as a shortcut to an If statement.

## Looping Through Objects

```javascript
var planetMoons = {
  mercury: 0,
  venus: 0,
  earth: 3
};

for (var planet in planetMoons) {
  var numberOfMoons = planetMoons[planet];
  console.log('Planet: ' + planet + 'Moons: ' + numberOfMoons);
};
```

In order to avoid some unexpected results while looping through Objects,
adding the following method is recommended:

```javascript
for (var planet in planetMoons) {
  if (planetMoons.hasOwnProperty(planet)) {
    .......
    ......
  };
};
```

## array.map()

> The map() method creates a new array with the results of calling a provided function on every element in the calling array

```js
var array1 = [1, 4, 9, 16];

const map1 = array1.map(x => x * 2);
console.log(map1);

--> [2, 8, 18, 32]
```

## array.filter()

> The filter() method will iterate over an array of values in order to filter down the values into a smaller list

```js
const numbers = [1, 2, 3, 4, 5, 6];
const evens = numbers.filter(function(num) {
  return (num % === 0);
});
console.log(evens);

---> [2, 4, 6]
```

## Callback Functions
> callback is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action

```js
function greeting(name) {
  alert("Hello" + name);
};

function processUserInput(callback) {
  var name = prompt("Please enter your name.");
  callback(name);
};

processUserInput(greeting);
```

## Modules


```js
const sayHelloTo = require('./myModule');
// This says that the current file (i.e. main.js) requires what is exported from myModule (the .js isn't required)

module.exports = sayHelloTo;
// This says that from the myModule.js file the sayHelloTo function is exported
