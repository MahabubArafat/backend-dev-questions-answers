# Is goto evil? What is your opinion on the use of goto?

## ELI5 (Explain Like I'm 5)
Imagine you’re reading a story, but every few pages, the book tells you, “Go to page 42!” or “Jump back to page 10!” It gets confusing, right? That’s what using `goto` in code can feel like—it jumps all over the place, making it hard to follow the story.

---

The `goto` statement allows a program to jump to another line of code, breaking the normal flow. While it can be useful in rare cases, it is generally discouraged in modern programming.

---

## Why is goto considered harmful?
- **Spaghetti Code:** Code with lots of `goto` statements is hard to read and maintain.
- **Hard to Debug:** Jumps make it difficult to trace the flow of execution.
- **Error-Prone:** Easy to introduce bugs, especially in large codebases.
- **Breaks Structure:** Ignores structured programming principles (loops, functions, conditionals).

---

## Are there any good uses for goto?
- **Low-Level Programming:** Sometimes used in system programming, device drivers, or assembly language.
- **Error Handling:** In C, `goto` is sometimes used for cleanup in functions with multiple exit points.
- **Performance:** Rarely, for performance-critical code where structured alternatives are less efficient.

---

## Modern Alternatives
- Use loops, functions, exceptions, and structured control flow instead of `goto`.
- Most modern languages (Python, Java, JavaScript) don’t even have `goto`.

---

## Example (C)
```c
// Bad: Using goto for control flow
if (error1) goto cleanup;
if (error2) goto cleanup;
// ...
cleanup:
    // cleanup code
```
- In C, this is sometimes used for resource cleanup, but alternatives like functions or RAII (in C++) are preferred.

---

## References
- [Wikipedia: Go To Statement](https://en.wikipedia.org/wiki/Goto)
- [Edsger Dijkstra: Go To Statement Considered Harmful](https://homepages.cwi.nl/~storm/teaching/reader/Dijkstra68.pdf)
- [Stack Overflow: Is goto ever useful?](https://stackoverflow.com/questions/3517726/what-is-wrong-with-using-goto) 