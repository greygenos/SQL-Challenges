# Problem 10: Temporal Tables

**Problem:** Retrieve the state of a row at a specific point in time.

**Solution:**
```sql
SELECT *
FROM employees
FOR SYSTEM_TIME AS OF '2024-01-01T00:00:00';
