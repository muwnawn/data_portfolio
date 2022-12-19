---
title: "A note about SQL (Structured Query Language)"
date: 2022-12-20
last_modified_at: 2022-12-20T11:59:26-04:00
author_profile: true
header:
  image: "/images/DA_img_5.png"
  teaser: "/images/DA_img_5.png"
---
## FUNDAMENTAL
### SQL Definition 
- Aim: store, manipulate, and query data stored in relational databases.
- RDBMS (Relational Database Management Systems): a database that uses a relational model to create groups of data put into tables. Common RDBMS:Oracle, MS SQL Server, and My SQL.
- Data Types: 
  - String: VARCHAR(size),...
  - Date/Time: TIMESTAMP,...
  - Number: INT(size),...
  - Boolean: BOOL,...

### SQL Components
#### Three languages
- Data Definition Language (DDL): creates, modifies, and deletes database objects such as table, view, and index, and to manage access privileges to these objects. Examples: CREATE TABLE, DROP TABLE,...
- The Data Manipulation Language (DML): performs database maintenance. Using this powerful tool, you can specify what you want to do with the data in your database — enter it, change it, or extract it. Examples: INSERT, UPDATE, DELETE, SELECT,...
- The Data Control Language (DCL): protects your database from becoming corrupted. Examples: COMMIT, ROLLBACK, GRANT, and REVOKE.

#### SQL Statement
- Clauses are in-built functions helping us filter and analyze data quickly.
- SQL Clauses examples: SELECT, INSERT, DELETE,...
#### SQL Clauses
- Clauses are in-built functions helping us filter and analyze data quickly.
- SQL Clauses examples: WHERE, AND, TOP,...
#### [SQL Operator]([url](https://www.w3schools.com/sql/sql_operators.asp)
- A reserved word or a character used primarily in an SQL statement's WHERE clause to perform operation(s).
- SQL Clauses examples: =, +, IN, IS NULL,...
#### SQL Constraint
- Limit the type of data when the table is first created via the CREATE TABLE statement, or after the table is already created via the ALTER TABLE statement.
- SQL Constraint examples: NOT NULL, UNIQUE, PRIMARY KEY,...
#### SQL Keyword
- the reserved set of words in any programming language that are used to perform various operations.
- SQL Clauses examples: CREATE, DROP, DISTINCT,...
#### SQL Functions
- Built-in functions for performing calculations on data
- SQL Functions examples:
  - Aggregate functions: SUM, AVG, COUNT
  - Scalar functions: LEN, ROUND, UCASE
  - Ranking functions: RANK, DENSE_RANK, ROW_NUMBER
  - Before- and after-functions: LEAD, LAG
  - Window functions: OVER()
  - ...

## ADVANCED
### Window functions

### Common Table Expressions (CTEs)
- What: a temporary result you can use in the SELECT statement. It works like a temporary table – you can join it with other tables, other CTEs, or with itself.
- Why: CTEs will allow to write complex queries without using subqueries keeping your code simple and straightforward.
- How: Every CTE opens with the WITH clause >> must name CTE >> write a SELECT statement >> the written CTE can be used in the next SELECT statement.
- Sample:
```sql
WITH time_worked AS (
    SELECT  employee_id,
            end_time - start_time AS time
FROM project_timesheet
)
SELECT  e.first_name,
        e.last_name,
        AVG (tw.time) AS avg_time_worked
FROM employee e
LEFT JOIN time_worked tw
ON e.id = tw.employee_id
GROUP BY e.first_name, e.last_name;
```
### Subqueries
- What: A subquery is a SQL statement that has another SQL query embedded.
- Sample:
```sql
SELECT SUM (Sales) FROM Store_Information
WHERE Store_Name IN
(SELECT Store_Name FROM Geography
WHERE Region_Name = 'West');
```

## NOTES
### JOINs and UNIONs: Combine information from multiple tables.
#### JOINs: horizontally combine

#### UNION: vertically combine
- UNION does not return duplicate records (similar to SELECT DISTINCT)
- UNION & UNION ALL: The only difference is UNION returns distinct records, while UNION ALL returns all records.
- Like UNION, these queries below also return unique values
  - UNION: returns records from table A OR table B
  - INTERSECT: returns records from table A AND table B
  - MINUS: returns records from table A, not from table B
  
### GROUP BY extensions 
- ROLLUP
- CUBE
- GROUPING SETS


## EFFICIENT QUERIES 
- Strategies (run faster and use less data)
  1) Only select the columns you want, avoid using SELECT * FROM.
  2) Read less data.
  3) Avoid N:N JOINs.

## Source
1. [https://www.1keydata.com/sql/advanced.html](https://www.1keydata.com/sql/advanced.html)
2. [https://www.kaggle.com/learn/advanced-sql](https://www.kaggle.com/learn/advanced-sql)
3. [https://mode.com/sql-tutorial/](https://mode.com/sql-tutorial/)
4. SQL For Dummies, 8th Edition

