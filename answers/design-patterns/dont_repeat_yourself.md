# Don't Repeat Yourself (DRY): What is it, and how do you fix violations?

## ELI5 (Explain Like I'm 5)
Imagine you have to tell your friend the same story every day. Wouldn't it be easier to write it down once and just hand them the paper? The DRY principle is about not repeating yourself—write things once, and reuse them!

---

**The DRY Principle** says: "Every piece of knowledge must have a single, unambiguous, authoritative representation within a system." In other words, don't copy-paste code or logic —  Reuse it instead.

---

## Code Violating DRY (Bad Example)
```python
def calculate_area_of_square(side):
    return side * side

def calculate_area_of_rectangle(width, height):
    return width * height

def calculate_area_of_big_square(big_side):
    return big_side * big_side
```
- The logic for calculating the area of a square is repeated in two places.

---

## Why is this bad?
- **Hard to Maintain:** If you need to change the logic, you must update it everywhere.
- **Bug-Prone:** Easy to miss a spot and introduce inconsistencies.
- **Bloated Code:** More code to read, test, and debug.

---

## Fixed Example (Good Practice)
```python
def calculate_area_of_square(side):
    return calculate_area_of_rectangle(side, side)

def calculate_area_of_rectangle(width, height):
    return width * height

def calculate_area_of_big_square(big_side):
    return calculate_area_of_square(big_side)
```
- Now, the logic for area calculation is in one place and reused.

---

## Best Practices
- Extract repeated code into functions, classes, or modules.
- Use constants or configuration files for repeated values.
- Refactor regularly to eliminate duplication.

---

## References
- [Wikipedia: Don't Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
- [The Pragmatic Programmer: DRY Principle](https://pragprog.com/tips/tips.pdf)
- [Martin Fowler: DRY](https://martinfowler.com/bliki/DRY.html) 