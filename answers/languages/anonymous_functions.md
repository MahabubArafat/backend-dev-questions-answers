# Anonymous Functions: Example and Usefulness

## ELI5 (Explain Like I'm 5)
Imagine you need a helper just once to carry your bag across the street. You don’t give them a name—you just ask for help and move on. An anonymous function is like that helper: a function you use once, without naming it!

---

## What is an Anonymous Function?
- A function without a name, often created for short-term use.
- In Python, these are called `lambda` functions.

---

## Example (Python)
```python
nums = [1, 2, 3, 4]
squared = list(map(lambda x: x * x, nums))  # [1, 4, 9, 16]
```
- The `lambda` function is used just once to square each number.

---

## Why Use Anonymous Functions?
- **Conciseness:** Write quick, throwaway functions without cluttering code.
- **Functional Programming:** Useful with `map`, `filter`, `reduce`, etc.
- **Callbacks:** Handy for event handlers or short-lived logic.

---

## References
- [Python Docs: Lambda Expressions](https://docs.python.org/3/tutorial/controlflow.html#lambda-expressions)
- [MDN Web Docs: Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Stack Overflow: What is an anonymous function?](https://stackoverflow.com/questions/1819124/what-is-an-anonymous-function) 