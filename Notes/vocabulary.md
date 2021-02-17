# Java: Vocabulary
- **Concatenate** - One of the text functions to join two or more text strings into one string
- **delimiter** - one or more characters that separate text strings.
    - Common delimiters include:
        1. commas
        2. semicolon
        3. quotes
        4. braces
        5. pipes
        6. slashes
   
 - **Java Pool** - The Java Pool holds the java execution code in a similar manner to the PL/SQL cache.  The Java pool is used by many internal routines, such as import and export.
        - When a String is initialized, the JVM checks to increase or decrease memory by checking the String pool to see if that String literal already exist in the String Pool.
        - The String Pool is stored in the Java Heap momory
- **Java Heap** - The Java Heap is the area of memory used to store objects instantiated by applications running on the JVM.  Objects in the heap can be shared between threads.
- **Java Stack** - The stack is a linear data structure that is used to store the collection of objects. It is based on Last-In-First-Out (LIFO)
- **Literals** - Literals represent booleans, character, numeric, or string data.  Literals provide a means of expressiong specific values in your program.
    - Types of Java Literals:
        1. Integer
        2. Floating-point
        3. Boolean
        4. Character
        5. String
- **Inheritanced** - a mechanism in which one object acquires all the properties and behavior of a parent object.  The idea behind inheritance is that you can create new classes that are built upon existing classes.
- **Abstraction** - a way to conceptualize abstract characteristics into a class.
    - Abstract classes- Declared using the <u>abstract</u> keyword and cannot be instantiated.  The are templates for other classes to extend from concrete classes.
- **Polymorphism** - taking on many forms. Describes how objects can behave differently as in overloading and overriding.
    - Overloading (comile-time)- using the same method name but specifying different parameters.
        - The following are rules related to overloading:
            1. overloaded method must have a different number and/or types of parameters (the order can be different as long as the types are different)  
            2. overloaded methods can throw Exceptions
            3. overloaded methods can return a different datatype
    - Override (run-time)- dictates that a child class overrides a parent class. Method overriding describes the case in which a child class has the same method signature as a method in the parent class. However, this method in the child class can have a different implementation. Child classes can change the default behavior, which makes class hierarchies and inheritance more flexible and dynamic. Method overriding is considered **runtime polymorphism**.
        - When overriding a parent method in a child class, the method must:
            1. Have a covariant return type
            2. the return type must be the same or a subclass of the return type in the parent method
            3. The same method name
            4. The same method parameters
            5. The same access modifier or more access
- **Encapsulation** - Containing related state and behavior together inside a class. Can help us adhere to the Single Responsibility Principle (SRP). Hiding and preventing change to an object's data members. Prevents arbitrary external changes that could cause an object to be in an invalid/inconsistent state - e.g. imagine we have a Person class, and some code arbitrarily changes a Person object's age to a negative value
    - Encapsulation introduces the idea of **getter** and **setter** methods.
        - Getter methods are used to access private members from outside.
        - Setter methods would allow us to modify these members from outside. 
    **Access to the getter and setter methods themselves are also controlled by access modifiers.** Usually these getters and setters might be `public`.
- **Interface** - Interfaces cannot be instantiated like abstract classes. They serve as contracts for methods that a class must implement. To inherit from interfaces, classes use the `implements` keyword to implement the interface. Classes that do this are forced to actually override these methods defined in the interface and provide some sort of code in the method body. 
    - Multiple interfaces can be implemented by a class. However, you cannot extend multiple classes, only one class. This is one of the reasons you might use interfaces instead.
- **Annotations** - Java annotations are special constructs that may be seen througout Java code.  Annotations use the @ symbol followed by the annotation name.  They are used to provide metadata about source code to the compiler and/or JVM.  They can be placed on classes, methods, fields, and other constructs depending on how these annotations were defined.
    - One of the primary purposes of annotations is to enforce rules in the code or to abstract away some functionalality provided by a framework (example, Spring framework).  Annotations are often processed using Java's built-in `Reflection API` to dynamically provided functionality for developers.
    - You should be familiar with a few built-in annotations:
        1. `@Override` : declares that a method must ovverride an inherited method
        2. `@Deprecated` : marks a method as obsolete
        3. `@SuppressWarnings` : instructs compiler to suppress compilation warnings
        4. `@FunctionalInterface` : designates an interface to be a functional interface
- **POJOS (Plain Old Java Object)** - It is an ordinary Java Object, not bound by any special resgtriction other than those forced by the Java Language Specification and not requiring any classpath.  POJOs are used for increasing the readability and re-usability of a program.  POJOs have gained the most acceptance because they are easy to write and understand.
    - POJO should not:
    1. Extend prespecified classes, Ex. public class GFG extends javax.servlet.http.HttpServlet{...} is **not** a POJO class.
    2. Implement prespecified interfaces
    3. Contain prespecified annotations.