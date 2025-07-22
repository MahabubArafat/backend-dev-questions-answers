# Code Comments: Are comments in code useful? Should they be avoided as much as possible?

## ELI5 (Explain Like I'm 5)
Imagine you’re building a LEGO set and you find a note that says, “This piece goes here because it makes the door open.” That note helps you understand why something was done a certain way. But if every piece had a note saying “This is a LEGO brick,” it wouldn’t help at all! Good comments explain the “why,” not the obvious “what.”

---

## Are Comments Useful?
- **Yes, when used well:** Comments can explain the intent, reasoning, or context behind code, especially when it’s not obvious.
- **No, when overused or misused:** Comments that just repeat what the code says, or become outdated, can clutter code and cause confusion.

---

## When to Use Comments
- **Explain Why, Not What:** Use comments to explain why something is done, not what is being done (which should be clear from the code itself).
- **Clarify Complex Logic:** If a piece of code is tricky or uses a non-obvious workaround, explain it.
- **Document Assumptions or Side Effects:** Note any important assumptions, limitations, or side effects.
- **TODOs and FIXMEs:** Mark places where improvements or fixes are needed.

---

## When to Avoid Comments
- **Obvious Code:** Don’t comment things that are self-explanatory.
- **Redundant Comments:** Avoid comments that just restate the code.
- **Outdated Comments:** Remove or update comments that no longer match the code.

---

## Example
### Bad Comment
```python
def add(a, b):
    # This function adds two numbers
def add(a, b):
    return a + b
```
- The comment is unnecessary; the code is clear.

### Good Comment
```python
def calculate_discount(price, user):
    # VIP users get a 20% discount as part of the loyalty program
    if user.is_vip:
        return price * 0.8
    return price
```
- The comment explains the business reason for the discount.

---

## Best Practices
- Write clear, self-explanatory code first; use comments to explain intent or complex logic.
- Keep comments up to date.
- Use comments to document “why,” not “what.”
- Prefer meaningful names for variables and functions to reduce the need for comments.

---

## References
- [Clean Code by Robert C. Martin](https://www.oreilly.com/library/view/clean-code/9780136083238/)
- [Wikipedia: Comment (computer programming)](https://en.wikipedia.org/wiki/Comment_(computer_programming))
- [Stack Overflow: When should I comment code?](https://stackoverflow.com/questions/184618/when-should-i-comment-code) 