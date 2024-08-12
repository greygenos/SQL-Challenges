# Problem 7: Dynamic SQL

**Problem:** Construct and execute a dynamic SQL Query to retrieve data from specified table.

**Solution:**
```sql
DECLARE @tablename NVARCHAR(50) = 'employees';
DECLARE @sql NVARCHAR(MAX) = 'SELECT * FROM' + @ tablename,
EXEC sp_executesql @sql;
