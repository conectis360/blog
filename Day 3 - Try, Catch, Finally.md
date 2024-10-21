**Day 3: Try, Catch, Finally: The Java Love Triangle**

In the romantic world of Java, the **try**, **catch**, and **finally** blocks form a perfect (yet occasionally dysfunctional) trio. They work together to ensure your program doesn’t crash and burn, much like how Ross, Rachel, and Monica try to keep their friendship intact on _Friends_.

## Try: The Risk-Taker

The **try** block is your brave friend who always volunteers to do the risky stuff—like reading a file or dividing numbers. It wraps around the code that _might_ throw an exception.
``` java
try {
   int result = 10 / 0; // Uh-oh! Division by zero!
}
```

## Catch: The Problem Solver

Then we have **catch**, the responsible problem-solver. It swoops in when things go wrong and tries to fix the mess.
``` java
catch (ArithmeticException e) {
    System.out.println("Oops, division by zero is not allowed!");
}
```

## Finally: The Cleanup Crew

Finally, **finally** always shows up, no matter what. Even if an exception is thrown or caught, **finally** ensures that resources are cleaned up—kind of like that friend who sticks around to help clean after the party.

``` java
finally { 
	System.out.println("Cleanup complete!"); 
}
```
### Call to Action:

Do you have any clean-up nightmares (coding or otherwise)? Share your stories, and remember to subscribe for more programming love triangles!