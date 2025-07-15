# How would you find the most expensive queries in an application?

Finding the most expensive (slowest or most resource-intensive) queries is crucial for database performance tuning. This process typically involves monitoring, logging, and analyzing query execution times and resource usage.

---

## Methods to Find Expensive Queries

### 1. **Database Query Logs**
- **Enable slow query logging** in your database (supported by MySQL, PostgreSQL, SQL Server, etc.).
- Logs queries that exceed a certain execution time threshold.
- Example (MySQL):
  ```sql
  SET GLOBAL slow_query_log = 'ON';
  SET GLOBAL long_query_time = 1; -- log queries slower than 1 second
  ```
- Example (PostgreSQL):
  ```sql
  SET log_min_duration_statement = 1000; -- log queries slower than 1 second
  ```

### 2. **Database Performance Tools**
- Use built-in tools or extensions:
  - **MySQL:** `SHOW PROCESSLIST`, `EXPLAIN`, `performance_schema`
  - **PostgreSQL:** `pg_stat_statements`, `EXPLAIN ANALYZE`
  - **SQL Server:** Query Store, Activity Monitor
- These tools can show query frequency, average duration, and resource usage.

### 3. **Application Performance Monitoring (APM)**
- Use APM tools (e.g., New Relic, Datadog, AppDynamics) to trace slow queries from the application side.
- These tools often provide end-to-end transaction tracing.

### 4. **Manual Profiling**
- Use `EXPLAIN` or `EXPLAIN ANALYZE` to understand query plans and identify bottlenecks.
- Profile queries in development and staging environments.

---

## Best Practices
- Regularly review slow query logs and performance dashboards.
- Optimize indexes and query structure based on findings.
- Test changes in a staging environment before deploying to production.
- Automate alerts for slow queries in production.

---

## References
- [MySQL: The Slow Query Log](https://dev.mysql.com/doc/refman/8.0/en/slow-query-log.html)
- [PostgreSQL: Monitoring Database Activity](https://www.postgresql.org/docs/current/monitoring-stats.html)
- [SQL Server: Query Store](https://learn.microsoft.com/en-us/sql/relational-databases/performance/query-store)
- [DigitalOcean: How To Find Slow Queries in MySQL](https://www.digitalocean.com/community/tutorials/how-to-find-slow-queries-in-mysql) 