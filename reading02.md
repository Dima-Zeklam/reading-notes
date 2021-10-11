# Arrays, Loops, Imports

## Java Packages
A package in Java is used to group related classes. Think of it as a folder in a file directory. We use packages to avoid name conflicts, and to write a better maintainable code.

![Java Packages](https://simplesnippets.tech/wp-content/uploads/2018/04/packages-in-java-programming-featured-image.jpg)

* Creating a package in java is quite easy, simply include a package command followed by name of the package as the first statement in java source file.
* To import java package into a class, we need to use java import keyword which is used to access package and its classes into the java program.

##### Package syntax

```

package illustration;

import java.awt.*;

public class Drawing {
    . . .
}
```


##### Common imports
**There are 166 packages containing 3279 classes and interfaces in Java 5.**

Package | Description 
-------|-------------
* import java.awt.*; |	Common GUI elements.
* import java.awt.event.*; |	The most common GUI event listeners.
* import javax.swing.*;	 |More common GUI elements. Note "javax".
* import java.util.*;	| Data structures (Collections), time, Scanner, etc classes.
* import java.io.*; |	Input-output classes.
* import java.text.*;	| Some formatting classes.
* import java.util.regex.*; |	Regular expression classes.

##### Static imports in Java 5
The static import feature of Java 5 facilitate the java programmer to access any static member of a class directly. There is no need to qualify it by the class name.

* Advantage of static import:
Less coding is required if you have access any static member of a class oftenly.

* Disadvantage of static import:
If you overuse the static import feature, it makes the program unreadable and unmaintainable.

**Example:**

```
import static java.lang.System.*;    
class StaticImportExample{  
  public static void main(String args[]){  
     
   out.println("Hello");//Now no need of System.out  
   out.println("Java");  
  
 }   
}  
```

### Loops
In programming languages, **looping is a feature which facilitates the execution of a set of instructions until the controlling Boolean-expression evaluates to false.**
Here are the types of loops that we can find in Java:  

1. **For Loop When you know exactly how many times you want to loop through a block of code, use the for loop instead of a while loop.**
The syntax of the for loop is:

>for (initialization; Boolean-expression; step) 
>  statement;

2. **for-each loop It is mainly used to traverse the array or collection elements.**
 
* It starts with the keyword for like a normal for-loop.
* Instead of declaring and initializing a loop counter variable, you declare a variable that is the same type as the base type of the array, followed by a colon, which is then followed by the array name.
* In the loop body, you can use the loop variable you created rather than using an indexed array element. 
* It’s commonly used to iterate over an array or a Collections class (eg, ArrayList)
Syntax: 


> for (type var : array) { 
>    statements using var;
> }

*for loop flow chart :*

![for loop](https://static.javatpoint.com/cpages/images/forloop.png)

3. **while loop Loops can execute a block of code as long as a specified condition is reached.**
The syntax of the while loop is:

>while (Boolean-expression) 
>    statement;
 
4. **Do-while loop The do-while loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.**
The syntax of the do-while is:
> do {
>   statement;
> } while (Boolean-expression);



