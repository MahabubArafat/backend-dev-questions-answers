# How do tests and TDD influence code design?

## ELI5 (Explain Like I'm 5)
Imagine you’re building a LEGO castle, but before you add each new piece, you check if it fits and if the castle is still strong. If something doesn’t fit, you fix it right away. That’s what writing tests before code (TDD) is like—it helps you build things the right way from the start!

---

## What is TDD?
**Test-Driven Development (TDD)** is a software development process where you:
1. Write a test for a new feature or function.
2. Write the minimum code needed to pass the test.
3. Refactor the code while keeping the test passing.
4. Repeat for each new feature or change.

---

## How Do Tests and TDD Influence Code Design?
- **Forces Simplicity:** You write only the code needed to pass the test, avoiding unnecessary complexity.
- **Encourages Modularity:** Code is broken into small, testable units (functions, classes, modules).
- **Improves Interfaces:** You design code from the perspective of how it will be used (since you write the test first).
- **Promotes Loose Coupling:** To make code testable, dependencies are injected or abstracted, reducing tight coupling.
- **Enables Refactoring:** With tests in place, you can safely improve code structure without fear of breaking functionality.
- **Documentation:** Tests serve as living documentation for how the code is supposed to work.

---

## Example (Python)
```python
# Step 1: Write a test
import unittest
class TestAdder(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)

# Step 2: Write minimal code to pass the test
def add(a, b):
    return a + b

# Step 3: Refactor if needed (already simple here)
```
- The function `add` is simple, focused, and easy to test.

---

## Best Practices
- Write tests before code (when possible).
- Keep functions and classes small and focused.
- Use dependency injection to make code more testable.
- Refactor code regularly, using tests as a safety net.
- Treat tests as part of the codebase, not an afterthought.

---

## References
- [Kent Beck: Test-Driven Development by Example](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530)
- [Martin Fowler: Test-Driven Development](https://martinfowler.com/bliki/TestDrivenDevelopment.html)
- [Wikipedia: Test-driven development](https://en.wikipedia.org/wiki/Test-driven_development) 