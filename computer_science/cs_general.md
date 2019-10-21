# Computer Science General

## Contents
* [Recursion](##recursion)
* 

## Recursion
Recursion is an alternative to looping, which accomplishes the same thing in a different way.

```js
function countEvenToTwelve(num) {
  if (num <= 12) {
    console.log(num);
  }
  countEvenToTwelve(num + 2);
}

countEvenToTwelve(0);
```
The above function calls itself - until it doesn't.

> Every recursive function must **stop** calling itself at some point.

* We refer to number `<= 12` as the recursive case, because as long as it is true the function will continue to call iteself.
* We refer to the number `> 12` as the base case. If true, the function will stop calling itself.