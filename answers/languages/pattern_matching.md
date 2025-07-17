# Pattern Matching: What is it and how is it different from switch clauses?

## ELI5 (Explain Like I'm 5)
Imagine you have a box of different-shaped blocks. Pattern matching is like having a special tool that can pick out the right block based on its shape, not just its color or size. It’s smarter than just checking one thing!

---

## What is Pattern Matching?
- A way to check a value against a pattern and extract data if it matches.
- More powerful than a simple `switch` or `if-else` because it can match on structure, types, and values.

---

## Example (Python 3.10+)
```python
def describe(value):
    match value:
        case 0:
            return "zero"
        case [x, y]:
            return f"a list with two elements: {x}, {y}"
        case {"name": name}:
            return f"a dict with a name: {name}"
        case _:
            return "something else"
```
- Matches on value, list structure, and dictionary keys.

---

## Pattern Matching vs Switch
- **Switch:** Checks a single value against constants.
- **Pattern Matching:** Can match on structure, types, and extract data.
- More expressive and flexible.

---

## References
- [Python Docs: Structural Pattern Matching](https://docs.python.org/3/reference/compound_stmts.html#the-match-statement)
- [MDN Web Docs: Pattern Matching](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch#alternatives)
- [Stack Overflow: What is pattern matching?](https://stackoverflow.com/questions/2349107/what-is-pattern-matching) 