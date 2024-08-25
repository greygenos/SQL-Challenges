# Problem 20: Self-Referencing Data

**Problem:** Retrieve all employees who report directly or indirectly to s specific manager

**Solution:**
```sql
WITH RECURSIVE ReportsTo AS (
  SELECT employee_id, first_name, manager_id
    FROM employees
    WHERE manager_id = 101
    UNION ALL
    SELECT e.employee_id, e.first_name, e.manager_id
    FROM employees e
    INNER JOIN ReportsTo r ON e.manager_id = r.employee_id
)
SELECT * FROM ReportsTo;
