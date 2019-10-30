# Mocha & Chai 

> Mocha is a JavaScript testing framework

> Chai is an assertion library

npm account: https://www.npmjs.com/settings/cmastel/packages


`npm install mocha chair --same-dev`

This command installs the two libraries and adds them to the dependencies script in the .json file

```js
// package.json
"scripts": {
  "test": "mocha" 
}
```

Update the test script so that it can run mocha directly wih:

`npm test`


## Typical test.js file

```js
const assert = require('chai').assert;
const functionToTest = require('./functionToTest.js');

describe('functionToTest', function() {

  it('should return 2 for 1 + 1', function() {
    assert.equal(functionToTest(1, 1), 2);
  });
});
```

