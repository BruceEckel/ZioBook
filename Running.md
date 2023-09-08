You've got a zio that describes something. How do you actually run it?

Although Scala compiles code to JVM bytecodes, ZIO has an interpreter that steps through your code, much like the JVM interprets JVM bytecodes. The Zio interpreter is the hidden piece that allows Zio to understand so much more about the meaning of your code, including the ability to decide what to run concurrently and how to invisibly tune that concurrency -- all at runtime.

The interpreter is also the mechanism that evaluates the various effects described in the generic type parameters for each ZIO object.

The reason we have the `delay` directive in zio-direct is to indicate that this code will be evaluated by the interpreter.

Here's a basic example that shows a ZIO being executed by the interpreter:
