# Day 01 - SQL Fundamentals

## 🎯 Goal
Learn the basic SQL commands used by Data Analysts to retrieve, filter, sort, and inspect data.

---

## 1. SELECT

Used to retrieve specific columns from a table.

Syntax:
SELECT column1, column2
FROM table_name;

Example:
SELECT name, salary
FROM employees;

---

## 2. SELECT *

Used to retrieve all columns.

SELECT *
FROM employees;

---

## 3. DISTINCT

Used to return unique values and remove duplicate results.

SELECT DISTINCT department
FROM employees;

---

## 4. WHERE

Used to filter rows based on a condition.

SELECT *
FROM employees
WHERE salary > 50000;

Common Operators:

=   Equal
>   Greater than
<   Less than
>=  Greater than or equal
<=  Less than or equal
<>  Not equal

---

## 5. AND

Both conditions must be TRUE.

SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 50000;

---

## 6. OR

At least one condition must be TRUE.

SELECT *
FROM employees
WHERE department = 'IT'
OR department = 'Sales';

---

## 7. NOT

Used to exclude a condition.

SELECT *
FROM employees
WHERE NOT department = 'HR';

---

## 8. IN

Used to filter multiple possible values.

SELECT *
FROM employees
WHERE department IN ('IT', 'Sales', 'HR');

IN is useful instead of:

WHERE department = 'IT'
OR department = 'Sales'
OR department = 'HR';

---

## 9. BETWEEN

Used to filter values within a range.

SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 80000;

Important:
BETWEEN includes both boundary values.

---

## 10. LIKE

Used for pattern matching.

Starts with A:

SELECT *
FROM employees
WHERE name LIKE 'A%';

Ends with A:

SELECT *
FROM employees
WHERE name LIKE '%A';

Contains A:

SELECT *
FROM employees
WHERE name LIKE '%A%';

Wildcards:

% = Any number of characters
_ = Exactly one character

---

## 11. IS NULL

Used to find missing values.

SELECT *
FROM employees
WHERE salary IS NULL;

Important:

Do NOT use:
salary = NULL

Use:
salary IS NULL

---

## 12. IS NOT NULL

Used to find values that are not missing.

SELECT *
FROM employees
WHERE salary IS NOT NULL;

---

## 13. ORDER BY

Used to sort results.

Ascending:

SELECT *
FROM employees
ORDER BY salary ASC;

Low → High

Descending:

SELECT *
FROM employees
ORDER BY salary DESC;

High → Low

ASC = Ascending
DESC = Descending

---

## 14. LIMIT

Used to restrict the number of rows returned.

SELECT *
FROM employees
LIMIT 5;

---

# 🔥 Combining SQL Commands

Business Question:
Find the top 5 highest-paid employees in IT.

SQL:

SELECT name, salary
FROM employees
WHERE department = 'IT'
ORDER BY salary DESC
LIMIT 5;

Thinking:

WHAT?
Employee name + salary

GIVEN?
Employees table

NEED?
Only IT employees

HOW?
WHERE → ORDER BY → LIMIT

---

# 📌 Basic SQL Query Execution Order

FROM
↓
WHERE
↓
SELECT
↓
ORDER BY
↓
LIMIT

---

# 🧠 Data Analyst Query Patterns

Get specific columns:

SELECT column1, column2
FROM table;

Filter rows:

SELECT *
FROM table
WHERE condition;

Filter multiple conditions:

SELECT *
FROM table
WHERE condition1
AND condition2;

Multiple values:

SELECT *
FROM table
WHERE column IN ('A', 'B', 'C');

Range:

SELECT *
FROM table
WHERE column BETWEEN value1 AND value2;

Pattern:

SELECT *
FROM table
WHERE column LIKE 'A%';

Missing values:

SELECT *
FROM table
WHERE column IS NULL;

Sort:

SELECT *
FROM table
ORDER BY column DESC;

Top records:

SELECT *
FROM table
ORDER BY column DESC
LIMIT 5;

---

# 💼 Real-World Data Analyst Examples

## Example 1: High-value customers

Find customers whose total amount is greater than 10,000.

SELECT customer_id, total_amount
FROM customers
WHERE total_amount > 10000;

---

## Example 2: Hyderabad customers

SELECT customer_id, customer_name
FROM customers
WHERE city = 'Hyderabad';

---

## Example 3: Customers from selected cities

SELECT customer_id, customer_name, city
FROM customers
WHERE city IN ('Hyderabad', 'Bangalore', 'Chennai');

---

## Example 4: Orders between two amounts

SELECT order_id, amount
FROM orders
WHERE amount BETWEEN 1000 AND 5000;

---

## Example 5: Find missing email addresses

SELECT customer_id, customer_name
FROM customers
WHERE email IS NULL;

---

## Example 6: Find highest orders

SELECT order_id, amount
FROM orders
ORDER BY amount DESC
LIMIT 10;

---

# ⚡ Quick Revision

SELECT       → Choose columns
SELECT *     → Select all columns
DISTINCT     → Get unique values
WHERE        → Filter rows
AND          → Both conditions
OR           → Either condition
NOT          → Exclude condition
IN           → Multiple values
BETWEEN      → Range
LIKE         → Pattern matching
IS NULL      → Find missing values
IS NOT NULL  → Find non-missing values
ORDER BY     → Sort data
LIMIT        → Limit rows

---

# 🎯 Interview Questions

Q1. What is SELECT?

SELECT is used to retrieve data from one or more columns of a table.

Q2. What is WHERE?

WHERE filters rows based on a specified condition.

Q3. What is DISTINCT?

DISTINCT returns unique values and removes duplicate results.

Q4. Difference between IN and BETWEEN?

IN checks multiple specific values.
BETWEEN checks a range of values.

Q5. How do you find NULL values?

SELECT *
FROM employees
WHERE salary IS NULL;

Q6. How do you find the top 5 salaries?

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;

Q7. How do you find unique departments?

SELECT DISTINCT department
FROM employees;

---

# 📝 Practice Questions

1. Display all employees.
2. Display only employee names and salaries.
3. Find employees with salary greater than 50,000.
4. Find employees from the IT department.
5. Find employees from IT or Sales.
6. Find employees with salary between 40,000 and 80,000.
7. Find employees whose names start with A.
8. Find unique departments.
9. Find employees with missing salary.
10. Find employees whose salary is not missing.
11. Find the top 5 highest-paid employees.
12. Find employees who are not from HR.
13. Find employees from IT, HR, or Sales.
14. Find employees whose names contain "an".
15. Find the top 10 highest-paid employees from IT.

---

# 🧠 QTHINK Method

For every SQL question, think:

WHAT?
What information is required?

GIVEN?
Which table and columns are available?

NEED?
What filter or condition is required?

HOW?
Which SQL concepts are required?

Example:

Question:
Find the top 5 highest-paid IT employees.

WHAT?
Name + Salary

GIVEN?
Employees table

NEED?
IT employees

HOW?
WHERE + ORDER BY DESC + LIMIT

SQL:

SELECT name, salary
FROM employees
WHERE department = 'IT'
ORDER BY salary DESC
LIMIT 5;

---

# ✅ Day 01 Topics

✓ SELECT
✓ SELECT *
✓ DISTINCT
✓ WHERE
✓ AND
✓ OR
✓ NOT
✓ IN
✓ BETWEEN
✓ LIKE
✓ IS NULL
✓ IS NOT NULL
✓ ORDER BY
✓ LIMIT
✓ Basic SQL query combinations
✓ Data Analyst thinking

---

# 🚀 Next Day

Day 02 - SQL Filtering & Conditions
