# Java Exceptions – The Crash You Never Saw Coming

You’re happily coding away, sipping your third cup of coffee, when—*boom*—an error message appears, and your screen turns into a wall of red text. Welcome to the world of Java exceptions! Like a friendly cat that suddenly knocks your coffee cup off the table, exceptions are unexpected events that make your program crash unless you handle them properly.

## What Are Java Exceptions?

Java exceptions are like little traffic accidents in your code. They occur when something goes wrong—an array goes out of bounds, a file goes missing, or your math suddenly decides that dividing by zero is cool (spoiler: it's not). Exceptions are Java’s way of saying, “Hey, something’s broken! You should probably fix this.”

### Types of Exceptions:

- **Checked Exceptions**: Imagine your mom making you check your homework before you leave the house—checked exceptions are like that. Java forces you to handle them whether you like it or not. Forget about them, and Java will throw a tantrum (aka a compilation error).
  
- **Unchecked Exceptions**: These are like stepping on a Lego—completely unexpected but totally your fault. If you don't handle them, your program might crash.

### Try-Catch Blocks

To deal with exceptions, you need a **try-catch block**. It's like Java’s version of bubble wrap—try something risky (like opening a file), and if it goes wrong, the **catch** block swoops in to save the day.

```java
try {
    // risky operation
} catch (Exception e) {
    // handle the error
}
