# Bad Design: What would you do to understand if your code has a bad design?

## ELI5 (Explain Like I'm 5)
Imagine you built a LEGO castle, but every time you want to add a new room, you have to take the whole thing apart. Or, if you want to change the door, the windows fall off! If building or changing things is hard, your design might be bad. Good design means you can make changes easily without breaking everything else.

---

## How to Recognize Bad Code Design

### 1. **Hard to Change or Extend**
- Small changes require editing code in many places.
- Adding new features is difficult or risky.

### 2. **Difficult to Understand**
- Code is confusing, poorly named, or lacks clear structure.
- New developers struggle to figure out what’s going on.

### 3. **Tight Coupling and Low Cohesion**
- Modules/classes depend heavily on each other (tight coupling).
- Classes or functions do too many unrelated things (low cohesion).

### 4. **Code Duplication**
- The same logic appears in multiple places (violates DRY principle).

### 5. **Lack of Tests or Hard-to-Test Code**
- Code is not covered by automated tests, or is hard to test due to dependencies or complexity.

### 6. **Frequent Bugs and Regression**
- Fixing one bug causes others to appear.
- Code is fragile and breaks easily.

### 7. **Long Methods or Classes**
- Functions or classes are very large and try to do too much.

---

## What to Do If You Suspect Bad Design
- **Code Review:** Ask peers to review your code for clarity, structure, and maintainability.
- **Refactoring:** Break large functions/classes into smaller, focused ones. Remove duplication.
- **Add Tests:** Write unit tests to catch regressions and clarify expected behavior.
- **Use Design Principles:** Apply SOLID, DRY, KISS, and YAGNI principles.
- **Automated Tools:** Use linters, static analysis, and code quality tools to spot issues.
- **Documentation:** Document intent and design decisions to help others (and your future self).

---

## Example: Signs of Bad Design
```python
# Bad: One class does everything
class GodClass:
    def read_file(self): ...
    def write_file(self): ...
    def process_data(self): ...
    def send_email(self): ...
    def calculate_salary(self): ...
# Hard to test, maintain, or extend
```

---

## Best Practices
- Regularly review and refactor code.
- Keep functions and classes small and focused.
- Favor composition over inheritance.
- Write and maintain automated tests.
- Encourage open feedback and code reviews.

---

## References
- [Refactoring Guru: Code Smells](https://refactoring.guru/refactoring/smells)
- [Martin Fowler: Is This Code Bad?](https://martinfowler.com/bliki/IsThisCodeBad.html)
- [ThoughtWorks: How to Recognize Bad Code](https://www.thoughtworks.com/insights/blog/how-recognize-bad-code)
- [Stack Overflow: How to identify bad code?](https://stackoverflow.com/questions/1376324/how-to-identify-bad-code)
- [Google Engineering Practices: Code Review Guide](https://google.github.io/eng-practices/review/)
