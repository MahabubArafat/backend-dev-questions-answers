# Design vs Architecture: What is the difference between design and architecture?

## ELI5 (Explain Like I'm 5)
Imagine you’re building a house. The architect decides how many rooms there will be, where the kitchen goes, and how the house will stand up. The designer picks the colors, where the furniture goes, and how to make each room comfortable. Both are important, but they focus on different things!

---

## What is Software Architecture?
- **Architecture** is the high-level structure of a software system.
- It defines the main components, how they interact, and the guiding principles and constraints.
- Architecture answers: “What are the big building blocks? How do they fit together?”

### Examples
- Choosing between a monolith or microservices.
- Deciding to use a layered architecture (e.g., presentation, business logic, data access).
- Selecting major technologies (e.g., database, messaging system).

---

## What is Software Design?
- **Design** is about the details of how each part of the system is built.
- It focuses on the internal structure of modules, classes, functions, and their interactions.
- Design answers: “How does each building block work inside? How do we implement the details?”

### Examples
- Designing a class hierarchy for user accounts.
- Choosing data structures and algorithms for a feature.
- Deciding how to handle errors within a module.

---

## Key Differences
| Aspect         | Architecture                                 | Design                                      |
|---------------|----------------------------------------------|---------------------------------------------|
| Scope         | System-wide, high-level                      | Component/module/class-level, detailed      |
| Focus         | Structure, components, interactions          | Implementation, algorithms, patterns        |
| Decisions     | What are the main parts? How do they connect?| How does each part work?                    |
| Impact        | Harder to change later                       | Easier to change/refactor                   |

---

## Why Does the Distinction Matter?
- **Clear Roles:** Helps teams divide responsibilities (architects vs. developers/designers).
- **Better Planning:** Big decisions (architecture) are made early; details (design) can evolve.
- **Maintainability:** Good architecture supports good design and makes future changes easier.

---

## Best Practices
- Start with architecture to set the foundation, then move to detailed design.
- Document both architecture and design decisions.
- Review architecture and design regularly as the system evolves.

---

## References
- [Martin Fowler: Who Needs an Architect?](https://martinfowler.com/ieeeSoftware/whoNeedsArchitect.pdf)
- [Wikipedia: Software architecture](https://en.wikipedia.org/wiki/Software_architecture)
- [Wikipedia: Software design](https://en.wikipedia.org/wiki/Software_design) 