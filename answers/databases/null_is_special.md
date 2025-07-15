# Why do databases treat NULL as a special case?

In SQL and most relational databases, `NULL` represents the absence of a value or an unknown value. It is not the same as zero, an empty string, or any other default value. This special treatment of `NULL` leads to unique behavior in queries and comparisons.

---

## Key Points about NULL

- **NULL means "unknown" or "missing" value.**
- **NULL is not equal to anything, even another NULL.**
- **Special operators are required to check for NULL.**

---

## Why does `WHERE field = NULL` not match records with NULL?

- In SQL, any comparison with `NULL` (e.g., `field = NULL`, `field <> NULL`) results in `UNKNOWN`, not `TRUE` or `FALSE`.
- This is because `NULL` is not a value, but a marker for missing information. The result of `field = NULL` is not true, even if `field` is `NULL`.
- To check for `NULL`, you must use the `IS NULL` or `IS NOT NULL` operators:

```sql
SELECT * FROM table WHERE field IS NULL;
```

---

## Three-Valued Logic in SQL
- SQL uses three-valued logic: `TRUE`, `FALSE`, and `UNKNOWN`.
- Any operation involving `NULL` generally results in `UNKNOWN`.
- Rows are only returned by a `WHERE` clause if the condition evaluates to `TRUE`.

---

## Example
Suppose you have a table:

| id | value   |
|----|---------|
| 1  | apple   |
| 2  | NULL    |
| 3  | orange  |

- `SELECT * FROM table WHERE value = NULL;` returns **no rows**.
- `SELECT * FROM table WHERE value IS NULL;` returns the row with `id = 2`.

---

## Why is this important?
- Ensures that missing or unknown data is handled explicitly.
- Prevents accidental matches or logic errors in queries.
- Forces developers to consider the presence of missing data.

---

## References
- [PostgreSQL: NULL Handling](https://www.postgresql.org/docs/current/datatype-null.html)
- [MySQL: Working with NULL Values](https://dev.mysql.com/doc/refman/8.0/en/working-with-null.html)
- [Wikipedia: Null (SQL)](https://en.wikipedia.org/wiki/Null_(SQL)) 