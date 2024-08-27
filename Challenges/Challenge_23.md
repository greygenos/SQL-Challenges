# Problem 23: Generating Series

**Problem:** Generating a series of dates
**Solution:**
```sql
WITH RECURSIVE DateSeries AS (
    SELECT DATE('2024-01-01') AS date
    UNION ALL
    SELECT date + INTERVAL 1 DAY
    FROM DateSeries
    WHERE date < '2024-01-10'
)
SELECT * FROM DateSeries;
