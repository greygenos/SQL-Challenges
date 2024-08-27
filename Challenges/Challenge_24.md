# Problem 24: Rank Densely

**Problem:** Densely rank employees based on their salary within their department.

**Solution:**
```sql
SELECT department_id, employee_id, first_name, salary,
       DENSE_RANK() OVER(PARTITION BY department_id ORDER BY salary DESC) AS dense_rank
FROM employees;
