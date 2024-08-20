# Problem 8: XML Data Handling

**Problem:** Retrieve specific values from an XML column.

**Solution:**
```sql
SELECT xml_column.value('(/employee/name)[1]', 'VARCHAR(100)') AS name,
       xml_column.value('(/employee/age)[1]', 'INT') AS age
FROM xml_table;

