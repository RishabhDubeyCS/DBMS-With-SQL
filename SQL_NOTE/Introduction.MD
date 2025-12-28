# What is a Database?

-- A database is a digital place where data is stored, organized, and managed so we can get it anytime easily.

-- 📱Example: Your mobile contact list → A database.

# SQL vs NoSQL

-- | Feature      | SQL                             | NoSQL                                                        |
-- | ------------ | ------------------------------- | ------------------------------------------------------------ |
-- | Meaning      | Structured Query Language       | Not Only SQL                                                 |
-- | Data Storage | **Tables (rows & columns)**     | **Flexible formats** like JSON, documents, key-value, graphs |
-- | Schema       | Fixed structure                 | No fixed structure                                           |
-- | Best For     | Complex queries & relationships | Large-scale, fast, unstructured data                         |
-- | Examples     | MySQL, PostgreSQL, Oracle       | MongoDB, Firebase, Cassandra                                 |

# What is SQL?

 SQL (Structured Query Language) is a language used to store, manage, and retrieve data from a database.
 n simple words:
 SQL helps us talk to the database and get the information we need.

  What is a Table?

 A table is a structure inside a database used to store data in rows and columns.

 Example: Contact list → Each contact = row, each detail (name, number) = column.

# Code:
CREATE DATABASE StudentDB;

USE StudentDB;

CREATE TABLE Students(
student_id int PRIMARY KEY ,
name VARCHAR (50) NOT NULL,
course VARCHAR (90) , 
age INT);

insert into Students ( student_id , name , course, age )Values
( 1 , "Rishabh" , "SQL ", 22),
( 2,  'Aman ' , 'React ', 23),
 (3, 'Kavya ' , 'Nodejs', 19 );
 
 SELECT * FROM Students;


 # Example: Create a Students Table

CREATE TABLE Students (  
  id INT PRIMARY KEY,
  name VARCHAR(50),
  course VARCHAR(50),
  age INT
);

# What is Constraint?
A constraint is a rule applied on a table’s data
to ensure correct, valid, and safe data is stored.

name VARCHAR(50) NOT NULL
-- NOT NULL constraint ensures that the 'name' column cannot have NULL values.

# What is Key Constraint?

-- A key constraint is a type of constraint used to identify or link records in a table.

Primary Key → Unique + Not Null

Foreign Key → Connects two tables

Unique Key → No duplicate values allowed

-- id INT PRIMARY KEY

 # Short Summary

-- Constraint = Data rules

-- Key Constraint = Rules for identifying & linking records

#  WHERE Clause
The WHERE clause is used to filter data —
It shows only those rows that match a condition.
-- SELECT * FROM Students WHERE age > 20;

# Operators in WHERE

Used to set conditions.

| Operator | Meaning               | Example                   |
| -------- | --------------------- | ------------------------- |
| =        | Equal                 | course = 'SQL'            |
| != or <> | Not equal             | age <> 21                 |
| >        | Greater than          | age > 20                  |
| <        | Less than             | age < 25                  |
| >=       | Greater or equal      | age >= 18                 |
| <=       | Less or equal         | age <= 22                 |
| AND      | Both conditions true  | age > 18 AND course='SQL' |
| OR       | Either condition true | age=21 OR age=22          |
| LIKE     | Pattern match         | name LIKE 'R%'            |
| BETWEEN  | Range                 | age BETWEEN 18 AND 25     |
| IN       | Multiple values       | course IN ('SQL','React') |

#  Quick Example Queries

SELECT * FROM Students WHERE course = 'SQL';

SELECT * FROM Students WHERE age > 20 AND course='React';

SELECT * FROM Students WHERE name LIKE 'R%';

# Summary

WHERE = Filter data

Operators = Create conditions

Used in almost every SELECT, UPDATE, DELETE query 🚀


# ORDER BY

Used to sort the result.

SELECT * FROM Students ORDER BY age ASC; -- Small to big
SELECT * FROM Students ORDER BY age DESC; -- Big to small

# LIMIT

Used to show limited number of rows.

SELECT * FROM Students LIMIT 2;


#  Aggregate Functions
Used to perform calculations on a column.

| Function | Meaning              |
| -------- | -------------------- |
| COUNT()  | Total number of rows |
| SUM()    | Add all values       |
| AVG()    | Average value        |
| MAX()    | Highest value        |
| MIN()    | Lowest value         |

SELECT COUNT(*) FROM Students;
SELECT MAX(age) FROM Students;
SELECT AVG(age) FROM Students;


# Super Short Summary

ORDER BY → Sort data

LIMIT → Restrict number of rows

Aggregate Functions → Math on data (count, sum etc.)


# GROUP BY

Used to group rows having the same values together.

Example: Count students in each course

SELECT course, COUNT(*) 
FROM Students 
GROUP BY course;


#  HAVING

Used to filter groups (just like WHERE filters rows).

# Example: Show only courses having more than 1 student

SELECT course, COUNT(*) 
FROM Students 
GROUP BY course 
HAVING COUNT(*) > 1;


# OR Operator (General)

Used when any one condition can be true.

SELECT * FROM Students 
WHERE age = 21 OR course = 'React';


# Short Summary

GROUP BY → Group similar data

HAVING → Filter groups

OR → Any one condition true

 UPDATE :- Used to modify existing data.


# DELETE :-
Used to delete specific rows.

DELETE FROM Students 
WHERE student_id = 2;

-- Table remains, only selected data removed.

# ALTER TABLE

-- Used to modify table structure (add/remove columns, change type).

ALTER TABLE Students ADD email VARCHAR(50);
ALTER TABLE Students DROP COLUMN age;


# TRUNCATE TABLE

Used to delete all rows from table very fast
(but structure remains)

TRUNCATE TABLE Students;


# Super Short Summary

| Command  | What it does                    |
| -------- | ------------------------------- |
| UPDATE   | Change data                     |
| DELETE   | Remove selected rows            |
| ALTER    | Change table structure          |
| TRUNCATE | Delete all rows, but keep table |




--  -------------------------------------------------PRIMARY KEY & FOREIGN----------------------------
