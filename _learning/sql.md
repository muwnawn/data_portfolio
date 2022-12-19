---
title: "A note about SQL (Structured Query Language)"
date: 2022-12-20
last_modified_at: 2022-12-20T11:59:26-04:00
author_profile: true
header:
  image: "/images/DA_img_5.png"
  teaser: "/images/DA_img_5.png"
toc: true
<!-- toc_sticky: true -->
---

## 1. FUNDAMENTAL
### 1.1. SQL Definition 
- Aim: store, manipulate, and query data stored in relational databases.
- RDBMS (Relational Database Management Systems): a database that uses a relational model to create groups of data put into tables. Common RDBMS:Oracle, MS SQL Server, and My SQL.
- Data Types: 
  - String: VARCHAR(size),...
  - Date/Time: TIMESTAMP,...
  - Number: INT(size),...
  - Boolean: BOOL,...

### 1.2. SQL Components
#### SQL Statement
- Clauses are in-built functions helping us filter and analyze data quickly.
- SQL Clauses examples: SELECT, INSERT, DELETE,...
#### SQL Clauses
- Clauses are in-built functions helping us filter and analyze data quickly.
- SQL Clauses examples: WHERE, AND, TOP,...
#### [SQL Operator](https://www.w3schools.com/sql/sql_operators.asp)
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
- SQL Functions examples: MAX, SUM, COUNT,...

## 2. ADVANCED
### 2.1. Window/Analytic functions
- What: A window function performs a calculation across a set of table rows that are somehow related to the current row
- How: using OVER() with 
  - Aggregate functions: SUM, AVG, COUNT
  - Ranking functions: RANK, DENSE_RANK (2 identical records are given the same rank), ROW_NUMBER (2 identical records are given the different number)
  - Before- and after-functions: LEAD, LAG
  - Grouping functions: NTILE
- Sample:
```sql
SELECT start_terminal,
       duration_seconds,
       NTILE(4) OVER
         (PARTITION BY start_terminal ORDER BY duration_seconds)
          AS quartile,
       NTILE(5) OVER
         (PARTITION BY start_terminal ORDER BY duration_seconds)
         AS quintile,
       NTILE(100) OVER
         (PARTITION BY start_terminal ORDER BY duration_seconds)
         AS percentile
  FROM tutorial.dc_bikeshare_q1_2012
 WHERE start_time < '2012-01-08'
 ORDER BY start_terminal, duration_seconds
```

### 2.2. Common Table Expressions (CTEs)
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

### 2.3. Subqueries
- What: A subquery (inner queries or nested queries) is a SQL statement that has another SQL query embedded.
- How: Subqueries can be used in several places within a query
  - FROM statement
  - WHERE/HAVING clause
  - JOIN
- Sample:
```sql
SELECT SUM (Sales) FROM Store_Information
WHERE Store_Name IN
  (SELECT Store_Name FROM Geography
  WHERE Region_Name = 'West');
```

