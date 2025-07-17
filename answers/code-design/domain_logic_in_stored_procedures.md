# Domain Logic in Stored Procedures: Pros and Cons

## ELI5 (Explain Like I'm 5)
Imagine you have a toy factory. You can either put the instructions for building toys in the machines (the database) or give them to the workers (the application). If the machines know the instructions, they can build toys quickly, but it’s harder to change the instructions. If the workers have the instructions, it’s easier to update them, but they might be slower. That’s the difference between putting logic in stored procedures (machines) and in application code (workers).

---

## What are Stored Procedures?
- **Stored procedures** are sets of SQL statements stored and executed on the database server.
- They can contain business/domain logic, such as calculations, validations, or data transformations.

---

## Pros of Holding Domain Logic in Stored Procedures
- **Performance:** Logic runs close to the data, reducing network latency and round-trips.
- **Atomicity:** Complex operations can be executed as a single transaction.
- **Security:** Sensitive logic stays on the server; permissions can be tightly controlled.
- **Consistency:** Centralizes logic, so all applications using the database follow the same rules.
- **Reduced Data Transfer:** Only the results are sent to the application, not all intermediate data.

---

## Cons of Holding Domain Logic in Stored Procedures
- **Maintainability:** SQL and procedural languages (like PL/pgSQL, T-SQL) are less expressive and harder to test than modern application languages.
- **Version Control:** Harder to track changes and manage deployments compared to application code.
- **Portability:** Stored procedures are often database-specific, making migrations difficult.
- **Testing:** Unit testing and automated testing are more challenging.
- **Separation of Concerns:** Mixing business logic with data access can lead to tightly coupled systems.
- **Developer Skills:** Requires developers to be proficient in both application and database languages.

---

## Example
### Business Logic in a Stored Procedure (PostgreSQL)
```sql
CREATE OR REPLACE FUNCTION apply_discount(price NUMERIC, is_vip BOOLEAN)
RETURNS NUMERIC AS $$
BEGIN
    IF is_vip THEN
        RETURN price * 0.8;
    ELSE
        RETURN price;
    END IF;
END;
$$ LANGUAGE plpgsql;
```
- The discount logic is in the database, not the application.

---

## When to Use Stored Procedures for Domain Logic
- When performance is critical and logic is data-intensive.
- When you need to enforce rules across multiple applications.
- When you want to limit data access for security reasons.

## When to Avoid
- When you need portability across databases.
- When you want to use modern development tools, testing, and CI/CD pipelines.
- When business logic changes frequently.

---

## Best Practices
- Keep stored procedures focused and well-documented.
- Use version control for database scripts.
- Prefer application code for complex or frequently changing logic.
- Use stored procedures for performance-critical, data-centric operations.

---

## References
- [Microsoft: Benefits and Drawbacks of Using Stored Procedures](https://learn.microsoft.com/en-us/sql/relational-databases/stored-procedures/stored-procedures-database-engine)
- [Percona: Should You Put Business Logic in the Database?](https://www.percona.com/blog/2018/10/23/should-you-put-business-logic-in-the-database/)
- [ThoughtWorks: Business Logic in the Database](https://www.thoughtworks.com/insights/blog/business-logic-database)
- [Stack Overflow: Pros and cons of putting logic in stored procedures](https://stackoverflow.com/questions/124973/advantages-and-disadvantages-of-stored-procedures)
- [Redgate: The Pros and Cons of Stored Procedures](https://www.red-gate.com/simple-talk/databases/sql-server/t-sql-programming-sql-server/the-pros-and-cons-of-stored-procedures/) 