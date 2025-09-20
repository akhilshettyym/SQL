# SQL UPDATE Statement

The SQL UPDATE Statement
The UPDATE statement is used to modify the existing records in a table.

## UPDATE Syntax
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

#### Note: Be careful when updating records in a table! Notice the WHERE clause in the UPDATE statement. The WHERE clause specifies which record(s) that should be updated. If you omit the WHERE clause, all records in the table will be updated!

### UPDATE Table
The following SQL statement updates the first customer (CustomerID = 1) with a new contact person and a new city.

ExampleGet your own SQL Server
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;
The selection from the "Customers" table will now look like this:

#### UPDATE Multiple Records
It is the WHERE clause that determines how many records will be updated.

The following SQL statement will update the ContactName to "Juan" for all records where country is "Mexico":

### Example :
UPDATE Customers
SET ContactName='Juan'
WHERE Country='Mexico';
The selection from the "Customers" table will now look like this:

CustomerID	CustomerName	ContactName	Address	City	PostalCode	Country
1

Alfreds Futterkiste	Alfred Schmidt	Obere Str. 57	Frankfurt	12209	Germany
2	Ana Trujillo Emparedados y helados	Juan	Avda. de la Constitución 2222	México D.F.	05021	Mexico
3	Antonio Moreno Taquería	Juan	Mataderos 2312	México D.F.	05023	Mexico
4

Around the Horn	Thomas Hardy	120 Hanover Sq.	London	WA1 1DP	UK
5	Berglunds snabbköp	Christina Berglund	Berguvsvägen 8	Luleå	S-958 22	Sweden
Update Warning!
Be careful when updating records. If you omit the WHERE clause, ALL records will be updated!

### Example :
UPDATE Customers
SET ContactName='Juan';
The selection from the "Customers" table will now look like this:

# SQL DELETE Statement
The SQL DELETE Statement
The DELETE statement is used to delete existing records in a table.

## DELETE Syntax
DELETE FROM table_name WHERE condition;

Note: Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!

### SQL DELETE Example
The following SQL statement deletes the customer "Alfreds Futterkiste" from the "Customers" table:

ExampleGet your own SQL Server
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
The "Customers" table will now look like this:

DELETE FROM table_name;

The following SQL statement deletes all rows in the "Customers" table, without deleting the table:

### Example :
DELETE FROM Customers;
Delete a Table
To delete the table completely, use the DROP TABLE statement:

### Example :
Remove the Customers table:

DROP TABLE Customers;

## SQL TOP, LIMIT, FETCH FIRST or ROWNUM Clause
The SQL SELECT TOP Clause
The SELECT TOP clause is used to specify the number of records to return.

The SELECT TOP clause is useful on large tables with thousands of records. Returning a large number of records can impact performance.

ExampleGet your own SQL Server
Select only the first 3 records of the Customers table:

SELECT TOP 3 * FROM Customers;
Note: Not all database systems support the SELECT TOP clause. MySQL supports the LIMIT clause to select a limited number of records, while Oracle uses FETCH FIRST n ROWS ONLY and ROWNUM.

### SQL Server / MS Access Syntax:

SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;

### MySQL Syntax:
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;

### Oracle 12 Syntax:
SELECT column_name(s)
FROM table_name
ORDER BY column_name(s)
FETCH FIRST number ROWS ONLY;

### Older Oracle Syntax:
SELECT column_name(s)
FROM table_name
WHERE ROWNUM <= number;

### Older Oracle Syntax (with ORDER BY):
SELECT *
FROM (SELECT column_name(s) FROM table_name ORDER BY column_name(s))
WHERE ROWNUM <= number;

## LIMIT
The following SQL statement shows the equivalent example for MySQL:

Example
Select the first 3 records of the Customers table:

SELECT * FROM Customers
LIMIT 3;
FETCH FIRST
The following SQL statement shows the equivalent example for Oracle:

Example
Select the first 3 records of the Customers table:

SELECT * FROM Customers
FETCH FIRST 3 ROWS ONLY;
SQL TOP PERCENT Example
The following SQL statement selects the first 50% of the records from the "Customers" table (for SQL Server/MS Access):

Example
SELECT TOP 50 PERCENT * FROM Customers;
The following SQL statement shows the equivalent example for Oracle:

Example
SELECT * FROM Customers
FETCH FIRST 50 PERCENT ROWS ONLY;
ADD a WHERE CLAUSE
The following SQL statement selects the first three records from the "Customers" table, where the country is "Germany" (for SQL Server/MS Access):

Example
SELECT TOP 3 * FROM Customers
WHERE Country='Germany';
The following SQL statement shows the equivalent example for MySQL:

Example
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;
The following SQL statement shows the equivalent example for Oracle:

Example
SELECT * FROM Customers
WHERE Country='Germany'
FETCH FIRST 3 ROWS ONLY;
ADD the ORDER BY Keyword
Add the ORDER BY keyword when you want to sort the result, and return the first 3 records of the sorted result.

### For SQL Server and MS Access:
Example
Sort the result reverse alphabetically by CustomerName, and return the first 3 records:

SELECT TOP 3 * FROM Customers
ORDER BY CustomerName DESC;
The following SQL statement shows the equivalent example for MySQL:

Example
SELECT * FROM Customers
ORDER BY CustomerName DESC
LIMIT 3;
The following SQL statement shows the equivalent example for Oracle:

Example
SELECT * FROM Customers
ORDER BY CustomerName DESC
FETCH FIRST 3 ROWS ONLY;