# Robustness Principle: What is it and why does it matter?

## ELI5 (Explain Like I'm 5)
Imagine you’re playing catch with a friend. You always try to throw the ball gently and straight (be careful with what you send), but you’re ready to catch the ball even if it’s a little off or bouncy (be tolerant with what you receive). That’s the robustness principle!

---

**The Robustness Principle** (also known as Postel’s Law) says: “Be conservative in what you send, be liberal in what you accept.” It’s a guideline for designing software systems, especially protocols and APIs.

---

## What does it mean?
- **Be strict/careful in what you output:** Only send well-formed, valid data.
- **Be tolerant/flexible in what you input:** Accept and handle a wider range of inputs, even if they’re not perfect.

---

## Why is it important?
- **Interoperability:** Helps different systems work together, even if they’re not perfectly implemented.
- **Resilience:** Makes systems more robust to errors, changes, or unexpected data.
- **Backward Compatibility:** Allows new versions to work with old ones.

---

## Practical Implications
- **Protocols:** Web browsers accept imperfect HTML, but try to render it anyway.
- **APIs:** A tolerant API might accept extra fields in JSON input, ignoring what it doesn’t understand.
- **Security Caution:** Too much tolerance can hide bugs or security issues—balance is needed.

---

## Criticisms
- Can encourage sloppy implementations if taken too far.
- May make debugging harder if errors are silently ignored.

---

## References
- [Wikipedia: Robustness Principle](https://en.wikipedia.org/wiki/Robustness_principle)
- [IETF RFC 1122: Requirements for Internet Hosts](https://datatracker.ietf.org/doc/html/rfc1122#section-1.2.2)
- [Postel’s Law: The Robustness Principle Reconsidered](https://tools.ietf.org/html/draft-iab-protocol-maintenance-07) 