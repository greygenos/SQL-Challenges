# Problem 3: Window-functions-rank

**Problem:** Retrieve the hierarchy of employees and their managers.

**Solution:**
```sql
SELECT department_id, employee_id, first_name, salary,
       RANK() OVER(PARTITION BY department_id ORDER BY salary DESC) AS salary_rank
FROM employees;
