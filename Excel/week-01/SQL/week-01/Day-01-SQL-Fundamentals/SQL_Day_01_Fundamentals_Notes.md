# SQL Day 01 – Fundamentals

## What is SQL?

SQL (Structured Query Language) is used to communicate with and analyze data stored in relational databases.

As a Data Analyst, SQL is mainly used to:

- Retrieve data
- Filter data
- Sort data
- Remove duplicate values
- Select required columns
- Analyze business data

---

## Database

A database is a structured collection of data.

A database can contain multiple tables.

Example:

```text
Database
│
├── customers
├── orders
├── products
└── employees
Table
A table stores data in rows and columns.
Example:
customer_id	customer_name	city
C01	Ravi	Hyderabad
C02	Sita	Vijayawada
C03	Arun	Bangalore


- Column → Attribute / Field
- Row → Record
1. SELECT
SELECT is used to retrieve data from a table.
Syntax
SELECT column_name
FROM table_name;
Example
SELECT customer_name
FROM customers;
This returns only the customer names.
Selecting Multiple Columns
SELECT customer_name, city
FROM customers;
Selecting All Columns
SELECT *
FROM customers;
* means all columns.
2. FROM
FROM specifies the table from which the data should be retrieved.
SELECT *
FROM orders;
Here:
- SELECT → What data do we need?
- FROM → Where is the data?
3. WHERE
WHERE is used to filter rows based on a condition.
Example
SELECT *
FROM customers
WHERE city = 'Hyderabad';
This returns customers from Hyderabad.
Numeric Example
SELECT *
FROM employees
WHERE salary > 50000;
This returns employees whose salary is greater than 50,000.
4. ORDER BY
ORDER BY is used to sort the result.
Ascending Order
SELECT *
FROM employees
ORDER BY salary ASC;
Descending Order
SELECT *
FROM employees
ORDER BY salary DESC;
ASC → Lowest to highest
DESC → Highest to lowest
5. LIMIT
LIMIT restricts the number of rows returned.
Example
SELECT *
FROM employees
LIMIT 5;
This returns only the first 5 rows.
Top 5 Highest Salaries
SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;
6. DISTINCT
DISTINCT is used to remove duplicate values from the result.
Example
SELECT DISTINCT city
FROM customers;
This returns each city only once.
7. AS – Alias
AS is used to give a temporary name to a column or table.
Column Alias
SELECT salary AS employee_salary
FROM employees;
Calculation with Alias
SELECT quantity * unit_price AS total_sales
FROM orders;
Alias makes the output easier to understand.
SQL Query Thinking
When an interviewer asks:
"Which columns do you need?"
Think:
SELECT
"From which table?"
Think:
FROM
"Only customers from Hyderabad?"
Think:
WHERE
"Highest salary first?"
Think:
ORDER BY ... DESC
"Only top 5?"
Think:
LIMIT 5
"Unique cities?"
Think:
DISTINCT
Basic SQL Query Structure
SELECT column_name
FROM table_name
WHERE condition
ORDER BY column_name DESC
LIMIT 5;
The basic thinking is:
WHAT do I need?
        ↓
SELECT

WHERE is the data?
        ↓
FROM

WHICH rows?
        ↓
WHERE

HOW should it be arranged?
        ↓
ORDER BY

HOW MANY rows?
        ↓
LIMIT
Data Analyst Perspective
SQL is not just about writing syntax.
A Data Analyst should first understand:
1. What is the business question?
2. Which table contains the required data?
3. Which columns are needed?
4. What filter is required?
5. Does the result need sorting?
6. Does the result need to be limited?
Then write the SQL query.
Day 01 Summary
SQL Concept	Purpose
SELECT	Select required columns
FROM	Select the table
WHERE	Filter rows
ORDER BY	Sort results
LIMIT	Limit number of rows
DISTINCT	Remove duplicates
AS	Rename output column


Status
SQL Day 01 – Fundamentals Completed ✅
