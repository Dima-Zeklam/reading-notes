# Object Oriented Programming (OOP)
Object-oriented programming is a model that provides different types of concepts, such as inheritance, abstraction, polymorphism, etc,  to improve code readability and reusability by defining a Java program efficiently.

![Object-Oriented Programming](https://static.javatpoint.com/difference/images/procedural-programming-vs-object-oriented-programming.png)


## Objects 
* Objects have charactaristics, which are used to describe them.for example a mug can be full or empty, a car can be red or black, and so on .these charactaristics are called **attributes**.

* Object is  entity that has state which is the data of the object and behavior.
* an object is an **instance** of a class.
* Example on software object:

![software object](https://docs.oracle.com/javase/tutorial/figures/java/concepts-object.gif)

## Class 
Class is blueprint from which objects are created, can be contain Fields, Methods, Constructors and Blocks.
Each class has a name, and each is used to define attributes and behavior.

#### The differences between Objects and Classes:

!(Objects vs Classes)[https://media.geeksforgeeks.org/wp-content/uploads/Screenshot-from-2018-08-27-10-39-14-1.png]
Class	| Object
--------|--------
A class is a blueprint from which you can create the an objects |An object is the instance of the class, which helps programmers to use variables and methods from inside the class
A class is used to bind data as well as methods together as a single unit |	Object acts like a variable of the class.
Classes have logical existence | 	Objects have a physical existence
A class doesn't take any memory spaces when a programmer creates one |	An object takes memory when a programmer creates one
The class has to be declared only once |	Objects can be declared several times depending on the requirement
Class is declare using class keyword -> class Employee{}|Object is created through new keyword -> Employee ob =new Employee();

## Interfaces
An interface is a completely abstract class that contains only abstract methods.


**Some specifications for interfaces:**

- Defined using the interface keyword.
- May contain only static final variables.
- Cannot contain a constructor because interfaces cannot be instantiated.
- Interfaces can extend other interfaces.
- A class can implement any number of interfaces.

**Interfaces have the following properties:**
- An interface is implicitly abstract. You do not need to use the abstract keyword while declaring an interface.
- Each method in an interface is also implicitly abstract, so the abstract keyword is not needed.
- Methods in an interface are implicitly public.

**An example of a simple interface:**

```
public interface OperateCar {

   int turn(Direction direction,
            double radius,
            double startSpeed,
            double endSpeed);
   int changeLanes(Direction direction,
                   double startSpeed,
                   double endSpeed);
   int signalTurn(Direction direction,
                  boolean signalOn);
   int getRadarFront(double distanceToCar,
                     double speedOfCar);
   int getRadarRear(double distanceToCar,
                    double speedOfCar);
         ......
   // more method signatures
}
```
**When you implement an interface, you need to override all of its methods.**

```
public class OperateBMW760i implements OperateCar {

int turn(Direction direction,
            double radius,
            double startSpeed,
            double endSpeed){
                .....
            }
   int changeLanes(Direction direction,
                   double startSpeed,
                   double endSpeed){
                       .....
                   }
   int signalTurn(Direction direction,
                  boolean signalOn){
                      ......
                  }
   int getRadarFront(double distanceToCar,
                     double speedOfCar){
                         ......
                     }
   int getRadarRear(double distanceToCar,
                    double speedOfCar){
                        .........
                    }

    // other members, as needed -- for example, helper classes not 
    // visible to clients of the interface
}
```

## Inheritance
Is the process that enables one class to acquire the properties (methods and variables) of another. 

* The class inheriting the properties of another is the subclass (also called derived class, or child class); the class whose properties are inherited is the superclass (base class, or parent class).

* To inherit from a class, use the extends keyword.
*Example*
```
class MountainBike extends Bicycle {

    // new fields and methods defining 
    // a mountain bike would go here

}
```

* When one class is inherited from another class, it inherits all of the superclass' non-private variables and methods.
* Recall the protected access modifier, which makes the members visible only to the subclasses.
* Constructors are not member methods, and so are not inherited by subclasses.
* You can access the superclass from the subclass using the super keyword.

##### read more about [ Object-Oriented Programming](https://docs.oracle.com/javase/tutorial/java/concepts/).





