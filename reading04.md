# OOP
Object-oriented programming is a model that provides different types of concepts, such as inheritance, abstraction, polymorphism, etc,  to improve code readability and reusability by defining a Java program efficiently.

!(oop)[https://lh4.googleusercontent.com/TnYIigkJ8KvE-AyaWdum1Uho_MtHJUtacEBCpNt3VNEm7N8j0snWilSXFVRHY7c9lOPOvNVYwRehahmMJ8wFMoNTaZfBoEOp_Ce3vsoxW0wJM5jsdrvgwYGUD1CSqgQIKslRKVM]


## Objects 
An entity that has state which is the data of the object and behavior or it's consists of methods and properties to make certain type of data useful.
like pen, table, car, etc..

## class 
Class is blueprint from which objects are createdm can be contain Fields, Methods, Constructors and Blocks.

!(object and class)[http://www.atnyla.com/library/images-tutorials/class-and-object-in-java-6.PNG]

## Inheritance

Inheritance represents the IS-A relationship which is also known as a parent-child relationship.
which one object acquires all the properties and behaviors of a parent object.

*  use the extends keyword, followed by the name of the class to inherit from:

```
class MountainBike extends Bicycle {

    // new fields and methods defining 
    // a mountain bike would go here

}
```

## Interface
An interface is used to group related methods with empty bodies.

some specifications for interface :
* Defined using interface keyword
* may contain only static final variables
* can't contain a constructor because interface can't be instantiated.
* inter face can extends other interfaces.
* a class can implement any numer of interfaces.

##### An Example of an interface:

```
interface Bicycle {

    //  wheel revolutions per minute
    void changeCadence(int newValue);

    void changeGear(int newValue);

    void speedUp(int increment);

    void applyBrakes(int decrement);
}
```
## Binary, Decimal and Hexadecimal Numbers
### Decimals
The decimal point goes between Ones and Tenths.
The decimal point is the most important part of a Decimal Number. Without it we are lost, and don't know what each position means.

![Decimals](https://www.mathsisfun.com/numbers/images/decimal.svg)

### Binary
so requiring only two different symbols for its digits, 0 and 1, instead of the usual 10 different symbols needed in the decimal system.

Here are some equivalent values:

Decimal: |	0	| 1 |	2	|3	|4	|5|	6	|7|	8	|9	|10	|11	|12|	13|	14|	15
Binary:	| 0|	1|	10|	11|	100	|101|	110	|111|	1000	|1001	|1010	|1011	|1100	|1101|	1110	|1111

### Hexadecimal Numbers
described as a 16 digit number representation of numbers from 0 - 9 and digits from A - F. 

Decimal: |	0 |	1	|2	|3	|4	|5	|6	|7	|8|	9	|10|	11	|12	|13	|14|	15
Hexadecimal:|	0	|1|	2	|3	|4	|5	|6|	7	|8	|9|	A	|B	C|	D	|E	|F

**Example:**    
![ hexadecimal number ](https://www.mathsisfun.com/numbers/images/hex-example.gif)
