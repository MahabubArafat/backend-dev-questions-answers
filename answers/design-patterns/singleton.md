# Singleton Pattern: How to write a thread-safe Singleton?

## ELI5 (Explain Like I'm 5)
Imagine you have a magic remote control that can turn on the lights in your house. But you only want ONE remote, so nobody gets confused. The Singleton pattern is like making sure there is only one magic remote in the whole house, no matter how many people try to make a new one. If someone tries to make another, they just get the same remote!

---

The **Singleton** pattern ensures that a class has only one instance and provides a global point of access to it. While simple in concept, writing a thread-safe Singleton—especially in multi-threaded environments—requires care.

---

## Basic Singleton (Not Thread-Safe)
```python
class Singleton:
    _instance = None
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance
```
- This version is **not thread-safe**: two threads could create two instances at the same time.

---

## Thread-Safe Singleton (Python Example)
### Using a Lock
```python
import threading

class Singleton:
    _instance = None
    _lock = threading.Lock()

    def __new__(cls):
        if cls._instance is None:
            with cls._lock:
                if cls._instance is None:
                    cls._instance = super().__new__(cls)
        return cls._instance
```
- The double-checked locking pattern ensures only one instance is created, even with multiple threads.

### Using a Decorator (Pythonic)
```python
def singleton(cls):
    instances = {}
    def get_instance(*args, **kwargs):
        if cls not in instances:
            instances[cls] = cls(*args, **kwargs)
        return instances[cls]
    return get_instance

@singleton
class MyClass:
    pass
```

---

## Other Languages
- **Java:** Use `synchronized`, `volatile`, or the "Initialization-on-demand holder" idiom.
- **C#:** Use `static` constructors or `Lazy<T>`.

---

## Pitfalls
- **Global State:** Singletons can introduce hidden dependencies and make testing harder.
- **Concurrency:** Incorrect implementations can lead to multiple instances.
- **Lifecycle Management:** Hard to control destruction or re-initialization.

---

## References
- [Wikipedia: Singleton Pattern](https://en.wikipedia.org/wiki/Singleton_pattern)
- [Python Patterns: Singleton](https://python-3-patterns-idioms-test.readthedocs.io/en/latest/Singleton.html)
- [Java: Effective Java, Item 3: Enforce the singleton property with a private constructor or an enum type](https://www.oreilly.com/library/view/effective-java-3rd/9780134686097/) 