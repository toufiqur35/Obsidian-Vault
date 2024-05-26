SQL is the standard language for dealing with Relational Databases.
SQL is used to insert, search, update, and delete database records.
#### Some of The Most Important SQL Commands
- `SELECT` - extracts data from a database
- `UPDATE` - updates data in a database
- `DELETE` - deletes data from a database
- `INSERT INTO` - inserts new data into a database
- `CREATE DATABASE` - creates a new database
- `ALTER DATABASE` - modifies a database
- `CREATE TABLE` - creates a new table
- `ALTER TABLE` - modifies a table
- `DROP TABLE` - deletes a table
- `CREATE INDEX` - creates an index (search key)
- `DROP INDEX` - deletes an index

#### SELECT Statement
* The `SELECT` statement is used to select data from a database.
```mysql
SELECT * FROM  _table_name_;
```

#### WHERE Clause
* The `WHERE` clause is used to filter records.
* It is used to extract only those records that fulfill a specified condition.
```mysql
SELECT * FROM Customers WHERE Country = 'Dhaka';
```

####  AND, OR and NOT Operators

The `WHERE` clause can be combined with `AND`, `OR`, and `NOT` operators.
The `AND` and `OR` operators are used to filter records based on more than one condition:
 - The `AND` operator displays a record if all the conditions separated by `AND` are TRUE.
 - The `OR` operator displays a record if any of the conditions separated by `OR` is TRUE.
 - The `NOT` operator displays a record if the condition(s) is NOT TRUE.
#### AND Syntax
```mysql
SELECT * FROM Customers  
WHERE Country = 'Germany' AND City = 'Berlin';
```
#### OR Syntax
```mysql
SELECT * FROM Customers  
WHERE City = 'Berlin' OR City = 'Stuttgart';
```
#### NOT Syntax
```mysql
SELECT * FROM Customers  
WHERE NOT Country = 'Germany';
```

####  ORDER BY Keyword
* The `ORDER BY` keyword is used to sort the result-set in ascending or descending order.
* The `ORDER BY` keyword sorts the records in ascending order by default. To sort the records in descending order, use the `DESC` keyword.

```mysql
SELECT * FROM Customers  
ORDER BY Country; //deafult ascending

//examole2
SELECT * FROM Customers  
ORDER BY Country DESC;
```

####  INSERT INTO
* The `INSERT INTO` statement is used to insert new records in a table.

```mysql
INSERT INTO _table_name_ (_column1_, _column2_, _column3_, ...)  
VALUES (_value1_, _value2_, _value3_, ...);

'////If you are adding values for all the columns of the table'
INSERT INTO _table_name_  
VALUES (_value1_, _value2_, _value3_, ...); 
```

####  NULL Value
* A field with a NULL value is a field with no value.

```mysql
SELECT _column_names _FROM _table_name_  
WHERE _column_name_ IS NULL;

//example2
SELECT _column_names _FROM _table_name_  
WHERE _column_name_ IS NOT NULL;
```

#### Update Statement
* The `UPDATE` statement is used to modify the existing records in a table.

```mysql
UPDATE Customers  
SET ContactName = 'Alfred Schmidt', City = 'Frankfurt'  
WHERE CustomerID = 1;
```
#### DELETE Statement
* The `DELETE` statement is used to delete existing records in a table.

```mysql
DELETE FROM _table_name_ WHERE _condition_;
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
```
####  LIMIT Clause
* The `LIMIT` clause is used to specify the number of records to return.
* The `LIMIT` clause is useful on large tables with thousands of records. Returning a large number of records can impact performance.

```mysql
SELECT _column_name(s)_  
FROM _table_name  
_WHERE _condition_  
LIMIT _number_;

//example

```