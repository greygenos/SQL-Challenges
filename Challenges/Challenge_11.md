# Problem 11: Cross Apply

**Problem:** Retrieve employees and their respective department name using CROSS APPLY.

**Solution:**
```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees e
CROSS APPLY (
  SELECT department_name FROM departments d
  WHERE e.department_id=d.department_id) AS d;
