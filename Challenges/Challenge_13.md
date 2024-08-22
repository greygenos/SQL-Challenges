# Problem 13: Full-Text Search

**Problem:** Perform a full-text search to find employees with specific keywords in their job descriptions.

**Solution:**
```sql
SELECT * FROM employees
WHERE CONTAINS(job_description, 'developer OR engineer');
