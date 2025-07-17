# Namespaces: What are they useful for? Invent an alternative.

## ELI5 (Explain Like I'm 5)
Imagine you and your friend both have a toy car named "Lightning." If you keep your toys in separate boxes with your names on them, you won’t get confused. Namespaces are like those boxes—they keep things with the same name from getting mixed up!

---

## What are Namespaces Useful For?
- Prevent name conflicts in large codebases.
- Organize code into logical groups (modules, packages).
- Make code easier to read and maintain.

---

## Example (Python)
```python
import math
print(math.sqrt(16))  # Uses 'sqrt' from the 'math' namespace
```
- `math.sqrt` is different from any other `sqrt` you might define.

---

## Alternative: Prefixes
- Use unique prefixes for names (e.g., `myapp_`, `lib_`).
- Common in C and JavaScript before modules were standard.
- **Example:** `myapp_calculate()` vs `lib_calculate()`

---

## Other Alternatives
- Use classes or objects to group related functions.
- Use file/folder structure to separate code.

---

## References
- [Python Docs: Modules and Namespaces](https://docs.python.org/3/tutorial/modules.html)
- [MDN Web Docs: Namespaces](https://developer.mozilla.org/en-US/docs/Glossary/Namespace)
- [Stack Overflow: What is a namespace?](https://stackoverflow.com/questions/332396/what-is-a-namespace) 