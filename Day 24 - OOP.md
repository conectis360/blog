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
