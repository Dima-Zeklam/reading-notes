# Java Language Basics
![java](https://vipaa.net/wp-content/uploads/2021/08/java.jpg)

### Variables
A Java variable is a piece of memory that can contain a data value and Variable names are case-sensitive.
The Java programming language defines the following kinds of variables:
* Instance Variables (Non-Static Fields) 
* Class Variables (Static Fields)
* Local Variables
* Parameters 


### Arrays
An array is a container object that holds a fixed number of values of a single type.

![array](https://qph.fs.quoracdn.net/main-qimg-7f2d12b941e12858dba96dba2c00bea6)

##### Copying Arrays
The System class has an arraycopy method that you can use to efficiently copy data from one array into another:

>> public static void arraycopy(Object src, int srcPos,
                             Object dest, int destPos, int length)

### Primitive Data Types
 The eight primitive data types supported by the Java programming language are:
Data Type |	Default Value |	Default size
----------|---------------|-------------
boolean	| false	|1 bit
char	v'\u0000' v	2 byte
byte|	0	| 1 byte
short |	0	|2 byte
int	| 0	| 4 byte
long|	0L	|8 byte
float|	0.0f	|4 byte
double|	0.0d	|8 byte

### Operators
Operators |	Precedence
postfix  |	expr++ expr--
unary	| ++expr --expr +expr -expr ~ !
multiplicative |	* / %
additive |	+ -
shift |	<< >> >>>
relational |	< > <= >= instanceof
equality |	== !=
bitwise | AND	&
bitwise | exclusive OR	^
bitwise | inclusive OR	|
logical|  AND	&&
logical | OR	||
ternary |	? :
assignment |	= += -= *= /= %= &= ^= |= <<= >>= >>>=

### Expressions
An expression is a construct made up of variables, operators, and method invocations, which are constructed according to the syntax of the language, that evaluates to a single value.

### Blocks
A block is a group of zero or more statements between balanced braces and can be used anywhere a single statement is allowed.

```
class BlockDemo {
     public static void main(String[] args) {
          boolean condition = true;
          if (condition) { // begin block 1
               System.out.println("Condition is true.");
          } // end block one
          else { // begin block 2
               System.out.println("Condition is false.");
          } // end block 2
     }
}
```

### Control Flow Statements
Java compiler executes the code from top to bottom. The statements in the code are executed according to the order in which they appear.
##### The if-then Statement
The if-then statement is the most basic of all the control flow statements. It tells your program to execute a certain section of code only if a particular test evaluates to true
#### Flow chart of a switch statement:

![flow chart for if statment](https://dotnettutorials.net/wp-content/uploads/2020/08/If-Else-Statement-Control-Flow-Chart-in-Java.png)

##### The switch Statement
Unlike if-then and if-then-else statements, the switch statement can have a number of possible execution paths. A switch works with the byte, short, char, and int primitive data types.
Code Example:

```
public class SwitchDemo {
    public static void main(String[] args) {

        int month = 8;
        String monthString;
        switch (month) {
            case 1:  monthString = "January";
                     break;
            case 2:  monthString = "February";
                     break;
            case 3:  monthString = "March";
                     break;
            case 4:  monthString = "April";
                     break;
            default: monthString = "Invalid month";
                     break;
        }
        System.out.println(monthString);
    }
}
```

##### The Java while Loop
The while loop enables your Java program to repeat a set of operations while a certain conditions is true.
```
while (expression) {
     statement(s)
}
```

##### The Java for loop
The Java for loop repeats a set of Java operations. A for loop repeats a block of code as long as some condition is true.

```
for (initialization; termination;
     increment) {
    statement(s)
}
```

##### The break Statement
The break statement has two forms: labeled and unlabeled. You saw the unlabeled form in the previous discussion of the switch statement. You can also use an unlabeled break to terminate a for, while, or do-while loop.

### Java’s API Documentation
Javadoc (originally cased JavaDoc) is a documentation generator created by Sun Microsystems for the Java language (now owned by Oracle Corporation) for generating API documentation in HTML format from Java source code. 
You can find things in the API documentation by Using the index way:
1.  Visit [docs.oracle.com/javase/8/docs/api/](https://docs.oracle.com/javase/8/docs/api/)
2. Click the INDEX link at the top of the page to open the index.
3. In the P section, do a search for println to find the println entries.
4. Pick one of the println entries.
5. Click the link for the entry that you’ve chosen.



