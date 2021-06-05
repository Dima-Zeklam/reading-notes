# JavaScript 

## JavaScript Expressions and operators

###  1. Assignment operators
#### An assignment operator assigns a value to its left operand based on the value of its right operand. The simple assignment operator is equal `(=)`, which assigns the value of its right operand to its left operand. That is, `x = y` assigns the value of `y` to `x`.


Name                    |	Shorthand operator   |  Meaning
------------------------|----------------------|-----------
Assignment              |	x = y	               | x = y

- Destructuring
>var foo = ['one', 'two', 'three'];

 >// without destructuring

 >var one   = foo[0];

  >var two   = foo[1];

 >var three = foo[2];

  >// with destructuring

  >var [one, two, three] = foo;




### 2. Bitwise Operators

Name                    |	Shorthand operator   |  Meaning
------------------------|----------------------|-----------
Left shift assignment   | x <<= y	           | x = x << y 
Right shift assignment| 	x >>= y              |	x = x >> y
Unsigned right shift assignment|	x >>>= y	|x = x >>> y
Bitwise AND assignment|	x &= y               	|x = x & y
Bitwise XOR assignment|	x ^= y	               | x = x ^ y
Bitwise OR assignment	|x = y	| x = x \| y

### 3. Comparison operators
#### A comparison operator compares its operands and returns a logical value based on whether the comparison is true.


  Operator       | 	Description    |  Comparing| return
-----------------|-----------------|-----------|--------
== |	equal to	| x == 8 |	false	
| | | x == 5	|true	
| | | x == "5"	|true	
===	| equal value and equal type|	x === 5	|true	
| | |x === "5"|	false	
!=	|not equal	|x != 8	|true	
!==	 |not equal value or not equal type|	x !== 5|	false	
|||x !== "5"|	true	
| | | x !== 8 |	true	
\> |	greater than|	x > 8|	false	
\< |	less than|	x < 8	|true	
\>= |	greater than or equal to|	x >= 8	|false	
<= |	less than or equal to|x <= 8|	true

### 4. Logical operators
Name                    |	Shorthand operator   |  Meaning
------------------------|----------------------|-----------
Logical AND assignment|x &&= y	|x && (x = y)
Logical OR assignment|	x \|\|= y	 | x  \|\| (x = y)
Logical nullish assignment	|x ??= y          |	x ?? (x = y)


### 5. Arithmetic operators 

Name                    |	Shorthand operator   |  Meaning
------------------------|----------------------|-----------
Addition assignment	    |x += y                |	x = x + y
Subtraction assignment  |	x -= y               |x = x - y
Multiplication assignment|	x *= y             |	x = x * y
Division assignment	    | x /= y               |x = x / y
Remainder assignment    |	x %= y               |	x = x % y
Exponentiation assignment|	x \**= y         	| x = x \** y

### 6. Nullish coalescing operator (??)
#### The nullish coalescing operator (??) is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand.

#### This can be contrasted with the logical OR (||) operator, which returns the right-hand side operand if the left operand is any falsy value, not only null or undefined. In other words

**Example**

`const foo = null ?? "default string";`

`console.log(foo); // expected output: "default string"`


`const baz = 0 ?? 1 ;`

`console.log(baz); // expected output: 0`


## Functions
#### Functions are one of the fundamental building blocks in JavaScript. A function in JavaScript is similar to a procedure—a set of statements that performs a task or calculates a value, but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output.

- For example, the following code defines a simple function named square:

 > function square(number) { return number * number;
}
 
- Such a function can be anonymous; it does not have to have a name. For example, the function square could have been defined as:
 > const square = function(number) { return number * number }

 > var x = square(4) // x gets the value 16

- The eval() function evaluates JavaScript code represented as a string.

### Nested functions and closures
#### To summarize:

- The inner function can be accessed only from statements in the outer function.

- The inner function forms a closure: the inner function can use the arguments and variables of the outer function, while the outer function cannot use the arguments and variables of the inner function.

## Control flow
The control flow is the order in which the computer executes statements in a script.

Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops. 


### read more about   [Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#recursion) , [Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects) , [Statements (Control flow) ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling).

