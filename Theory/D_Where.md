# SQL WHERE Clause
The SQL WHERE Clause
The WHERE clause is used to filter records.

It is used to extract only those records that fulfill a specified condition.

ExampleGet your own SQL Server
Select all customers from Mexico:

SELECT * FROM Customers
WHERE Country='Mexico';
Syntax
SELECT column1, column2, ...
FROM table_name
WHERE condition;

Note: The WHERE clause is not only used in SELECT statements, it is also used in UPDATE, DELETE, etc.!

## Text Fields vs. Numeric Fields
SQL requires single quotes around text values (most database systems will also allow double quotes).

However, numeric fields should not be enclosed in quotes:

Example
SELECT * FROM Customers
WHERE CustomerID=1;
Operators in The WHERE Clause
You can use other operators than the = operator to filter the search.

## Example :
Select all customers with a CustomerID greater than 80:

SELECT * FROM Customers
WHERE CustomerID > 80;

### SQL ORDER BY Keyword
The SQL ORDER BY
The ORDER BY keyword is used to sort the result-set in ascending or descending order.

ExampleGet your own SQL Server
Sort the products by price:

SELECT * FROM Products
ORDER BY Price;
Syntax
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;

## DESC
The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

### Example :
Sort the products from highest to lowest price:

SELECT * FROM Products
ORDER BY Price DESC;
Order Alphabetically
For string values the ORDER BY keyword will order alphabetically:

### Example:
Sort the products alphabetically by ProductName:

SELECT * FROM Products
ORDER BY ProductName;
Alphabetically DESC
To sort the table reverse alphabetically, use the DESC keyword:

### Example :
Sort the products by ProductName in reverse order:

SELECT * FROM Products
ORDER BY ProductName DESC;
ORDER BY Several Columns
The following SQL statement selects all customers from the "Customers" table, sorted by the "Country" and the "CustomerName" column. This means that it orders by Country, but if some rows have the same Country, it orders them by CustomerName:

### Example :
SELECT * FROM Customers
ORDER BY Country, CustomerName;
Using Both ASC and DESC
The following SQL statement selects all customers from the "Customers" table, sorted ascending by the "Country" and descending by the "CustomerName" column:

### Example :
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;