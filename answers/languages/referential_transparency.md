# Referential Transparency: Transparent vs Opaque Functions

## ELI5 (Explain Like I'm 5)
Imagine you have a magic box. If you put in the same toy every time and always get the same result, the box is predictable (transparent). If sometimes you get a different result, it’s a mystery box (opaque)!

---

## Referentially Transparent Function
- Always gives the same output for the same input.
- No side effects (doesn’t change anything outside itself).

### Example (Python)
```python
def add(a, b):
    return a + b
```
- `add(2, 3)` always returns `5`.

## Referentially Opaque Function
- Output can change, or it has side effects.

### Example (Python)
```python
import random
def add_random(a):
    return a + random.randint(1, 10)
```
- `add_random(2)` can return different results each time.

---

## Why Does It Matter?
- Referential transparency makes code easier to test, reason about, and refactor.
- Opaque functions can be harder to debug and maintain.

---

## References
- [Wikipedia: Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency)
- [Stack Overflow: What is referential transparency?](https://stackoverflow.com/questions/210835/what-is-referential-transparency)
- [GeeksforGeeks: Referential Transparency](https://www.geeksforgeeks.org/referential-transparency/) 