# Problem 18: Correlated subquery

**Problem:** Retrieve employees whose salary is above the average salary of their department

**Solution:**
```sql
SELECT e1.employee_id, e1.first_name, e1.salary
FROM employees e1
WHERE e1.salary > (SELECT AVG(e2.salary) FROM employees e2 WHERE e2.department_id = e1.department_id);
