# Java: Annotations
Java annotations are special constructs that may be seen througout Java code.  Annotations use the @ symbol followed by the annotation name.  They are used to provide metadata about source code to the compiler and/or JVM.  They can be placed on classes, methods, fields, and other constructs depending on how these annotations were defined.

One of the primary purposes of annotations is to enforce rules in the code or to abstract away some functionalality provided by a framework (example, Spring framework).  Annotations are often processed using Java's built-in `Reflection API` to dynamically provided functionality for developers.

You should be familiar with a few built-in annotations:
- `@Override` : declares that a method must override an inherited method
- `@Deprecated` : marks a method as obsolete
- `@SuppressWarnings` : instructs compiler to suppress compilation warnings
- `@FunctionalInterface` : designates an interface to be a functional interface

Annotations have a number of uses for example:
- **Information for the compiler** - used by the compiler to detect errors or suppress warnings.
- **Comiple-time and deployment-time processing** - Software tools can process annotation information to generate code, XML files, and more
- **Runtime processiong** - Some annotations are available to be examined at runtime.

