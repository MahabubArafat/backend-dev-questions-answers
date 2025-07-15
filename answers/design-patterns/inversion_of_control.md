# What is Inversion of Control (IoC) and how does it improve code design?

**Inversion of Control (IoC)** is a design principle in which the control of objects or portions of a program is transferred to a container or framework. Instead of the application code controlling the flow, the framework or container calls into the application code. This leads to more modular, testable, and flexible code.

---

## Key Concepts
- **Traditional Control:** Application code creates and manages dependencies directly.
- **IoC:** The framework or container manages the creation and wiring of dependencies, and calls application code as needed.
- **Dependency Injection (DI):** The most common form of IoC, where dependencies are provided to a class rather than the class creating them itself.

---

## Benefits of IoC
- **Decoupling:** Reduces tight coupling between components, making code easier to change and maintain.
- **Testability:** Makes it easier to substitute mock or fake dependencies for testing.
- **Reusability:** Components can be reused in different contexts because they are not hard-wired to specific implementations.
- **Flexibility:** Behavior can be changed by swapping implementations or configurations without changing code.

---

## Example (Without IoC)
```python
class Service:
    def __init__(self):
        self.repository = Repository()  # Direct dependency
```

## Example (With IoC / Dependency Injection)
```python
class Service:
    def __init__(self, repository):
        self.repository = repository  # Dependency is injected
```

---

## Common IoC Containers
- **Spring (Java)**
- **.NET Core Dependency Injection**
- **Angular (JavaScript/TypeScript)**
- **Django (Python, via settings and middleware)**

---

## References
- [Martin Fowler: Inversion of Control](https://martinfowler.com/bliki/InversionOfControl.html)
- [Martin Fowler: Dependency Injection](https://martinfowler.com/articles/injection.html)
- [Wikipedia: Inversion of Control](https://en.wikipedia.org/wiki/Inversion_of_control) 