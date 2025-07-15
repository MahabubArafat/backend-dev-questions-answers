# What is the N+1 Problem and how do you fix it?

The **N+1 problem** is a common performance issue in applications using ORMs (Object-Relational Mappers) with lazy loading. It occurs when the application first queries for a list of parent records (1 query), and then, for each parent, issues an additional query to load related child records (N queries), resulting in N+1 total queries.

---

## Example
Suppose you have `Author` and `Book` tables, and you want to list all authors and their books:

```python
# Pseudo-code
for author in get_all_authors():
    print(author.name)
    for book in author.books:  # Triggers a query per author
        print(book.title)
```
- This results in 1 query to get all authors, and then 1 query per author to get their books.
- For 100 authors, this means 101 queries!

---

## Why is it a problem?
- **Performance:** Many small queries are much slower than a single, well-optimized query.
- **Scalability:** The problem gets worse as the number of parent records increases.

---

## How to Fix the N+1 Problem
- **Eager Loading / Preloading:** Fetch related data in a single query using `JOIN` or ORM-specific features.
    - **Django:** Use `select_related` or `prefetch_related`.
    - **SQLAlchemy:** Use `joinedload` or `subqueryload`.
    - **Hibernate:** Use `fetch join`.
    - **Entity Framework:** Use `.Include()`.
- **Batch Queries:** Some ORMs can batch related queries to reduce the number of round-trips.

**Example (Django):**
```python
# Eager loading books with authors
for author in Author.objects.prefetch_related('books').all():
    print(author.name)
    for book in author.books.all():
        print(book.title)
```

**Example (SQL):**
```sql
SELECT a.name, b.title
FROM authors a
LEFT JOIN books b ON b.author_id = a.id;
```

---

## Best Practices
- Always check ORM documentation for eager loading options.
- Profile your queries in development and staging.
- Use database query logs or ORM debug output to detect N+1 issues.

---

## References
- [Martin Fowler: ORM Performance Anti-Patterns](https://martinfowler.com/articles/ormPerformance.html#TheN1Problem)
- [Django Docs: select_related and prefetch_related](https://docs.djangoproject.com/en/stable/topics/db/queries/#select-related-objects)
- [SQLAlchemy Docs: Relationship Loading Techniques](https://docs.sqlalchemy.org/en/20/orm/queryguide/relationships.html)
- [Hibernate Docs: Fetching Strategies](https://docs.jboss.org/hibernate/orm/current/userguide/html_single/Hibernate_User_Guide.html#fetching) 