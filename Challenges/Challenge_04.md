# Problem 4: LEAD() and LAG()

**Problem:** Compare each employee’s salary with the next and previous employee’s salary within their department.

**Solution:**
```sql
SELECT department_id, employee_id, first_name, salary,
       LAG(salary) OVER(PARTITION BY department_id ORDER BY salary) AS previous_salary,
       LEAD(salary) OVER(PARTITION BY department_id ORDER BY salary) AS next_salary
FROM employees;
