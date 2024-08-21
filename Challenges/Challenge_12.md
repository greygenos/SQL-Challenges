# Problem 12: Outer Apply

**Problem:** Retrieve employees and their respective department name, including those without a department, using OUTER APPLY.

**Solution:**
```sql
SELECT e.first_name, e.last_name, d.department_name
FROM employees
OUTER APPLY (
  SELECT department_name FROM departments d
  WHERE e.department_id = d.department_id) AS d
