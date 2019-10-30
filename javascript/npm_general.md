# npm & Packages

> npm --> package manager of Node.js (self-contained library)

Virtually all Node.js projects have a `package.json` file
- Contains basic attributes such as project name, description, author
- scripts: {
  myscripts: {......}
  test: {......}
} --> allows us to run commands using an alias
`npm run myscript`
- dependencies: {
  mocha: "^4.6.10"
  chai: "^3.4.7"
} --> dependencies list the packages that need to be installed

`npm init` initializes directory to use npm, and creates .json file

`npm init -y` sets .json file to default categories

`npm install chalk` installs the chalk package, update .json dependencies, creates node_modules to store pacakge

`npm publish --access public` publishes a public package to npm

## Common Packages

`npm i mocha --save-dev` --> testing framework

`npm i chai --save-dev` --> assertions for Mocha tests

`npm i express` --> web application framework

`npm i ejs` --> template framework to be used with Express

`npm i body-parser` --> parse incoming request bodies before event handler

`npm i cookie-parser` --> parse cookie header, and populate req.cookies with an object keyed by the cookie names

`npm i nodemon --save-dev` --> keeps server running while changes are made to code