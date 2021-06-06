# JavaScript
## Loops and iteration

### 1. for statement
#### A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop.

#### A for statement looks as follows:
>for ([initialExpression]; [conditionExpression]; [incrementExpression])
  statement

### 2. do...while statement
#### The do...while statement repeats until a specified condition evaluates to false.

#### A do...while statement looks as follows:

>do
  statement
while (condition);

### 3. while statement
#### A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:

>while (condition)
  statement

### 4. for...in statement 

#### The for...in statement iterates a specified variable over all the enumerable properties of an object. For each distinct property, JavaScript executes the specified statements. A for...in statement looks as follows:

>for (variable in object)
  statement

### 5. for...of statement

#### The for...of statement creates a loop Iterating over iterable objects (including Array, Map, Set, arguments object and so on), invoking a custom iteration hook with statements to be executed for the value of each distinct property.

  >for (variable of object)
  statement

## Arrays

#### Although it may be tempting to use this as a way to iterate over Array elements, the for...in statement will return the name of your user-defined properties in addition to the numeric indexes.

## labeled statement
#### A label provides a statement with an identifier that lets you refer to it elsewhere in your program. For example, you can use a label to identify a loop, and then use the break or continue statements to indicate whether a program should interrupt the loop or continue its execution.

#### The syntax of the labeled statement looks like the following:

`label :
   statement`
   
## break statement 
#### Use the break statement to terminate a loop, switch, or in conjunction with a labeled statement.
* hen you use break without a label, it terminates the innermost enclosing while, do-while, for, or switch immediately and transfers control to the following statement.
* When you use break with a label, it terminates the specified labeled statement.
The syntax of the break statement looks like this:
`break;
break [label];
`

Learn more about :[Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators) , [Loops and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
