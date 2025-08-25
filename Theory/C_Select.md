# SQL SELECT Statement
The SQL SELECT Statement.
The SELECT statement is used to select data from a database.

## ExampleGet your own SQL Server
Return data from the Customers table:

## SELECT CustomerName, City FROM Customers;
SELECT column1, column2, ...
FROM table_name;
The table_name represents the name of the table you want to select data from.

## Demo Database
Below is a selection from the Customers table used in the examples:

## Select ALL columns
If you want to return all columns, without specifying every column name, you can use the SELECT * syntax:

Return all the columns from the Customers table: 
**SELECT * FROM Customers;**

# SQL SELECT DISTINCT Statement
The SQL SELECT DISTINCT Statement
The SELECT DISTINCT statement is used to return only distinct (different) values.

## ExampleGet your own SQL Server
Select all the different countries from the "Customers" table:

### SELECT DISTINCT Country FROM Customers;
Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

SELECT DISTINCT column1, column2, ...
FROM table_name;

SELECT Country FROM Customers;

Count Distinct
By using the DISTINCT keyword in a function called COUNT, we can return the number of different countries.

## SELECT COUNT(DISTINCT Country) FROM Customers;
Note: The COUNT(DISTINCT column_name) is not supported in Microsoft Access databases.

**SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);**