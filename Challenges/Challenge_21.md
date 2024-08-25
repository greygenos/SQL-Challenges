# Problem 21: Finding Gaps in a Sequence

**Problem:** Identify gaps in a sequence of employee IDs
**Solution:**
```sql
SELECT (t1.employee_id + 1) AS start_gap, (t2.employee_id - 1) AS end_gap
FROM employees t1, employees t2
WHERE t1.employee_id < t2.employee_id
AND NOT EXISTS (SELECT 1 FROM employees t3 WHERE t3.employee_id = t1.employee_id + 1)
AND t2.employee_id > t1.employee_id + 1
ORDER BY start_gap;
