# Problem 19: Recursive Fibonacci Sequence

**Problem:** Generate the first 10 numbers in the Fibonacci sequence

**Solution:**
```sql
WITH RECURSIVE Fibonacci (n, fib) AS (
    SELECT 1 AS n, 0 AS fib
    UNION ALL
    SELECT 2, 1
    UNION ALL
    SELECT n + 1, (SELECT fib FROM Fibonacci WHERE n = Fibonacci.n - 1) + (SELECT fib FROM Fibonacci WHERE n = Fibonacci.n - 2)
    FROM Fibonacci
    WHERE n < 10
)
SELECT * FROM Fibonacci;
