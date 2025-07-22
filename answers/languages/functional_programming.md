# Functional Programming: Why is there a rising interest?

## ELI5 (Explain Like I'm 5)
Imagine you have a magic kitchen where every time you make a sandwich, the ingredients never run out and nothing ever gets messy. That’s what functional programming is like—no leftovers, no mess, just clean results every time!

---

## Why the Rising Interest?
- **Immutability:** Data doesn’t change, so fewer bugs from unexpected changes.
- **Easier to Test:** Functions always give the same output for the same input (pure functions).
- **Concurrency:** Safe to run code in parallel (no shared state).
- **Modularity:** Code is broken into small, reusable functions.
- **Modern Hardware:** Multi-core CPUs benefit from functional approaches.
- **Influence of Big Data:** Tools like Spark, Scala, and F# use functional ideas for large-scale data processing.

---

## Example (Python)
```python
def double(x):
    return x * 2
nums = [1, 2, 3]
doubled = list(map(double, nums))  # [2, 4, 6]
```
- No variables are changed; the function just returns a new value.

---

## References
- [Martin Fowler: Functional Programming](https://martinfowler.com/articles/functional-programming.html)
- [Stack Overflow: Why is functional programming becoming more popular?](https://stackoverflow.com/questions/204339/why-is-functional-programming-becoming-more-popular)
- [FreeCodeCamp: Why Functional Programming is on the Rise](https://www.freecodecamp.org/news/why-functional-programming-is-on-the-rise/) 