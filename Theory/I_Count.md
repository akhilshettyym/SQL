# SQL COUNT() Function

The `COUNT()` function returns the number of rows that matches a specified criterion.

---

## Example
Find the total number of rows in the **Products** table:

```sql
SELECT COUNT(*)
FROM Products;

SELECT COUNT(column_name)
FROM table_name
WHERE condition;