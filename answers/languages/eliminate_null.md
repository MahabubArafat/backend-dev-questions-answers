# Eliminate Null: How would you remove null references from a language?

## ELI5 (Explain Like I'm 5)
Imagine you have a toy box, but sometimes you reach in and find nothing—no toy at all! That’s what a `null` is in programming. If you never want to find an empty spot, you need a way to always have something, or a clear sign that there’s nothing there.

---

## How to Remove Null References
- **Option/Maybe Types:** Use a special type that can be “something” or “nothing” (e.g., `Optional`, `Maybe`).
- **Non-nullable by Default:** Make all variables non-nullable unless explicitly allowed.
- **Compiler Checks:** Use static analysis to prevent nulls.

---

## Example (TypeScript)
```typescript
function findUser(id: number): User | undefined {
    // returns a User or undefined (never null)
}
let user = findUser(1);
if (user) {
    // safe to use user
}
```
- TypeScript’s `strictNullChecks` helps prevent null errors.

---

## Consequences
- **Fewer Bugs:** Null reference errors (“billion dollar mistake”) are avoided.
- **More Explicit Code:** Developers must handle the “nothing” case.
- **Slightly More Verbose:** More checks and handling required.
- **Better Safety:** Code is safer and more predictable.

---

## References
- [Wikipedia: Option type](https://en.wikipedia.org/wiki/Option_type)
- [Kotlin Docs: Null Safety](https://kotlinlang.org/docs/null-safety.html)
- [Stack Overflow: How to avoid null references?](https://stackoverflow.com/questions/2713988/how-to-avoid-null-references) 