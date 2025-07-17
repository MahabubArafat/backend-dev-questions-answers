# Exceptions: Why do some languages have no exceptions by design? Pros and Cons

## ELI5 (Explain Like I'm 5)
Imagine you’re playing a game, and if you make a mistake, you have to stop and start over. Some games let you keep playing and just fix the mistake. Some programming languages don’t use exceptions—they want you to handle mistakes right away, not stop everything!

---

## Why Do Some Languages Avoid Exceptions?
- **Predictability:** No hidden jumps in control flow; errors are handled explicitly.
- **Performance:** Avoids the overhead of exception handling.
- **Simplicity:** Forces developers to handle errors directly (e.g., return values like `Result` or `Option`).
- **Safety:** Makes error handling visible and explicit.

---

## Pros
- Easier to reason about code flow.
- Fewer surprises (no hidden exceptions).
- Can improve performance in critical systems.

## Cons
- More boilerplate (manual error checking everywhere).
- Can make code harder to read if not managed well.
- Less convenient for quick prototyping.

---

## Example (Rust)
```rust
fn divide(a: i32, b: i32) -> Option<i32> {
    if b == 0 {
        None
    } else {
        Some(a / b)
    }
}
```
- No exceptions; caller must check the result.

---

## References
- [Rust Book: Error Handling](https://doc.rust-lang.org/book/ch09-02-recoverable-errors-with-result.html)
- [Go Blog: Error Handling](https://go.dev/blog/error-handling)
- [Stack Overflow: Why do some languages not have exceptions?](https://stackoverflow.com/questions/2259270/why-do-some-languages-not-have-exceptions) 