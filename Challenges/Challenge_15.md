# Problem 15: Windows Functions: NTILE()
**Problem:** Distribute employees into 4 quartiles based on their salary.

**Solution:**
```sql
SELECT employee_id, first_name, salary,
  NTILE(4) OVER(ORDER BY salary) AS quartile
FROM employees;
