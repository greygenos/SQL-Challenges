# Problem 5: Percentile Calculation

**Problem:** Calculate the percentile rank of each employee’s salary within their department.

**Solution:**
```sql
SELECT department_id, employee_id, first_name, salary,
       PERCENT_RANK() OVER(PARTITION BY department_id ORDER BY salary) AS percentile_rank
FROM employees;
