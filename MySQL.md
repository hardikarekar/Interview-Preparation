## What is a database?
* A database is a collection of data in a format that can be easily accessed (Digital).
* A software application used to manage our DB is called DBMS (Database Management System).
* user (SQL)--> DBMS --> DB
## Types of Databases
* 1. Relational
	* Data stored in tables.
		* MySQL, MSSQL, PostgreSQL, Oracle
	* We use SQL to work with relational DBMS.
* 2. Non Relational (NoSQL)
	* Data not stored in tables 
		* mongodb
* What is SQL?
	* Structured Query Language
	* SQL is a programming language used to interact with relational databases.
	* It is used to perform CRUD (Create, Read, Update, Delete) operations.
## What is a table?
* Is a structure used to store data in the form of rows and columns.

| Emplyee_ID | Name   | Department | Salary |
| ---------- | ------ | ---------- | ------ |
| 1          | Hardik | IT         | 45000  |
| 2          | Raj    | IT         | 45000  |
* Columns -> structure / schema (design)
* Rows -> Individual data
## Creating Database
```sql
CREATE DATABASE college;

DROP DATABASE college;                  # delete database
```
## Create table
```sql
use college;                    ## use database

CREATE TABLE table_name(
	column_name1 datatype constraint,
	column_name2 datatype constraint,
	column_name3 datatype constraint
);
```
For eg: 
```sql
CREATE TABLE student(
	id INT PRIMARY KEY,
	name VARCHAR(50),
	age INT NOT NULL
);
```
## SQL Datatypes
* They define the type of values that can be stored in a column.

| DATATYPE | DESCRIPTION                                                          | USAGE       |
| -------- | -------------------------------------------------------------------- | ----------- |
| CHAR     | string(0-255), can store characters of fixed length                  | CHAR(50)    |
| VARCHAR  | string(0-255), can store characters up to given length               | VARCHAR(50) |
| BLOB     | string(0-65535), can store binary large object                       | BLOB(1000)  |
| INT      | integer(-2,147,483,648 to 2,147,483,647)                             | INT         |
| TINYINT  | integer(-128 to 127)                                                 | TINYINT     |
| BIGINT   | integer(-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807)     | BIGINT      |
| BIT      | can store x-bit values, x can range from 1 to 64                     | BIT(2)      |
| FLOAT    | Decimal number with precision to 23 digits                           | FLOAT       |
| DOUBLE   | Decimal number with 24 to 53 digits                                  | DOUBLE      |
| BOOLEAN  | Boolean values 0 or 1                                                | BOOLEAN     |
| DATE     | date in format of YYYY-MM-DD ranging from 1000-01-01 to   9999-12-31 | DATE        |
| YEAR     | year in 4 digits format ranging from 1901 to 2155                    | YEAR        |
* Signed and Unsigned
	* TINYINT UNSIGNED (0 to 255)
	* TINYINT (-128 to 127)
## Types of SQL Commands
* DDL (Data Definition Language)
	* create, alter, rename, truncate, drop
* DQL (Data Query Language)
	* select
* DML (Data Manipulation Language)
	* insert, update and delete
* DCL (Data Control Language)
	* grant and revoke permission to users
* TCL (Transaction Control Language)
	* start transaction, commit, rollback
## Database Related Queries
```sql
CREATE DATABASE db_name;
CREATE DATABASE IF NOT EXISTS college;

DROP DATABASE db_name;
DROP DATABASE IF EXISTS db_name;

SHOW DATABASES;

SHOW TABLES;
```
## Table Related Queries
* Create 
```sql
CREATE TABLE table_name(
	column_name1 datatype constraint,
	column_name2 datatype constraint
);

For eg:
CREATE TABLE student(
	rollno INT PRIMARY KEY,
	name VARCHAR(50)
);
```

* Select and View all columns
```sql
SELECT * FROM table_name;

SELECT * FROM student;
```

* Insert
```sql
INSERT INTO table_name
(colname1, colname2)
VALUES
(col1_v1, col2_v1),
(col1_v2, col2_v2);

For eg:
INSERT INTO student
(roll_no, name)
VALUES
(1, "Hardik"),
(2, "Raj");
```
## Practice Questions
1. Create a database for your company named XYZ.
	1. Create a table inside this DB to store employee info (id, name and salary)
	2. Add following information in the DB
		1. 1, "adam", 25000
		2. 2, "bob", 30000
		3. 3, "casey", 40000
	3. Select and view all your table data

