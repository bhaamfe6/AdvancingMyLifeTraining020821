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
- **Inheritance** - a mechanism in which one object acquires all the properties and behavior of a parent object.  The idea behind inheritance is that you can create new classes that are built upon existing classes.
- **Abstraction** - a way to conceptualize abstract characteristics into a class.
    - Abstract classes- Declared using the <u>abstract</u> keyword and cannot be instantiated.  The are templates for other classes to extend from concrete classes.
- **Polymorphism** - taking on many forms. Describes how objects can behave differently as in overloading and overriding.
    - Overloading (compile-time)- using the same method name but specifying different parameters.
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

- **Class** - a specific construct in Java that can associate behavior (methods) and state.  For example, the behavior and state of object or objects of a parent class are inherited by a sub or child class. It serves as a blueprint for an object (which is a 'living' instance) of the class.  
    - A class can declare both <u>static</u> and <u>instance</u> members (variables and methods).
    - The following is an example of adding a state to a class:
        - We'll create a simple variable that will specify the object's id. We'll represent that with an `int` labeled `id`. We'll also create a simple method to get and set the `id` variable.
    - **Object class** - is a special class that is the root class of all other classes. Essentially, other classes either *directly* or *indirectly* inherit from this `Object` class.
    
    - **Wrapper Class** - Wrapper classes allow us to represent primitives as objects.  Conversion between a wrapper object and a primitive occurs automatically
        - **autoboxing**: primitive to object
        - **unboxing**: object to primitive
        - Wrapper utility methods/fiELDS:
            - **<u>FIELDS<u>**
            - MAX_VALUE: constant holding the maximum value that that particular wrapper object / primitive can have
            - MIN_VALUE: constant holding the minimum value that particular wrapper object / primitive can have
            - SIZE: the number of bits
            - TYPE: *Class* instance representing primitive type
            
            - **<u>METHODS (static methods)</u>**
            - - valueOf(..): parses some argument into a wrapper object
            - parseInt(..), parseDouble(..), ... : parse some argument into a primitive of that type
            - intValue, doubleValue, longValue, etc.: returns value of wrapper object as a primitive

public class ClassOne {

    int id;

    public int getId(){ return id;}

    public void setId(int id) { this.id = id;}

    public static void main (String[] args){

    }
}

**The Getter and Setter** or getID() method and setID() methods are the behaviors with state return id and this.id = id of  primitive int and the variable id.

The following example updates the main() method and added an additional behavior setID() and a println() method. The setID() method set the ID to 25 when the variable c1 called the setId() method with the c1.setId(25) syntax.

 public static void main (String[] args){
        ClassOne c1 = new ClassOne();
        c1.setId(25);
    
        System.out.println(c1.getId());
    }
}

- **Access Modifier** - Access modifiers control the access to a class, a method, a field or constructor in one class compared to another.

- **public** means the construct is available to all classes in any package   
- **protected** means the construct is available to any class in the same package or a subclass in any package.   
- **private** means the construct is only available to the current class.   
- **default** is the given access when no modifier is specified and it means that only classes in the same package have access to it.

- **Constructor** - a block of code that is executed when a class is instantiated. This block of code is executed once per object that is created. A *<u>constructor always have the same name as the class</u>* and can accept any number of parameters. By default, if you create a class and don't specify a constructor the compiler will generate one for you. The one generated is called the default no-arg constructor.

public class Constructors {

    public Constructors(){
        System.out.println("Default constructor ran.");
    }

    public Constructors(int value){
        System.out.println(value);
    }

    public static void main(String[] args) {
        //create instances here
        Constructors c = new Constructors(5839);

        //use the no-arg constructor
        Constructors cNoArg = new Constructors();
    }
}

In the above example, the class Constructors has a constructor of the same name "Constructors" that is public accessible.  It is a no-arg constructor, which is a default constructor, because there is no parameter argument defined for this constructor.  The next constructor, *public Constructors( int value){* . This constructor example as an argument that is a single int parament named value.  The constructor is instantiated in the main() method by creating a Constructors object assigning a variable c to the object.  The object is instantiated with the new keyword and passing the value of 5839 to the object.  The last constructor is an example of contructor overloading because the  ***parameter has changed*** to no argument.  It is the same object Constructors with the cNoArg variable assignment.

- **Exceptions** - Exceptions are events that occur during execution of programs that disrupt the normal flow of instructions.
    - exceptional event that occurred inside the execution of a method
    - Information about the exception, including its type
    - The state of the program when the exception occurred
    - Some sort of exception message that may be specified when the exception is thrown
    - Other custom information
    - Exceptions can be
        - Thrown
        - Caught

    1. Checked Exceptions
        - The `Exception` class and all of its subclasses (except RuntimeException) are known as checked exceptions
        - Checked exceptions **MUST** be handled or declared by the programmer, otherwise the code **will not compile**

    2. Unchecked Exceptions
        - The `RuntimeException` class is a special type of exception that is not required to be handled or declared
        - Unchecked exceptions are typically reserved for issues such as
        - `ArithmeticException` for illegal arithmetic, such as dividing by 0
        - `IndexOutOfBoundsException` if we try to reference an index that is larger than the size of our array
        - `NullPointerException` if we try to access a field or invoke an instance method on something that is pointing to no object (`null`)
        - `ClassCastException` if we try to downcast from a parent reference type to some child reference type that is hierarchically valid, but the object is not of that instance.
    -**Custom Exceptions**
        - Usually we create custom exceptions to have some sort of descriptive element to the type of exceptional event that is happening. Custom exceptions can either extend RuntimeException, which would make it an `unchecked exception`, or extend Exception, which would make it `checked`.
    - **Handling Exceptions v. Declaring Exceptions**
    - Handling: risky code is placed inside a try/catch block
    - try-catch-finally
    - In order to handle exceptions, a try/catch block can be used
    - `try` encloses the code that may throw an exception
        - for example if we call methods/constructors that have some sort of `throws` declaration
    - `catch` defines an exception to catch and run the code inside that block if that exception occurs from the code inside the try block
    - `finally` is used to run a block of code whether an exception is thrown or not. It is always guaranteed to execute unless our program fatally crashes or System.exit() is called.

    - You can have
        - try-finally
        - try-catch-catch-...-finally
        - try-catch-...
- **Methods** - Methods are blocks of code that only run when they are called. The `public static void main(String[] args)` method, however, is a special method that is called directly by the JVM when we run our application. The purpose of utilizing methods, is to reuse code by defining it only once, and then using it many times. Methods must be declared within a class in Java
- Methods are defined with an access modifier, followed by any non-access modifiers, the return type, and then the name of the method and parentheses that can define the various parameters a method may accept

