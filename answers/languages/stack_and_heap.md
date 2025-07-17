# Stack and Heap: What are they? What's a stack overflow?

## ELI5 (Explain Like I'm 5)
Imagine your toys are in two places: a stack of plates (stack) and a big toy box (heap). The stack is neat and you always take the top plate first. The heap is a jumble—you can grab any toy, but it’s messier!

---

## What is a Stack?
- A region of memory for function calls and local variables.
- Last-In, First-Out (LIFO): The last thing added is the first taken out.
- Fast, but limited in size.

## What is a Heap?
- A region of memory for dynamic allocation (objects, data that outlives a function).
- Can grow as needed, but slower to access.

## What is a Stack Overflow?
- Happens when the stack runs out of space (e.g., too many nested function calls).
- Causes the program to crash.

---

## Example (Python)
```python
def recurse():
    return recurse()

# recurse()  # Uncommenting this will cause a stack overflow
```

---

## References
- [Medium: Stack vs Heap](https://medium.com/fhinkel/confused-about-stack-and-heap-2cf3e6adb771)
- [GeeksforGeeks: Stack vs Heap](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)
- [Stack Overflow: What is stack overflow?](https://stackoverflow.com/questions/6924195/what-is-stack-overflow) 