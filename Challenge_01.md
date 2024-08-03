# Problem 1: Recursive Common Table Expression (CTE)

**Problem:** Retrieve the hierarchy of employees and their managers.

**Solution:**
```sql
WITH RECURSIVE EmployeeHierarchy AS (
    SELECT employee_id, first_name, manager_id
    FROM employees
    WHERE manager_id IS NULL
    UNION ALL
    SELECT e.employee_id, e.first_name, e.manager_id
    FROM employees e
    INNER JOIN EmployeeHierarchy eh ON e.manager_id = eh.employee_id
)
SELECT * FROM EmployeeHierarchy;
