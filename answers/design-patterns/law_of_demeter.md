# What is the Law of Demeter? (With code example)

The **Law of Demeter** (LoD), also known as the "Principle of Least Knowledge," states that a module or object should only interact with its immediate friends and not with strangers. In practice, this means you should avoid chaining calls to objects returned by other objects ("train wrecks").

---

## Violating the Law of Demeter (Bad Example)
```python
# Bad: Chained calls violate LoD
order.customer.address.city
```
- Here, `order` knows about `customer`, `address`, and `city`—too many layers.
- If the structure of `customer` or `address` changes, all code using this chain breaks.

---

## Why is this a bad design?
- **Tight Coupling:** Code is tightly coupled to the internal structure of objects.
- **Fragility:** Changes in one class ripple through the codebase.
- **Difficult to Test:** Harder to mock or stub dependencies in tests.

---

## Fixing the Violation (Good Example)
```python
# Good: Expose what you need directly
class Order:
    def get_customer_city(self):
        return self.customer.address.city

# Usage
order.get_customer_city()
```
- Now, only `Order` knows about its internals. Callers don't need to know the structure of `customer` or `address`.

---

## Best Practices
- Only call methods of:
  - The object itself
  - Its fields
  - Objects created by itself
  - Objects passed as arguments
- Avoid long chains of method calls.

---

## References
- [Wikipedia: Law of Demeter](https://en.wikipedia.org/wiki/Law_of_Demeter)
- [Brad Appleton: Demeter Transmogrified](http://www.bradapp.net/docs/demeter-intro.html)
- [Martin Fowler: Demeter](https://martinfowler.com/bliki/LawOfDemeter.html) 