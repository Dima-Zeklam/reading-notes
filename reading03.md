# primitive and reference data type, Exceptions and Scanner in java

**Java provides two types of data types primitive and reference data type.**
#### Reference Data Types in Java
Reference Data Types also know as non-primitive data types, It contains the address (or reference) of dynamically created objects.All reference types are a subclass of type java.lang.Object. 

**Examples of reference data types**

Reference Type |	Description
-------------- | ---------------
Class	| It is a set of instructions. It describes the content of the object.
Array |	It provides the fixed-size data structure that stores the elements of the same type.
Annotations	| It provides a way to associate metadata with program elements.
Interface |	It is implemented by Java classes.
Enumeration |	It is a special kind of class that is type-safe.

#### Reference vs Primitive Data Types

Reference Type |	Primitive Type
-------------- |----------------
It is not pre-defined except the String. |	It is pre-defined in Java.
All reference type begins with Uppercase letter. |	All primitive type begins with a lowercase letter.
Non-primitive types have all the same size. |	The size of a primitive type depends on the data type.
It is used to invoke or call methods. | We cannot invoke the method with a primitive type.
It can be null.	| It cannot be null. It always has value.  
Examples of reference data types are class, Arrays, String, Interface, etc. | Examples of primitive data types are int, float, double, Boolean, long, etc. 
Example: Demo d1;	| Example: int num=78;

#### Memory footprint of the JVM
* Memory footprint refers to the amount of main memory that a program uses or references while running
* The JVM divides its memory into two main categories: heap memory and non-heap memory.

* Primitives are stored by value in the memory while Non-Primitives (Objects) are stored by reference.

*An example of how Primitives are stored:*

```
let a = 5
let b = a
console.log(a) // 5
console.log(b) // 5
console.log(a === b) // true
a = 10
console.log(a) // 10
console.log(b) // 5
console.log(a === b) // false
```
**Every time we decide to declare a new variable using a primitive data type we are creating a new address in memory for that value.**


*An example of how  Non-Primitives (Objects) are stored:*

```
let a = [10]
let b = a
console.log(a === b) // true
a.push(10)
console.log(a) // [10, 10]
console.log(a === b) // true
```
**It’s not creating a new address for a value, just a pointer to the object. If you modify a variable pointing to the address, you’re actually modifying the data stored inside the address itself.**

**So the objects in Java are slower and have a bigger memory impact than their primitive analogs.**

#### Performance
**Important influence factors to the performance of a Java program can be separated into two main parts:**

* Memory Consumption of the Java program

* Total runtime of a program

### Exceptions

An event that occurs during the execution of a program that disrupts the normal flow of instructions is called an exception. 

##### Hierarchy of Java Exception classes
![Hierarchy of Java Exception classes](https://static.javatpoint.com/core/images/hierarchy-of-exception-handling.png)


##### Types of Java Exceptions
1. Checked Exception
2. Unchecked Exception
3. Error

![ Types of Java Exceptions](https://static.javatpoint.com/core/images/types-of-exception-handling.png)

##### Exception Keywords

Keyword |	Description
--------|-------------
try	| The "try" keyword is used to specify a block where we should place an exception code. It means we can't use try block alone. The try block must be followed by either catch or finally.
catch |	The "catch" block is used to handle the exception. It must be preceded by try block which means we can't use catch block alone. It can be followed by finally block later.
finally	| The "finally" block is used to execute the necessary code of the program. It is executed whether an exception is handled or not.
throw |	The "throw" keyword is used to throw an exception.
throws	| The "throws" keyword is used to declare exceptions. It specifies that there may occur an exception in the method. It doesn't throw an exception. It is always used with method signature.

##### Syntax of Java try-catch

> try{    
> //code that may throw an exception    
> }catch(Exception_class_Name ref){}    

##### Syntax of try-finally block
>try{    
>//code that may throw an exception    
>}finally{}    

Example 

```
public class TryCatchExample1 {  
  
    public static void main(String[] args) {  
          
        int data=50/0; //may throw exception   
          
        System.out.println("rest of the code");  
          
    }  
      
} 
```

### Java User Input (Scanner)
* The Scanner class is used to get user input, and it is found in the java.util package.

* Input Types

Method |	Description
-------- |-------------
nextBoolean() |	Reads a boolean value from the user
nextByte() |	Reads a byte value from the user
nextDouble()|	Reads a double value from the user
nextFloat()|	Reads a float value from the user
nextInt()|	Reads a int value from the user
nextLine()|	Reads a String value from the user
nextLong()|	Reads a long value from the user
nextShort()|	Reads a short value from the user

* The scanner can also use delimiters other than whitespace.
example :

```
     String input = "1 fish 2 fish red fish blue fish";
     Scanner s = new Scanner(input).useDelimiter("\\s*fish\\s*");
     System.out.println(s.nextInt());
     System.out.println(s.nextInt());
     System.out.println(s.next());
     System.out.println(s.next());
     s.close();
     //output 
     //   1
     //2
     //red
     //blue
```

##### Localized numbers
An instance of this class is capable of scanning numbers in the standard formats as well as in the formats of the scanner's locale.