### 2.4. [Pivoting Data](https://mode.com/sql-tutorial/sql-pivot-table/)
#### Pivoting rows to columns
#### Pivoting columns to rows
- Using [CROSS JOIN](https://www.sqlshack.com/sql-cross-join-with-examples/)

### 2.5. SQL Stored Procedures
- What: A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.
- Stored Procedure Syntax and Execute
```sql
-- Syntax
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
AS
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
GO;
-- Execute
EXEC SelectAllCustomers @City = 'London', @PostalCode = 'WA1 1DP';
```

<!-- ### 2.7. Transact-SQL (T-SQL)
#### Definition
- A set of programming extensions from Sybase and Microsoft that add several features to SQL, including transaction control, exception and error handling, row processing and declared variables. Transact-SQL is central to using Microsoft SQL Server.
- Three languages
  - Data Definition Language (DDL): creates, modifies, and deletes database objects such as table, view, and index, and to manage access privileges to these objects. Examples: CREATE TABLE, DROP TABLE,...
  - The Data Manipulation Language (DML): performs database maintenance. Using this powerful tool, you can specify what you want to do with the data in your database — enter it, change it, or extract it. Examples: INSERT, UPDATE, DELETE, SELECT,...
  - The Data Control Language (DCL): protects your database from becoming corrupted. Examples: COMMIT, ROLLBACK, GRANT, and REVOKE.
#### Structure -->

<!-- a cursor, a transaction, data modeling concepts SQL -->

## 3. EFFICIENT QUERIES (run faster and use less data)
Try adding EXPLAIN at the beginning of query to get a sense of how long it will take. The output, Query Plan, shows the order in which your query will be executed. It's not perfectly accurate, but it's a useful tool. Example:
```sql
EXPLAIN
SELECT *
  FROM benn.sample_event_table
 WHERE event_date >= '2014-03-01'
   AND event_date < '2014-04-01'
 LIMIT 100
 ```
### 3.1. Reducing table size
  - Read less data by minimizing number of using rows and columns.
  - Only select the desired columns, avoid using SELECT * FROM.
  - Filtering the data to include only the needed records with WHERE, LIMIT clause.
  
### 3.2. Making joins less complicated
  - Avoid N:N JOINs.
  - Reduce table sizes before joining with subqueries.
  
### 3.3. Aggregations
#### JOINs: Combine horizontally multiple tables.
#### UNIONs: Combine vertically multiple tables.
  - UNION does not return duplicate records (similar to SELECT DISTINCT)
  - UNION & UNION ALL: The only difference is UNION returns distinct records, while UNION ALL returns all records.
  - Like UNION, these queries below also return unique values
    - UNION: returns records from table A OR table B
    - INTERSECT: returns records from table A AND table B
    - MINUS: returns records from table A, not from table B
    
### 3.4. Optimized a query using indexes
- Indexing makes columns faster to query by creating pointers to where data is stored within a database.
- Why? Indexes use an optimal search method known as **binary search**. Binary searches work by constantly cutting the data in half and checking if the entry you are searching for comes before or after the entry in the middle of the current portion of data.
- When not to use? When data is written to the database, the original table (the clustered index) is updated first and then all of the indexes off of that table are updated. If the database is constantly receiving writes then the indexes will never be usable. This is why indexes are typically applied to databases in data warehouses that get new data updated on a scheduled basis(off-peak hours) and not production databases which might be receiving new writes all the time.

#### Clustered Indexes
- Clustered indexes are the unique index per table that uses the primary key to organize the data that is within the table.
- Creating Clustered Indexes: The clustered index will be automatically created when the primary key is defined. 
- Clustered indexes use the primary key sorted in ascending order.
#### Non-Clustered Indexes
- Non-clustered indexes are sorted references for a specific field, from the main table, that hold pointers back to the original entries of the table.
- Creating Non-Clustered Indexes: CREATE INDEX
```sql
CREATE INDEX friends_name_asc ON friends(name ASC);
```
- Testing Index performance: EXPLAIN ANALYZE. The output will tell which method of search from the query plan was chosen and how long the planning and execution of the query took.
```sql
EXPLAIN ANALYZE SELECT * FROM friends WHERE name = 'Blake';
```
- Only create one index at a time because not all indexes will decrease query time.
  - Adding an index will always mean storing more data.
  - Adding an index will increase how long it takes your database to fully update after a write operation.
<!-- - AUTO_INCREMENT  -->

### 3.5. Uncontrollable factors related to the database itself
  - Other users running queries: The more queries running on a database, the more the database must process at a given time and the slower everything will run. It can be especially bad if others are running particularly resource-intensive queries.
  - Database software and optimization.

## NOTES
### GROUP BY extensions 
- ROLLUP
- CUBE
- GROUPING SETS

## Source
1. [https://www.1keydata.com/sql/advanced.html](https://www.1keydata.com/sql/advanced.html)
2. [https://www.kaggle.com/learn/advanced-sql](https://www.kaggle.com/learn/advanced-sql)
3. [https://mode.com/sql-tutorial/](https://mode.com/sql-tutorial/)
<!-- 4. SQL For Dummies, 8th Edition -->

