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
* [Asynchronous Callbacks](##asynchronous-callbacks)
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
```

## Asynchronous Callbacks

> An asynchronous function takes a callback function as a parameter that is executed *after* the primary function is complete.

This can occur on a specific delay (i.e. setTimeout), or for a function that will take a while to process (i.e. fs.readfile).

### setTimeout

```js
setTimeout(callback, delay);
```

```js
setTimeout(() => {
  console.log("Delay complete");
}, 2000);
```
Once the delay has been processed, the callback function (i.e. console.log()) will then execute.


## Promises

> Represents the eventual result of an asynchronous operation. The `.then` method registers callbacks to receive either a promises eventual value or the reason why the promise cannot be fulfilled.

```js
nextISSTimes()
.then((passTimes) => {
  printPassTimes(passTimes);
})
.catch((error) => {
  console.log("Didn't work.", error.message);
});
```

### Promise Function

```js
new Promise (funtion(resolve[, reject]) {
  val value = doSomething;
  if (thingWorked) {
    resolve(value);
  } else if (somethingWentWrong) {
    reject();
  }
}).then(function(value) {
  //success!
  return nextThing(value);
}).catch(rejectFunction);
```

```js
.catch() = .then(undefined, rejectFunction)
```

## Classes

> Classses are blueprints (templates) that we use to create instances of objects.

> A class describes what the object is going to be and we can create new objects using the class

```js
class Pizza {

  constructor(size, crust) {
    this.size = size;
    this.crust = crust;
    this.toppings = ['cheese'];
  }

  addToppings(topping) {
    this.toppings.push(topping);
  }

}

let pizza1 = new Pizza('large', 'thin');
```
Class names should be a capitalized noun.

If the parameters are left empty when creating a new Pizza class, the object will still be created but the parameters will be undefined.

### Inheritance

```js
class Person {

}

class Student extends Person {

}

class Mentor extends Person {

}

let student1 = new Student;
let mentor1 = new Mentor;
```
Both student1 and mentor1 will have the Person constructors and access to Person methods.

Person --> Superclass

Student, Mentor --> Subclasses


