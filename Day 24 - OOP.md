Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects," which are instances of classes. It is widely used in modern software development because it makes programs more modular, reusable, and easier to understand.

Let’s break down OOP step by step:

---

### 1. **Core Concepts of OOP**

There are four fundamental principles of OOP: **Encapsulation, Inheritance, Polymorphism, and Abstraction**.

#### a) **Encapsulation**

- **Definition**: Encapsulation is the bundling of data (attributes) and methods (functions) into a single unit called an object.
- **Purpose**: To protect the data and expose only what’s necessary via controlled access using getters and setters.
- **Example**:

```java
class Car {
    private String color; // Private data

    public String getColor() { // Getter
        return color;
    }

    public void setColor(String color) { // Setter
        this.color = color;
    }
}
```
-  Here, the `color` property is private, but we can access or modify it using public methods.

#### b) **Inheritance**

- **Definition**: Inheritance allows one class (child class) to inherit properties and methods from another class (parent class).
- **Purpose**: To promote code reuse and represent relationships between objects.
- **Example**:

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat(); // Inherited method
        dog.bark(); // Dog-specific method
    }
}
```

Output:
```bash
This animal eats food.
The dog barks.
```
#### c) **Polymorphism**

- **Definition**: Polymorphism means "many forms." It allows objects to be treated as instances of their parent class while behaving according to their actual implementation.
- **Types**:
    1. **Compile-time Polymorphism (Method Overloading)**:
        - Same method name, different parameter lists.
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

