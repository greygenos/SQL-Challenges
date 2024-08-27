# Problem 22: Cumulative Sum

**Problem:** Calculate the cumulative sum of salaries

**Solution:**
```sql
SELECT employee_id, first_name, salary,
       SUM(salary) OVER(ORDER BY employee_id) AS cumulative_salary
FROM employees;