## Keys
* Primary Key
	* It is a column (or a set of columns) in a table that uniquely identifies each row (a unique id).
	* There is only 1 PK and it should not be null.
* Foreign Key
	* A foreign key is a column (or set of columns) in a table that refers to the primary key of another table.
	* There can be multiple FKs.
	* FKs can have duplicate and null values.
## Constraints
* SQL constraints are used to specify rules for data in a table.
* `NOT NULL` columns cannot have a null value. 
	* `col1 INT NOT NULL`
* `UNIQUE` all values in column are different
	* `col2 INT UNIQUE`
* `PRIMARY KEY` makes a column unique and not null based but used only for one.
```sql
id INT PRIMARY KEY;

CREATE TABLE temp(
	id INT NOT NULL,
	PRIMARY KEY (id)
);
```
* `Foreign Key` prevent actions that would destroy link between tables.
```sql
CREATE TABLE temp(
	cust_id INT,
	FOREIGN KEY(cust_id) references customer(id)
);
```
* `DEFAULT` sets the default value of a column.
```sql
salary INT DEFAULT 25000
```
* `CHECK` it can limit the values allowed in a column.
```sql
CREATE TABLE temp(
	id INT PRIMARY KEY,
	city VARCHAR(50),
	age INT,
	CONSTRAINT age_check CHECK (age >= 18 AND city="Delhi")
);

CREATE TABLE temp(
	age INT CHECK (age >= 18)
);
```

* Create this sample database
```sql
CREATE DATABASE college;

USE college;

CREATE TABLE student(
	roll_no INT PRIMARY KEY,
    name VARCHAR(50),
    marks INT NOT NULL,
    grade VARCHAR(1),
    city VARCHAR(20)
);
```
* Insert this data
```sql
INSERT INTO student 
(roll_no, name, marks, grade, city)
VALUES 
(101, "Anil", 78, "C", "Pune"),
(102, "bhumika", 93, "A","Mumbai"),
(103, "chetan", 85, "B", "Mumbai"),
(104, "dhruv", 96, "A", "Delhi"),
(105, "emanuel", 12, "F", "Delhi"),
(106, "farah", 82, "B", "Delhi");
```

## Select command 
* used to select any data from the database.
* Basic syntax
	* `SELECT col1, col2 FROM table_name;`
* To select all
	* `SELECT * FROM table_name;`
* To select distinct values
	* `SELECT DISTINCT city from student;`
## WHERE clause
* To define some conditions
```sql
SELECT col1, col2 FROM table_name
WHERE conditions;
```
```sql
SELECT * from student WHERE marks > 80;
SELECT * from student WHERE city = "Mumbai";
```
* Using operators in WHERE
	* Arithmetic Operators: + (addition), - (subtraction), * (multiplication), / (division), % (modulus)
	* Comparison Operators: = (equal to), != (not equal to), >, >=, <, <=
	* Logical Operators: AND, OR, NOT, IN, BETWEEN, ALL, LIKE, ANY
	* Bitwise Operators: & (Bitwise AND), | (Bitwise OR)
