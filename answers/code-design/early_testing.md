# Early Testing: In TDD, why are tests written before code?

## ELI5 (Explain Like I'm 5)
Imagine you’re building a toy car, but before you start, you draw a finish line and say, “My car must cross this line.” You build the car, test it, and fix it until it works. Writing the test first helps you know when you’re done and makes sure your car really works!

---

## Why Write Tests Before Code in TDD?
**Test-Driven Development (TDD)** is a process where you write tests before writing the code that makes them pass. This approach has several benefits:

- **Clarifies Requirements:** Writing tests first forces you to think about what the code should do before you write it.
- **Guides Design:** Tests define the interface and expected behavior, leading to simpler, more modular code.
- **Prevents Overengineering:** You only write the code needed to pass the test, avoiding unnecessary features.
- **Immediate Feedback:** You know right away if your code works as intended.
- **Safer Refactoring:** With tests in place, you can change code confidently, knowing tests will catch mistakes.
- **Encourages Simplicity:** Code is written to satisfy specific requirements, not guesses about future needs.

---

## Example (Python)
```python
# Step 1: Write the test first
import unittest
class TestAdder(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)

# Step 2: Write the minimal code to pass the test
def add(a, b):
    return a + b
```
- The test defines what “correct” means before any code is written.

---

## Best Practices
- Write small, focused tests for each feature or function.
- Let tests drive the design of your code.
- Refactor code only when tests are passing.
- Use tests as living documentation for your code’s behavior.

---

## References
- [Forte Group: What are the advantages of test-driven development?](https://fortegrp.com/test-driven-development-benefits/)
- [Agilemania: Benefits Of Test-Driven Development – A Guide For Beginners](https://agilemania.com/benefits-of-tdd-test-driven-development)
- [ConformIQ: The Six Benefits of Test-Driven Development](https://www.conformiq.com/resources/blog-the-six-benefits-of-test-driven-development-05-16-2023)
- [Andrew Webster: Five Good Reasons to Use Test-Driven Development](https://blog.andrewwebster.dev/2019/04/five-good-reasons-to-use-test-driven.html)
- [Kent Beck: Test-Driven Development by Example](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530)
- [Martin Fowler: Test-Driven Development](https://martinfowler.com/bliki/TestDrivenDevelopment.html)
- [Wikipedia: Test-driven development](https://en.wikipedia.org/wiki/Test-driven_development) 