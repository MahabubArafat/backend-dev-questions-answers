# What is an Anti-corruption Layer?

An **Anti-corruption Layer (ACL)** is a design pattern used in software architecture, especially in Domain-Driven Design (DDD), to protect a system's domain model from the influence of external systems or legacy code. It acts as a boundary that translates and adapts data and interactions, ensuring that the internal model remains clean and consistent.

---

## Why use an Anti-corruption Layer?
- **Isolate Domain Logic:** Prevents external models, terminology, and logic from "corrupting" your domain model.
- **Translation:** Converts data and requests between your system and external systems.
- **Decoupling:** Allows your system to evolve independently of external systems.
- **Integration:** Useful when integrating with legacy systems, third-party APIs, or microservices with different models.

---

## How does it work?
- The ACL sits between your domain and the external system.
- It uses adapters, translators, or facades to:
  - Map external data structures to internal ones (and vice versa)
  - Translate commands, queries, and events
  - Handle protocol or API differences

---

## Example (Pseudo-code)
```python
# External system returns a legacy Customer object
class LegacyCustomer:
    def __init__(self, legacy_id, full_name):
        self.legacy_id = legacy_id
        self.full_name = full_name

# Anti-corruption Layer translates to internal model
class CustomerAdapter:
    def __init__(self, legacy_customer):
        self.id = legacy_customer.legacy_id
        self.name = legacy_customer.full_name

# Internal code uses CustomerAdapter, not LegacyCustomer
```

---

## When to Use
- Integrating with legacy systems or third-party APIs
- Migrating from a monolith to microservices
- Protecting a clean domain model from external changes

---

## References
- [Domain-Driven Design: Anti-Corruption Layer](https://martinfowler.com/bliki/AntiCorruptionLayer.html)
- [Vaughn Vernon: Implementing Domain-Driven Design](https://www.oreilly.com/library/view/implementing-domain-driven-design/9780133039900/)
- [Microsoft: Anti-Corruption Layer pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/anti-corruption-layer) 