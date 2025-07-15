# What is ACID in Databases?

**ACID** is an acronym for four key properties of database transactions: **Atomicity, Consistency, Isolation, and Durability**. These properties ensure reliable processing of database transactions, even in the presence of errors, power failures, or other mishaps. ACID is a foundational concept in relational databases and is also relevant for many NoSQL systems.

---

## Atomicity
- **Definition:** A transaction is an indivisible unit; it either completes in full or does not happen at all.
- **Example:** If you transfer money from Account A to Account B, both the debit and credit must succeed. If one fails, neither change is saved.
- **How it's achieved:** Databases use mechanisms like write-ahead logs or undo logs to roll back incomplete transactions.

## Consistency
- **Definition:** A transaction brings the database from one valid state to another, maintaining all predefined rules (constraints, cascades, triggers, etc.).
- **Example:** If a column is defined as NOT NULL, a transaction cannot leave it null.
- **How it's achieved:** The database enforces constraints before committing a transaction.

## Isolation
- **Definition:** Concurrent transactions do not interfere with each other. The result is as if transactions were executed serially, one after another.
- **Example:** If two users transfer money at the same time, each transaction is isolated and does not see the other's intermediate state.
- **How it's achieved:** Databases use locks, multi-version concurrency control (MVCC), or other techniques to isolate transactions. Isolation levels (e.g., Read Committed, Serializable) define the strictness.

## Durability
- **Definition:** Once a transaction is committed, its changes are permanent, even in the event of a system crash.
- **Example:** After a successful transfer, the new balances remain even if the server loses power immediately after.
- **How it's achieved:** Databases write changes to non-volatile storage (disk, SSD) and often use transaction logs to recover committed transactions after a crash.

---

## Why is ACID Important?
- **Reliability:** Ensures data integrity and correctness, even in the face of failures.
- **Predictability:** Developers can reason about the state of the database after transactions.
- **Industry Standard:** Most relational databases (e.g., PostgreSQL, MySQL, Oracle, SQL Server) guarantee ACID properties for transactions.

---

## References
- [Wikipedia: ACID](https://en.wikipedia.org/wiki/ACID)
- [PostgreSQL Documentation: Transactions](https://www.postgresql.org/docs/current/tutorial-transactions.html)
- [Oracle: ACID Properties](https://docs.oracle.com/cd/E17952_01/mysql-8.0-en/glossary.html#glos_acid)
- [Martin Kleppmann, Designing Data-Intensive Applications, O'Reilly, 2017] 