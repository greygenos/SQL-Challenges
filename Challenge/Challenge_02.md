
# Problem 2: Window Functions: ROW_NUMBER()

**Problem:** Assign a row number to each employee within their department.

**Solution:**
```sql
SELECT department_id, employee_id, first_name,
       ROW_NUMBER() OVER(PARTITION BY department_id ORDER BY salary DESC) AS row_num
FROM employees;
