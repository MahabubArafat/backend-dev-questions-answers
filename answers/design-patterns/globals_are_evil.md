# Why are global and static objects considered evil? (With code example)

Global and static objects are often discouraged in software design because they introduce hidden dependencies, make code harder to test, and can lead to bugs that are difficult to trace.

---

## Why are globals and statics problematic?
- **Hidden Dependencies:** Any part of the code can change a global, making it hard to reason about state.
- **Testing Difficulty:** Tests may interfere with each other due to shared state, making tests unreliable.
- **Concurrency Issues:** Globals can cause race conditions in multi-threaded environments.
- **Tight Coupling:** Code becomes tightly coupled to global state, reducing modularity and reusability.

---

## Code Example (Bad Practice)
```python
# Python example with a global variable
config = {}

def set_config(key, value):
    global config
    config[key] = value

def get_config(key):
    return config.get(key)

# Any part of the code can change config, leading to bugs
```

---

## How to Avoid
- Pass dependencies explicitly (dependency injection).
- Use instance variables or context objects.
- Limit the scope of shared state.

---

## Fixed Example (Good Practice)
```python
class Config:
    def __init__(self):
        self._data = {}
    def set(self, key, value):
        self._data[key] = value
    def get(self, key):
        return self._data.get(key)

# Each part of the code can have its own Config instance
```

---

## References
- [Stack Overflow: Why are global variables evil?](https://stackoverflow.com/questions/484635/are-global-variables-bad)
- [Wikipedia: Global Variable](https://en.wikipedia.org/wiki/Global_variable)
- [Martin Fowler: Inversion of Control](https://martinfowler.com/bliki/InversionOfControl.html) 