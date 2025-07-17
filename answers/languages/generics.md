# Generics: What are they useful for?

## ELI5 (Explain Like I'm 5)
Imagine you have a box that can hold anything: toys, books, or snacks. Generics are like that box—they let you write code that works with any type, not just one specific thing!

---

## What are Generics?
- Generics let you write functions, classes, or data structures that work with any data type.
- They help you avoid code duplication and make code safer (type checking).

---

## Example (TypeScript)
```typescript
function identity<T>(value: T): T {
    return value;
}
let num = identity(5);      // T is number
let text = identity('hi');  // T is string
```
- The same function works for numbers, strings, or anything else.

---

## Why Use Generics?
- **Reusability:** Write code once, use it for any type.
- **Type Safety:** Catch errors at compile time.
- **Cleaner Code:** Avoids copy-pasting similar code for different types.

---

## References
- [TypeScript Handbook: Generics](https://www.typescriptlang.org/docs/handbook/generics.html)
- [Oracle: Generics in Java](https://docs.oracle.com/javase/tutorial/java/generics/why.html)
- [Stack Overflow: What are generics?](https://stackoverflow.com/questions/2920297/what-are-generics-in-java) 