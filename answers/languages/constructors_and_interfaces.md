# Constructors and Interfaces: Why aren't constructors part of the interface?

## ELI5 (Explain Like I'm 5)
Imagine you have a set of blueprints for building toy cars. The blueprint tells you what the car can do (drive, honk), but not how to build it. Constructors are like the instructions for building the car, but the interface is just about what the car can do once it’s built!

---

## Why Aren't Constructors in Interfaces?
- **Interfaces** define what methods a class must have, not how to create the class.
- Constructors are about object creation, not behavior.
- Different classes may need different ways to be built, even if they share the same interface.

---

## Example (Java)
```java
interface Vehicle {
    void drive();
}
class Car implements Vehicle {
    public Car(String model) { /* ... */ }
    public void drive() { /* ... */ }
}
```
- The interface says nothing about how to construct a `Car`.

---

## Why is This Useful?
- Allows flexibility in how objects are created.
- Supports patterns like factories and dependency injection.

---

## References
- [Oracle: Interfaces and Inheritance](https://docs.oracle.com/javase/tutorial/java/IandI/interfaceDef.html)
- [Stack Overflow: Why can't constructors be part of an interface?](https://stackoverflow.com/questions/1810332/why-cant-constructors-be-part-of-an-interface)
- [GeeksforGeeks: Constructors in Interfaces](https://www.geeksforgeeks.org/constructors-in-java-interfaces/) 