## Operators
* AND (to check for both conditions to be true.
	* `SELECT * from student WHERE marks > 80 AND city = "Mumbai";`
* OR (to check for one of the conditions to be true)
	* `SELECT * from student WHERE marks > 90 OR city = "Mumbai";`
* BETWEEN (selects for a given range)
	* `SELECT * from student WHERE marks BETWEEN 80 and 90;`
* In (matches any value in the list)
	* `SELECT * from student WHERE city IN ("Delhi", "Mumbai");`
* NOT (to negotiate the given condition)
	* `SELECT * from student WHERE city NOT IN ("Delhi", "Mumbai");`
## LIMIT Clause
* Sets an upper limit on number of rows (tuples) to be returned.
	* `SELECT * FROM student LIMIT 3;`
```sql
SELECT col1, col2 FROM table_name
LIMIT number;
```
## ORDER BY Clause
* To sort in ascending (ASC) or descending order (DESC).
```sql
SELECT col1,col2 from table_name
ORDER BY col_name(s) ASC;
```
```sql
SELECT * from student
ORDER BY city ASC;
```
## Aggregate Functions
* Aggregate functions perform a calculation on a set of values, and return a single value.
* COUNT()
* MIN()
* MAX()
* SUM()
* AVG()
```sql
Get maximum marks
SELECT max(marks) FROM student;

Get average marks
SELECT avg(marks) FROM student;
```
## GROUP BY Clause
* Group rows that have the same values into summary rows.
* It collects data from multiple records and groups the result by one or more column.
* Generally we use GROUP BY with some aggregate function.
```sql
# Count number of students in each city
SELECT city, count(name) 
FROM student 
GROUP BY city;
```
## Practice Questions
* Write the query to find average marks in each city in ascending order.
```sql
select city, avg(marks) FROM student GROUP BY city ORDER BY city ASC;
```

* For the given table find the total payment according to each payment method.

| customer_id | customer          | mode        | city        |
| ----------- | ----------------- | ----------- | ----------- |
| 101         | Olivia Barrett    | Netbanking  | Portland    |
| 102         | Ethan Sinclair    | Credit Card | Miami       |
| 103         | Maya Hernandez    | Credit Card | Seattle     |
| 104         | Liam Donovan      | Netbanking  | Denver      |
| 105         | Sophia Nguyen     | Credit Card | New Orleans |
| 106         | Caleb Foster      | Debit Card  | Minneapolis |
| 107         | Ava Patel         | Debit Card  | Phoenix     |
| 108         | Lucas Carter      | Netbanking  | Boston      |
| 109         | Isabella Martinez | Netbanking  | Nashville   |
| 110         | Jackson Brooks    | Credit Card | Boston      |
```sql
SELECT mode, count(mode) FROM customer_info GROUP BY mode;
```
## HAVING Clause
* Similar to WHERE i.e. applies some conditions on rows.
* Used when we want to apply any condition after grouping.
* Count number of students in each city where max marks cross 90.
```sql
SELECT count(name), city 
FROM student 
GROUP BY city 
HAVING marks > 90;
```
## General Order Clauses
* SELECT column(s)
* FROM table_name
* WHERE condition
* GROUP BY column(s)
* HAVING condition
* ORDER BY column(s) ASC;
```sql
SELECT city 
FROM student 
WHERE grade = 'A'
GROUP BY city
HAVING max(marks) > 93
ORDER BY city ASC;
```
## UPDATE Command
* To update existing rows.
```sql
UPDATE table_name
SET col1=val1, col2=val2
WHERE condition;
```
```sql
UPDATE student 
SET grade = "O"
WHERE grade = "A";
```
* Turn off safe update mode (set safe update mode = 0) in MySQL
	* Execute this query: `SET SQL_SAFE_UPDATES;`

```sql
UPDATE student 
SET marks = 50
WHERE name = "emanuel";
```
## DELETE Command
* To delete existing rows 
```sql
DELETE FROM table_name
WHERE condition;
```
```sql
DELETE FROM student
WHERE marks < 33;
```
## Revisiting Foreign Keys

* Dept Table:

| id  | name    |
| --- | ------- |
| 101 | science |
| 102 | English |
| 103 | Hindi   |
* Teacher Table:

| id  | name   | dept_id (FK) |
| --- | ------ | ------------ |
| 101 | Adam   | 101          |
| 102 | Bob    | 103          |
| 103 | Casey  | 102          |
| 104 | Donald | 102          |

```sql
CREATE TABLE dept(
	id INT PRIMARY KEY,
    name VARCHAR(50)
);

CREATE TABLE teacher(
	id INT PRIMARY KEY,
    name VARCHAR(50),
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES dept(id)
);
```

## Cascading for Foreign Key
* On Delete Cascade
	* When we create a foreign key using this option, it deletes the referencing rows in the child table when the referenced row is deleted in the parent table which has a primary key.
* On Update Cascade
	* When we create a foreign key using UPDATE CASCADE the referencing rows are updated in the child table when the referenced row is updated in the parent table which has a primary key.
```sql
CREATE TABLE student(
	id INT PRIMARY KEY,
	courseID INT,
	FOREIGN KEY (courseID) REFERENCES course(id)
	ON DELETE CASCADE
	ON UPDATE CASCADE
);
```

## ALTER
* To change the schema. (column, datatype, constraints)
* Add Column
```sql
ALTER TABLE table_name
ADD COLUMN column_name datatype constraint;

## Example
ALTER TABLE student
ADD COLUMN age INT NOT NULL;
```

* Drop Column
```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```
* Rename Table
```sql
ALTER TABLE table_name
RENAME TO new_table_name;
```