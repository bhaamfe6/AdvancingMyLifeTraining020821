# Java: Encapsulation
The principle in OOP of 
1. Containing related state and behavior together inside a class
- Can help us adhere to the Single REsponsibility PRinciple (SRP)
2. Hiding and preventing change to an object's data members
- Prevents arbitrary exrernal changes that could cause an object to be in a nivalid/inconsistent state  - e.g. imagine we have a Person class, and some code arbitrarily changes a person object's age to a negative value 

Encapsulation introduces the idea of ***getter*** and ***setter*** methods. 
- Getter methods are used to access private members from outside
- Setter methods would allow us to modify these members from outside.

Access to the getter and setter methods themselves are also controlled by access modifiers.  Usually these getters and setters might be 'public'.

# Abstraction
Abstraction is a principle in which we centralize common characgeristics and generalize behavior into conceptual modules.  By utilizing abstraction, we hide underlying implementation. For example, when we drive a car, we don't need to know how the car works, we only need to know how to use the accelerator, brakes, and steering wheel.  THe car abstracts away the internal details of timing, engine cycles, transmission, cooling, and other functions.

## Abstract Classes
In Hava, we achieve abstraction using abstract classes and interfaces. Abstract classes are classes decleared using the `abstract` keyword that cannot be instantiated.  Abstrat classes essentially serve as templates for other classes to extend from `concrete classes` . WHithin abstract classes there can be both <u>abstract methods</u> and <u>concrete methods</u>. Abstract methods must be implemented by the concrete subclasses that extend that abstract class. An abstracgt class can contain instance fields and concrete methods just like ordinary classes.

THe primary differences, as summarized: 
- Abstract classes cannot be instantiated
- Abstract classes can have abstract methods

## Interfaces
Interfaces cannot be instantiated like abstract classes.  They serve as contracts for methods that a class must implement.  To inherit from interfaces. classes use the `implements` keyword to implement the interface.  Classes that do this are forced to actually override these methods defined in the interface and provide some sort of code in the method body.

Multiple interfaces can be implemented by a class. However, you cannot extend multiple classes, only one class. This is one of the reasons you might use interfaces instead.

There are also plenty of other differences as well.  
- Interfaces can have variables, but thety are implicityly set to `public` , `static` , and `final` ,so no instance fields can be defined in an interface unlike an abstraact class.
- Before Hava 8, interfaces could only contain abstract methods
    - However, since then, the `default` keyword could be used with a method in a interfact to allow you to provide an implementation directly in the interface
    - The purpose of this is to not break old classes that might be implementing an interface ewhenever you add new methods to that interface.
- Interfaces can contain static methods

Interfaces have a lot more restrictions than abstract classes, because one of the reasons is to actually allow for multiple interfaces to be implemented for a class.  The issue with multiple inheritance in Java is ambiguity that can arise if two classes had the same method name, since Java would not know which one to inherit.