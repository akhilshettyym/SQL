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

| ProductID | ProductName                  | SupplierID | CategoryID | Unit                | Price |
| --------- | ---------------------------- | ---------- | ---------- | ------------------- | ----- |
| 1         | Chais                        | 1          | 1          | 10 boxes x 20 bags  | 18    |
| 2         | Chang                        | 1          | 1          | 24 - 12 oz bottles  | 19    |
| 3         | Aniseed Syrup                | 1          | 2          | 12 - 550 ml bottles | 10    |
| 4         | Chef Anton's Cajun Seasoning | 2          | 2          | 48 - 6 oz jars      | 22    |
| 5         | Chef Anton's Gumbo Mix       | 2          | 2          | 36 boxes            | 21.35 |

### Specify Column
If you specify a column name instead of *, NULL values will not be counted.
Example - 
Find the number of products where the ProductName is not null:
SELECT COUNT(ProductName)
FROM Products;


### Add a WHERE Clause :
You can add a WHERE clause to specify conditions.
Example - 
Find the number of products where Price is higher than 20:

SELECT COUNT(ProductID)
FROM Products
WHERE Price > 20;
