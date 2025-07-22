# Functions as First-Class Citizens: What does it mean and why is it important?

## ELI5 (Explain Like I'm 5)
Imagine you can give someone a recipe, put it in a box, or even hand it to a friend. In some languages, you can do the same with functions—they’re like objects you can pass around!

---

## What Does It Mean?
- Functions can be assigned to variables, passed as arguments, and returned from other functions.
- They are treated like any other value (numbers, strings, etc.).

---

## Why Is It Important?
- **Flexibility:** Enables powerful programming patterns (callbacks, event handlers, decorators).
- **Abstraction:** Makes code more modular and reusable.
- **Functional Programming:** Core to functional programming paradigms.

---

## Example (Python)
```python
def greet(name):
    return f"Hello, {name}!"

say_hello = greet  # Assign function to variable
print(say_hello("Alice"))  # Hello, Alice!

def run_func(func, value):
    return func(value)

print(run_func(greet, "Bob"))  # Hello, Bob!
```

---

## References
- [Python Docs: Functions as Objects](https://docs.python.org/3/tutorial/controlflow.html#functions-as-objects)
- [MDN Web Docs: First-class functions](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function)
- [Stack Overflow: What are first-class functions?](https://stackoverflow.com/questions/7051732/what-are-first-class-functions) 