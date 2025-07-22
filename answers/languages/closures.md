# Closures: What are they and what are they useful for?

## ELI5 (Explain Like I'm 5)
Imagine you have a backpack. You can put things in it and carry it around. A closure is like a function with a backpack—it remembers the stuff (variables) you gave it, even after you leave the room!

---

## What is a Closure?
- A closure is a function that "remembers" the variables from the place where it was created, even after that place is gone.
- Useful for creating functions with private data or customizing behavior.

---

## Example (Python)
```python
def make_multiplier(factor):
    def multiplier(x):
        return x * factor  # Remembers 'factor' from outer scope
    return multiplier

double = make_multiplier(2)
print(double(5))  # 10
```
- `double` remembers that `factor` is 2, even after `make_multiplier` is done.

---

## Closures vs Classes
- Both can store data and behavior together.
- Closures use functions and variables; classes use objects and attributes.
- Classes are more flexible for complex structures; closures are lightweight for simple cases.

---

## References
- [Python Docs: Closures](https://docs.python.org/3/tutorial/classes.html#python-scopes-and-namespaces)
- [MDN Web Docs: Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
- [Stack Overflow: What are closures?](https://stackoverflow.com/questions/4020419/closures-in-python) 