# How would you manage database schema migrations?

Database schema migrations are the process of evolving a database schema over time, in a controlled and automated way, as the application changes. Managing schema migrations well is critical for application stability, developer productivity, and deployment automation.

---

## Key Principles
- **Version Control:** Treat schema changes as code. Store migration scripts in version control (e.g., Git).
- **Repeatability:** Migrations should be idempotent or safely repeatable.
- **Automation:** Apply migrations automatically as part of deployment or CI/CD pipelines.
- **Rollback:** Support rolling back changes if a migration fails.

---

## Common Tools
- **Flyway** ([flywaydb.org](https://flywaydb.org/))
- **Liquibase** ([liquibase.org](https://www.liquibase.org/))
- **Alembic** (for SQLAlchemy/Python)
- **Rails Active Record Migrations** (for Ruby on Rails)
- **Entity Framework Migrations** (for .NET)
- **Knex.js** (for Node.js)

---

## Typical Workflow
1. **Write Migration Scripts**
   - Create migration files (SQL or DSL) for each schema change (e.g., add table, alter column).
   - Name and number migrations sequentially (e.g., `V001__create_users.sql`).

2. **Store in Version Control**
   - Commit migration scripts alongside application code.

3. **Apply Migrations**
   - Use a migration tool to apply pending migrations to the database.
   - Tools track which migrations have been applied (often via a special table).

4. **Automate in CI/CD**
   - Integrate migration steps into deployment pipelines.
   - Run migrations before or as part of application deployment.

5. **Rollback/Undo**
   - Write "down" or rollback scripts for each migration, if supported.
   - Test rollbacks as part of the migration process.

---

## Best Practices
- **Test migrations on staging environments before production.**
- **Avoid destructive changes (e.g., dropping columns) without backups.**
- **Communicate schema changes to the team.**
- **Keep migrations small and incremental.**

---

## References
- [Flyway: Database Migrations Made Easy](https://flywaydb.org/documentation/)
- [Liquibase: Best Practices](https://docs.liquibase.com/concepts/bestpractices.html)
- [Martin Fowler: Evolutionary Database Design](https://martinfowler.com/articles/evodb.html)
- [ThoughtWorks: Database Migration Strategies](https://www.thoughtworks.com/insights/blog/database-migration-strategies) 