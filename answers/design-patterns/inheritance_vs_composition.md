# Inheritance vs Composition: Why is composition often preferred?

In Object-Oriented Programming (OOP), both inheritance and composition are ways to reuse code and model relationships. However, composition is often considered a better, more flexible option than inheritance for most scenarios.

---

## Inheritance
- **"Is-a" Relationship:** Models a strict hierarchy (e.g., `Dog` is an `Animal`).
- **Code Reuse:** Subclasses inherit methods and properties from parent classes.
- **Tight Coupling:** Subclasses are tightly coupled to the implementation of their parent, making changes risky.
- **Fragile Base Class Problem:** Changes in the base class can break subclasses.
- **Single Inheritance Limitation:** Most languages only allow single inheritance, limiting flexibility.

---

## Composition
- **"Has-a" or "Uses-a" Relationship:** Objects are built from other objects (e.g., `Car` has an `Engine`).
- **Flexibility:** Behavior can be changed at runtime by swapping components.
- **Loose Coupling:** Components can be reused and tested independently.
- **Favors Delegation:** Instead of inheriting behavior, objects delegate work to their components.
- **Avoids Inheritance Pitfalls:** No fragile base class or deep hierarchies.

---

## Example (Python)
### Inheritance (Less Flexible)
```python
class Bird:
    def fly(self):
        print("Flying")

class Duck(Bird):
    pass
```

### Composition (More Flexible)
```python
class FlyBehavior:
    def fly(self):
        print("Flying")

class Duck:
    def __init__(self, fly_behavior):
        self.fly_behavior = fly_behavior
    def fly(self):
        self.fly_behavior.fly()
```

---

## When to Use Each
- **Use inheritance:**
  - When there is a clear "is-a" relationship and the hierarchy is stable.
  - For base classes with shared implementation that is unlikely to change.
- **Use composition:**
  - When you want flexibility and loose coupling.
  - When behavior may change at runtime or needs to be reused in different contexts.
  - For most application code, especially as systems grow.

---

## References
- [Design Patterns: Elements of Reusable Object-Oriented Software (GoF)](https://en.wikipedia.org/wiki/Design_Patterns)
- [Martin Fowler: Favor Composition Over Inheritance](https://martinfowler.com/bliki/CompositionOverInheritance.html)
- [Effective Java, Item 18: Favor composition over inheritance](https://www.oreilly.com/library/view/effective-java-3rd/9780134686097/) 