# Data Mapper vs Active Record: When to use each pattern?

The **Data Mapper** pattern separates the in-memory objects from the database. Unlike Active Record, domain objects do not contain any persistence logic; instead, a separate mapper handles all database interactions. This separation offers greater flexibility and testability, especially for complex domains.

---

## Data Mapper Pattern
- **Separation of Concerns:** Domain objects are pure business logic; mappers handle persistence.
- **Testability:** Easier to unit test domain logic without a database.
- **Flexibility:** Supports complex mapping scenarios, multiple data sources, and different storage backends.
- **Complexity:** More boilerplate and setup compared to Active Record.

---

## Active Record Pattern (Recap)
- **Simplicity:** Combines data and persistence logic in one object.
- **Rapid Development:** Good for simple CRUD applications.
- **Tight Coupling:** Business logic and persistence are mixed.

---

## When to Use Each Pattern
- **Use Active Record when:**
  - The domain is simple and CRUD-focused.
  - You want rapid development and minimal boilerplate.
  - The application is small or a prototype.
- **Use Data Mapper when:**
  - The domain is complex, with rich business logic.
  - You need to decouple business logic from persistence.
  - You want to support multiple storage backends or complex mapping.
  - You require high testability and maintainability.

---

## Example (Pseudo-code)
```python
# Data Mapper Example
class User:
    def deactivate(self):
        self.active = False

class UserMapper:
    def save(self, user):
        # Handles DB logic
        pass
```
- Here, `User` contains only business logic; `UserMapper` handles persistence.

---

## References
- [Martin Fowler: Data Mapper](https://martinfowler.com/eaaCatalog/dataMapper.html)
- [ThoughtWorks: ORM Anti-Patterns](https://martinfowler.com/articles/ormPerformance.html#DataMapper)
- [Wikipedia: Data Mapper Pattern](https://en.wikipedia.org/wiki/Data_mapper_pattern) 