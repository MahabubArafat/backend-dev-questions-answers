# Why do array indexes start with 0 in most languages?

## ELI5 (Explain Like I'm 5)
Imagine you have a row of boxes, and you want to count them. If you start at the very first box and call it 0, then the number on each box tells you how many steps you need to take from the start to reach it. So, the first box is 0 steps away, the second is 1 step away, and so on. This makes it easy for the computer to find the right box!

---

## The Technical Reason
Most programming languages (like C, Java, Python) use **zero-based indexing** for arrays. This means the first element is at index 0, the second at index 1, and so on.

### Why?
- **Pointer Arithmetic:** In low-level languages like C, an array is stored as a block of memory. The name of the array points to the start of this block. The index tells the computer how many steps (offsets) to move from the start.
    - For example, `array[3]` means: start at the beginning, move 3 steps forward.
    - If arrays started at 1, the math would be more complicated (you’d always have to subtract 1).
- **Historical Reasons:** Early languages like C and BCPL used 0-based indexing for simplicity and efficiency. Later languages followed this convention.
- **Mathematical Consistency:** Many mathematical formulas and algorithms (like calculating offsets, ranges, and lengths) are simpler with 0-based indexing.

---

## Example (C)
```c
int arr[5] = {10, 20, 30, 40, 50};
// arr[0] is 10, arr[1] is 20, ...
// The address of arr[0] is the base address
// arr[n] = *(arr + n)
```
- `arr[0]` is at the base address (no offset).
- `arr[1]` is at base address + 1 element size.

---

## Why Not Start at 1?
- Some languages (like Fortran, Lua, MATLAB) do use 1-based indexing.
- However, 0-based indexing is more common in modern general-purpose languages because it matches how memory is addressed in hardware and makes calculations easier.

---

## Best Practices
- Always check the documentation for the language you’re using.
- Be careful when translating algorithms between languages with different indexing conventions.

---

## References
- [Dijkstra: Why numbering should start at zero](https://www.cs.utexas.edu/users/EWD/transcriptions/EWD08xx/EWD831.html)
- [Wikipedia: Zero-based indexing](https://en.wikipedia.org/wiki/Zero-based_numbering)
- [Stack Overflow: Why do arrays start at zero?](https://stackoverflow.com/questions/49941/why-do-arrays-start-at-zero) 