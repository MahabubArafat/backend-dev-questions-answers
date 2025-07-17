# Cohesion vs Coupling: What's the difference between cohesion and coupling?

## ELI5 (Explain Like I'm 5)
Imagine you have a team building a LEGO city. If each person works only on their own building (high cohesion), and they don’t need to constantly ask each other for help (loose coupling), the city gets built faster and with fewer mistakes. If everyone is working on everything and always interrupting each other, it’s confusing and slow!

---

## What is Cohesion?
- **Cohesion** is about how closely the tasks within a single module, class, or function are related to each other.
- **High cohesion:** All parts of a module work together to achieve a single, well-defined purpose.
- **Low cohesion:** The module does many unrelated things.

### Example (High Cohesion)
```python
class EmailSender:
    def send_email(self, recipient, subject, body):
        # Only handles sending emails
        pass
```
- All methods are related to sending emails.

---

## What is Coupling?
- **Coupling** is about how much one module, class, or function depends on others.
- **Loose coupling:** Modules interact through simple, well-defined interfaces and know little about each other’s details.
- **Tight coupling:** Modules are highly dependent on each other’s internal workings.

### Example (Loose Coupling)
```python
class UserService:
    def __init__(self, email_sender):
        self.email_sender = email_sender  # Dependency injected
    def register_user(self, user):
        self.email_sender.send_email(user.email, "Welcome!", "Thanks for registering!")
```
- `UserService` depends only on the interface of `EmailSender`, not its internal details.

---

## Key Differences
| Aspect    | Cohesion                        | Coupling                        |
|-----------|----------------------------------|---------------------------------|
| Definition| How related tasks are within a module | How much modules depend on each other |
| Goal      | High cohesion                   | Loose coupling                  |
| Benefit   | Easier to maintain, understand  | Easier to change, test, extend  |

---

## Why Do They Matter?
- **High cohesion** makes code easier to maintain and understand.
- **Loose coupling** makes code easier to change and test.
- Good software design aims for both: high cohesion within modules, loose coupling between modules.

---

## Best Practices
- Group related functionality together (high cohesion).
- Minimize dependencies between modules (loose coupling).
- Use interfaces or abstractions to reduce coupling.
- Refactor code regularly to improve both.

---

## References
- [Wikipedia: Cohesion (computer science)](https://en.wikipedia.org/wiki/Cohesion_(computer_science))
- [Wikipedia: Coupling (computer programming)](https://en.wikipedia.org/wiki/Coupling_(computer_programming))
- [Martin Fowler: Inversion of Control Containers and the Dependency Injection pattern](https://martinfowler.com/articles/injection.html) 