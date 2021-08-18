# FUNCTIONAL PROGRAMMING

### What is functional programming?

![functional programming](https://i.ytimg.com/vi/PyKZMY-_TI8/maxresdefault.jpg)

Is the process of building software by composing pure functions, **avoiding shared state**, **mutable data**, and **side-effects**. Functional programming is **declarative** rather than imperative, and application state flows through pure functions.

### What is a pure function and how do we know if something is a pure function?
A pure function is a function which:
* Given the same inputs, always returns the same output.
* Has no side-effects
Pure functions have lots of properties that are important in functional programming, including **referential transparency** *(you can replace a function call with its resulting value without changing the meaning of the program).*

### What are the benefits of a pure function?
1. The function always returns the same value for the same inputs.

2. Evaluation of the function has no side effects. Side effects refer to changing other attributes of the program not contained within the function, such as changing global variable values or using I/O streams.

### What is immutability?
Immutability is a central concept of functional programming because without it, the data flow in your program is lossy. State history is abandoned, and strange bugs can creep into your software.
For more on the significance of immutability, see [The Dao of Immutability.](https://medium.com/javascript-scene/the-dao-of-immutability-9f91a70c88cd).

### What is Referential transparency?
Referential transparency it can be replaced with its corresponding value (and vice-versa) without changing the program's behavior.[1] This requires that the expression be pure, that is to say the expression value must be the same for the same inputs and its evaluation must have no side effects.

## module in NodeJS
### What is a module?

![module](https://parallelcodes.com/wp-content/uploads/2020/11/node-js-custom-module-example.png)

Module in Node.js is a simple or complex functionality organized in single or multiple JavaScript files which can be reused throughout the Node.js application.

### What does the word ‘require’ do?

```
var http = require('http');

var server = http.createServer(function(req, res){

  //write code here

});

server.listen(5000);
```
In the above example, require() function returns an object because http module returns its functionality as an object, you can then use its properties and methods using dot notation e.g. `http.createServer()`.
In this way, you can load and use Node.js core modules in your application.

### How do we bring another module into the file the we are working in?
The *module.exports* is a special object which is included in every JS file in the Node.js application by default. Use **module.exports** or **exports** to expose a function, object or variable as a module in Node.js.

### What do we have to do to make a module available?
1. Need to download and install Node.js on your computer
2.  Creating a package.json file.
You can create a package.json file by running a CLI questionnaire or creating a default package.json file.
* On the command line, navigate to the root directory of your package.

> cd /path/to/package

* Run the following command:

> npm init

* Answer the questions in the command line questionnaire.

3. Create the file that will be loaded when your module is required by another application
In the file, add a function as a property of the exports object. This will make the function available to other code:

```
exports.printMsg = function() {
  console.log("This is a message from the demo package");
}
```
4. Test your module


## Things I want to know more about
* Nodejs and Module