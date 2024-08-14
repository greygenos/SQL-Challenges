# Problem 8: JSON Data Handling

**Problem:** Retrieve specific values from a JSON column.

**Solution:**
```sql
SELECT JSON_VALUE(data, '$.name') AS name,
       JSON_VALUE(data, '$.age') AS age
FROM json_table;
