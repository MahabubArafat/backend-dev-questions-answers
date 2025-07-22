# 3 Worst Defects of Python (Example Preferred Language)

## ELI5 (Explain Like I'm 5)
Python is like a super flexible LEGO set, but sometimes the pieces are a bit slow, can break if you’re not careful, and sometimes you don’t know what shape a piece is until you try to use it!

---

## 1. **Performance (Speed)**
- Python is slower than compiled languages like C++ or Java because it’s interpreted.
- Not ideal for CPU-intensive tasks (e.g., heavy math, real-time systems).
- **Example:** Processing millions of images is much slower in Python than in C++.

## 2. **Dynamic Typing (Type Safety)**
- Python doesn’t require you to declare variable types, which can lead to bugs that only show up at runtime.
- **Example:** Accidentally adding a string to a number (`'5' + 2`) causes a crash only when the code runs.

## 3. **Global Interpreter Lock (GIL)**
- Python’s GIL prevents true multi-threading for CPU-bound tasks.
- Limits performance on multi-core systems for certain workloads.
- **Example:** Running two CPU-heavy tasks in threads doesn’t use both CPU cores efficiently.

---

## Other Notable Defects
- Packaging and dependency management can be confusing.
- Version compatibility issues (Python 2 vs 3).

---

## References
- [Python Wiki: Performance](https://wiki.python.org/moin/PythonSpeed/PerformanceTips)
- [Real Python: The GIL Explained](https://realpython.com/python-gil/)
- [Stack Overflow: What are the main drawbacks of Python?](https://stackoverflow.com/questions/1136747/what-are-the-main-drawbacks-of-python) 