# Static and Dynamic Typing: Strong vs Weak Type Systems

## ELI5 (Explain Like I'm 5)
Imagine you have two toy boxes. In one, you label each spot for a specific toy (static typing). In the other, you can put any toy anywhere (dynamic typing). Strong typing means you can’t put a toy car in a spot for a teddy bear, while weak typing lets you mix things up more easily (sometimes causing problems!).

---

## Static Typing
- Types are checked at compile time (before running the program).
- Examples: Java, C, C++, TypeScript, Rust.
- **Pros:** Catches errors early, better tooling, safer for large codebases.
- **Cons:** More code to write (type annotations), less flexible.

## Dynamic Typing
- Types are checked at runtime (while the program runs).
- Examples: Python, JavaScript, Ruby, PHP.
- **Pros:** Flexible, faster to write, good for rapid prototyping.
- **Cons:** More runtime errors, harder to refactor large codebases.

## Strong vs Weak Typing
- **Strong typing:** Language prevents mixing incompatible types (e.g., adding a string to a number).
- **Weak typing:** Language may convert types automatically (sometimes unexpectedly).
- **Example:**
    - Python (strong, dynamic): `'5' + 2` → error
    - JavaScript (weak, dynamic): `'5' + 2` → `'52'`

---

## Opinion & When to Use Which
- **Enterprise Software:** Prefer static, strong typing for safety, maintainability, and tooling (e.g., Java, TypeScript, Rust).
- **Prototyping/Scripting:** Dynamic typing is great for quick development (e.g., Python, JavaScript).
- **Hybrid:** Some languages (TypeScript, Kotlin) offer both static and dynamic features.

---

## References
- [TypeScript Handbook: Static vs Dynamic Typing](https://www.typescriptlang.org/docs/handbook/basic-types.html)
- [Python Docs: Dynamic Typing](https://docs.python.org/3/reference/datamodel.html)
- [Stack Overflow: Static vs Dynamic Typing](https://stackoverflow.com/questions/2690544/static-vs-dynamic-typing) 