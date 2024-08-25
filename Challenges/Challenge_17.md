# Problem 17: Rolling Sum

**Problem:** Calculate rolling sum of salaries over a window of 3 rows

**Solution:**
```sql
SELECT employee_id, first_name, salary,
  SUM(salary) OVER(ORDER BY employee_id ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) AS rolling_sum
FROM employees;
