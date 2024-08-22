# Problem 16: Hierarchichal Data

**Problem:** Retrieve the entire organizational chart of a company.

**Solution:**
```sql
WITH RECURSIVE OrgChart AS (
  SELECT employee_id, first_name, manager_id
  FROM employees
  WHERE manager_id IS NULL
  UNION ALL
  SELECT e.employee_id, e.first_name, e.manager_id
  FROM employees e
  INNER JOIN OrgChart o ON e.manager_id = o.employee_id
)
SELECT * FROM OrgChart
