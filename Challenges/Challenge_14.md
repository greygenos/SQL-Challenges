# Problem 14: Merge Statement

**Problem:** Merge new employee data into the employees table.

**Solution:**
```sql
MERGE INTO employees AS target
USING new_employees AS source
ON target.employee_id = source.employee_id
WHEN MATCHED THEN
    UPDATE SET target.first_name = source.first_name, target.last_name = source.last_name
WHEN NOT MATCHED BY TARGET THEN
    INSERT (employee_id, first_name, last_name) VALUES (source.employee_id, source.first_name, source.last_name)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
