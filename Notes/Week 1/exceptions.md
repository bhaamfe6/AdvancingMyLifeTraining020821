# Java: Exceptions
Exceptions are events that occur during execution of programs that disrupt the normal flow of instructions

**NOTE**: Exceptions are not the same concept as compilation errors that might result from bad syntax.

In the context of Java, exceptions are objects that wrap an exceptional event that occurred inside the execution of a method. Exception objects contain information such as the following:
- Information about the exception, including its type
- The state of the program when the exception occurred

## Exception Hierarechy
![Exception Hierarchy](https://www.javamex.com/tutorials/exceptions/ExceptionHierarchy.png)

## Checked vs. Unchecked Exceptions
1. Checked Exceptions
- The `Exceptions` class and all of its subclasses (except Runtime Exception) are known as checked exceptions
- Checked exceptions **Must** be handled or declared by the programmer, otherwise the code **will not compile**

2. Unchecked Exceptions
- The `RuntimeException` class is a special type of exception that is not required to be handled or declared
- Unchecked exceptions are typically reserved for issues such as 
- `ArithmeticException` for illegal arithmetic, such as dividing by 0
- `IndexOutOfBoundsException` if we try to reference an index that is larger than the size of our array
- `NullPointerException` if we try to acess a field or invoke an instance method on something that is pointing to no object (`null`)
- `ClassCastException` if we try to downcast from a parent reference type to some child reference type that is hierarchically valid, but the object is not of that instance.

## Custom Exceptions
Usually we create custom exceptions to have some sort of descriptive event that is happening.  Custom exceptions can either extend RuntimeException, which would make it an `unchecked exception`, or extend Exception, which would make it `checked` .

## Handling Exceptions v. Declaring Exceptions
Handling: risky code is placed inside a try/catch block
- try-catch-finally
    - In order to handle exceptions, a try/catch block can be used
    - `try` encloses the code that may throw an exception
        - for example if we call methods/constructors that have some sort of `throws` declarations
    - `catch` defines an exception to cagtch and runt he code inside that block if that exception occurs from the code inside the try block
    - `finally` is used to run a block of code whether an exception is trhwon or not. It is always guaranteed to execute unless our program fatally crashes or System.exit() is called.

You can have try-finally on its own, without catching any exceptions.

You can have:
- try-finally
- try-catch-catch-...-finally
- try-catch-...

Declaring: We can use the `throws` keyword in the method signature to basically say, `"watch out, if you are a method that calls me, you will need to handle the exception that I might throw under certain conditions"` 