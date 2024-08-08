# Problem 6: Pivot Table

**Problem:** Create a pivot table showing the count of employees in each department by job title.

**Solution:**
```sql
SELECT department_id,
       SUM(CASE WHEN job_title = 'Manager' THEN 1 ELSE 0 END) AS Managers,
       SUM(CASE WHEN job_title = 'Engineer' THEN 1 ELSE 0 END) AS Engineers,
       SUM(CASE WHEN job_title = 'Analyst' THEN 1 ELSE 0 END) AS Analysts
FROM employees
GROUP BY department_id;
