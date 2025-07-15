# High Cohesion, Loose Coupling: What does it mean? Why is it important and how is it achieved?

## ELI5 (Explain Like I'm 5)
Imagine you have a box of LEGO sets. Each set is for a different thing: one for cars, one for houses, one for spaceships. If you keep all the car pieces together (high cohesion) and don’t mix them with house or spaceship pieces (loose coupling), it’s much easier to build and fix things. If you mix all the pieces together, it’s a mess!

---

## What is High Cohesion?
**Cohesion** refers to how closely related the responsibilities of a single module, class, or function are. 
- **High cohesion** means a module does one thing and does it well.
- **Low cohesion** means a module tries to do too many unrelated things.

### Why is High Cohesion Important?
- **Easier to maintain:** Changes are localized.
- **Easier to understand:** Each part has a clear purpose.
- **Reusability:** Well-defined modules can be reused elsewhere.

---

## What is Loose Coupling?
**Coupling** refers to how much one module depends on others.
- **Loose coupling** means modules interact through simple, well-defined interfaces and know little about each other’s internals.
- **Tight coupling** means modules are highly dependent on each other’s details.

### Why is Loose Coupling Important?
- **Easier to change:** You can modify one module without breaking others.
- **Better testability:** Modules can be tested in isolation.
- **Scalability:** Systems are easier to extend and refactor.

---

## How to Achieve High Cohesion and Loose Coupling
- **Single Responsibility Principle:** Each module/class should have one reason to change.
- **Encapsulation:** Hide internal details; expose only what’s necessary.
- **Use Interfaces/Abstractions:** Depend on contracts, not concrete implementations.
- **Dependency Injection:** Pass dependencies from the outside, rather than creating them inside modules.
- **Event-driven or Observer Patterns:** Allow modules to communicate without direct dependencies.

---

## Example (Python)
```python
# High Cohesion, Loose Coupling Example
class EmailSender:
    def send_email(self, recipient, subject, body):
        # Only handles sending emails
        pass

class UserService:
    def __init__(self, email_sender):
        self.email_sender = email_sender  # Dependency injected
    def register_user(self, user):
        # Only handles user registration
        self.email_sender.send_email(user.email, "Welcome!", "Thanks for registering!")
```
- `EmailSender` is highly cohesive (only sends emails).
- `UserService` is highly cohesive (only handles user logic).
- They are loosely coupled: `UserService` uses `EmailSender` via an interface, not by knowing its internals.

---

## Best Practices
- Refactor large classes into smaller, focused ones.
- Use dependency injection frameworks or patterns.
- Write unit tests to ensure modules work independently.
- Review code for unnecessary dependencies between modules.

---

## References
- [Wikipedia: Cohesion (computer science)](https://en.wikipedia.org/wiki/Cohesion_(computer_science))
- [Wikipedia: Coupling (computer programming)](https://en.wikipedia.org/wiki/Coupling_(computer_programming))
- [Martin Fowler: Inversion of Control Containers and the Dependency Injection pattern](https://martinfowler.com/articles/injection.html)
- [Robert C. Martin: The Single Responsibility Principle](https://web.archive.org/web/20161016153130/http://www.objectmentor.com/resources/articles/srp.pdf) 