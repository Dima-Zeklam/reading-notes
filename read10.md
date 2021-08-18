# In memory storage

## Understanding the JavaScript Call Stack
### 1. What is a ‘call’?
Call is to invoke a routine in a programming language. Calling a routine consists of specifying the routine name and, optionally, parameters.
### 2. How many ‘calls’ can happen at once?
Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.
### 3. What does LIFO mean?
**"LIFO"** stands for last-in, first-out, meaning that the most recently produced items are recorded as sold first.
### 4. Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

![stack](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d3/Call_stack_layout.svg/1024px-Call_stack_layout.svg.png)

```
function add(a, b) {
    return a + b;
}

function average(a, b) {
    return add(a, b) / 2;
}

let x = average(10, 20);
```
### 5.What causes a Stack Overflow?
The most-common cause of stack overflow is excessively deep or infinite recursion, in which a function calls itself so many times that the space needed to store the variables and information associated with each call is more than can fit on the stack.

## JavaScript Call Stack

### 1. What is a ‘refrence error’?
This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

```
foo = 'Hello' // Uncaught ReferenceError: foo is not defined
let foo
```
### 2. What is a ‘syntax error’?
This occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

> JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1

### 3. What is a ‘range error’?
Trying to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

```
var foo= []
foo.length = foo.length -1 // Uncaught RangeError: Invalid array length
```
### 4. What is a ‘tyep error’?
This occurs when you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

```
var foo = {}
foo.bar // undefined
foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined
```
### 5. What is a breakpoint?
When a programmer creates code they can add what is known as a breakpoint. A breakpoint is a point in the program where the code will stop executing.
### 6. What does the word ‘debugger’ do in your code?
![debugger](https://miro.medium.com/max/1400/1*F8zI019d4DUxu2P4rj5Syw.jpeg)
A debugger is a software tool that can help the software development process by identifying coding errors at various stages of the operating system or application development.

## Things I want to know more about
* JavaScript Debugging
