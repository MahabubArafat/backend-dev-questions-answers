# Multiple Inheritance, Interfaces, and Delegation: Impact on Orthogonality

## ELI5 (Explain Like I'm 5)
Imagine you have a toy robot. If you want it to both walk and talk, you could build a robot that has both walking and talking parts (multiple inheritance). Or, you could give it a remote control that tells it how to walk and another that tells it how to talk (interfaces). Or, you could have a friend robot do the talking for it (delegation). Each way lets your robot do more things, but some ways are easier to manage than others!

---

## What is Multiple Inheritance?
- **Multiple inheritance** means a class can inherit features (methods, properties) from more than one parent class.
- Supported in C++ and Python, but not in Java or C# (for classes).
- **Example (C++):**
```cpp
class Flyer { public: void fly(); };
class Swimmer { public: void swim(); };
class Duck : public Flyer, public Swimmer {};
```
- `Duck` can both fly and swim by inheriting from both `Flyer` and `Swimmer`.

### Pros
- Code reuse from multiple sources.
- Models real-world relationships.

### Cons
- **Diamond Problem:** Ambiguity if two parents have the same method.
- Increased complexity and risk of bugs.

---

## What are Interfaces (and Multiple Interfaces)?
- **Interfaces** define a contract (methods to implement) but no code.
- A class can implement multiple interfaces (TypeScript, Java, C#, Go, etc.).
- **Example (TypeScript):**
```typescript
interface Flyer { fly(): void; }
interface Swimmer { swim(): void; }
class Duck implements Flyer, Swimmer {
    fly() { /* ... */ }
    swim() { /* ... */ }
}
```
- No code is inherited, just the requirement to implement methods.

### Pros
- Avoids the diamond problem.
- Promotes orthogonality (independent features).
- Flexible and safe way to compose behaviors.

### Cons
- No code reuse (only contracts).
- Can lead to boilerplate if many interfaces are implemented.

---

## What is Delegation?
- **Delegation** means a class hands off (delegates) work to another class.
- Promotes composition over inheritance.
- **Example (Python):**
```python
class Flyer:
    def fly(self):
        print("Flying!")
class Duck:
    def __init__(self):
        self.flyer = Flyer()
    def fly(self):
        self.flyer.fly()
```
- `Duck` delegates flying to a `Flyer` object.

### Pros
- Very flexible; avoids inheritance issues.
- Encourages loose coupling and orthogonality.

### Cons
- Slightly more code to write (forwarding methods).

---

## Impact on Orthogonality
- **Orthogonality** means features can be combined independently without side effects.
- **Multiple inheritance** can reduce orthogonality due to ambiguity and tight coupling.
- **Interfaces** and **delegation** promote orthogonality by keeping features independent and composable.

---

## Multiple Inheritance vs Multiple Interfaces
| Aspect                | Multiple Inheritance         | Multiple Interfaces           |
|-----------------------|-----------------------------|-------------------------------|
| Code Reuse            | Yes                         | No (just contracts)           |
| Ambiguity Risk        | Yes (diamond problem)       | No                            |
| Language Support      | C++, Python                 | Java, C#, Go, TypeScript, etc.|
| Orthogonality         | Lower                       | Higher                        |
| Flexibility           | Moderate                    | High                          |

---

## Delegation vs Inheritance
- **Delegation** is more flexible and safer for combining behaviors.
- **Inheritance** is simpler for single hierarchies but can get messy with multiple parents.
- Modern best practice: "Favor composition (delegation) over inheritance."

---

## Best Practices
- Use interfaces or delegation for combining independent features.
- Avoid multiple inheritance unless necessary and your language handles it well.
- Prefer composition for flexibility and maintainability.

---

## References
- [Oracle: Multiple Inheritance of State, Implementation, and Type](https://docs.oracle.com/javase/tutorial/java/IandI/multipleinheritance.html)
- [Microsoft: Inheritance (C# Programming Guide)](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/inheritance)
- [GeeksforGeeks: Multiple Inheritance in C++](https://www.geeksforgeeks.org/multiple-inheritance-in-c/)
- [Forte Group: Favor Composition Over Inheritance](https://fortegrp.com/favor-composition-over-inheritance/)
- [Stack Overflow: Why does Java not support multiple inheritance?](https://stackoverflow.com/questions/53307/why-does-java-not-support-multiple-inheritance)
- [Python Docs: Multiple Inheritance](https://docs.python.org/3/tutorial/classes.html#multiple-inheritance) 