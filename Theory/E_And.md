## SQL AND Operator

The SQL AND Operator
The WHERE clause can contain one or many AND operators.

The AND operator is used to filter records based on more than one condition, like if you want to return all customers from Spain that starts with the letter 'G':

ExampleGet your own SQL Server
Select all customers from Spain that starts with the letter 'G':
SELECT *
FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%';
Syntax
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;

## AND vs OR
The AND operator displays a record if all the conditions are TRUE.

The OR operator displays a record if any of the conditions are TRUE.

All Conditions Must Be True
The following SQL statement selects all fields from Customers where Country is "Brazil" AND City is "Rio de Janeiro" AND CustomerID is higher than 50:

### Example :
SELECT * FROM Customers
WHERE Country = 'Brazil'
AND City = 'Rio de Janeiro'
AND CustomerID > 50;
Combining AND and OR
You can combine the AND and OR operators.

The following SQL statement selects all customers from Spain that starts with a "G" or an "R".

Make sure you use parenthesis to get the correct result.

### Example :
Select all Spanish customers that starts with either "G" or "R":

SELECT * FROM Customers
WHERE Country = 'Spain' AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
Without parenthesis, the select statement will return all customers from Spain that starts with a "G", plus all customers that starts with an "R", regardless of the country value:

### Example :
Select all customers that either:
are from Spain and starts with either "G", or
starts with the letter "R":

SELECT * FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%' OR CustomerName LIKE 'R%';

## SQL OR Operator
The SQL OR Operator
The WHERE clause can contain one or more OR operators.

The OR operator is used to filter records based on more than one condition, like if you want to return all customers from Germany but also those from Spain:

ExampleGet your own SQL Server
Select all customers from Germany or Spain:

SELECT *
FROM Customers
WHERE Country = 'Germany' OR Country = 'Spain';
Syntax
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;

## OR vs AND
The OR operator displays a record if any of the conditions are TRUE.

The AND operator displays a record if all the conditions are TRUE.

At Least One Condition Must Be True
The following SQL statement selects all fields from Customers where either City is "Berlin", CustomerName starts with the letter "G" or Country is "Norway":

### Example :
SELECT * FROM Customers
WHERE City = 'Berlin' OR CustomerName LIKE 'G%' OR Country = 'Norway';
Combining AND and OR
You can combine the AND and OR operators.

The following SQL statement selects all customers from Spain that starts with a "G" or an "R".

Make sure you use parenthesis to get the correct result.

### Example :
Select all Spanish customers that starts with either "G" or "R":

SELECT * FROM Customers
WHERE Country = 'Spain' AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
Without parenthesis, the select statement will return all customers from Spain that starts with a "G", plus all customers that starts with an "R", regardless of the country value:

### Example :
Select all customers that either:
are from Spain and starts with either "G", or
starts with the letter "R":

SELECT * FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%' OR CustomerName LIKE 'R%';

SQL NOT Operator
The NOT Operator
The NOT operator is used in combination with other operators to give the opposite result, also called the negative result.

In the select statement below we want to return all customers that are NOT from Spain:

ExampleGet your own SQL Server
Select only the customers that are NOT from Spain:

SELECT * FROM Customers
WHERE NOT Country = 'Spain';
In the example above, the NOT operator is used in combination with the = operator, but it can be used in combination with other comparison and/or logical operators. See examples below.

### Syntax :
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;

## NOT LIKE
Example
Select customers that does not start with the letter 'A':

SELECT * FROM Customers
WHERE CustomerName NOT LIKE 'A%';
NOT BETWEEN
Example
Select customers with a customerID not between 10 and 60:

SELECT * FROM Customers
WHERE CustomerID NOT BETWEEN 10 AND 60;
NOT IN
Example
Select customers that are not from Paris or London:

SELECT * FROM Customers
WHERE City NOT IN ('Paris', 'London');
NOT Greater Than
Example
Select customers with a CustomerId not greater than 50:

SELECT * FROM Customers
WHERE NOT CustomerID > 50;
NOT Less Than
Example
Select customers with a CustomerID not less than 50:

SELECT * FROM Customers
WHERE NOT CustomerId < 50;