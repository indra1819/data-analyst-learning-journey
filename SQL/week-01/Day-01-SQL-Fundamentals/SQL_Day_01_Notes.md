# Day 1 — SQL Fundamentals

## Topics Covered

- What is SQL?
- Database & Table
- SELECT
- FROM
- WHERE
- DISTINCT
- ORDER BY
- LIMIT
- Column Aliases
- Comparison Operators
- Logical Operators
- IN
- BETWEEN
- LIKE
- IS NULL
- IS NOT NULL

---

## 1. What is SQL?

SQL = Structured Query Language

SQL is used to:

- Read data
- Filter data
- Sort data
- Analyze data
- Update data
- Work with databases

Example:

    SELECT *
    FROM employees;

---

## 2. Database & Table

### Database

A database is a collection of related tables.

### Table

A table stores data in:

- Rows → Records
- Columns → Fields

Example:

| employee_id | name | department | salary |
|---|---|---|---:|
| 101 | Rahul | IT | 50000 |
| 102 | Priya | HR | 45000 |
| 103 | Arun | IT | 60000 |

---

## 3. SELECT

Used to choose columns.

### Select all columns

    SELECT *
    FROM employees;

### Select specific columns

    SELECT name, salary
    FROM employees;

Remember:

    SELECT → What columns do I need?
    FROM   → From which table?

---

## 4. WHERE

Used to filter rows.

    SELECT *
    FROM employees
    WHERE department = 'IT';

### Salary greater than 50000

    SELECT *
    FROM employees
    WHERE salary > 50000;

---

## 5. DISTINCT

Used to remove duplicate values.

    SELECT DISTINCT department
    FROM employees;

Example result:

    IT
    HR
    Finance

---

## 6. ORDER BY

Used to sort data.

### Ascending

    SELECT *
    FROM employees
    ORDER BY salary ASC;

### Descending

    SELECT *
    FROM employees
    ORDER BY salary DESC;

Remember:

    ASC  → Small to Large
    DESC → Large to Small

---

## 7. LIMIT

Used to return a limited number of rows.

    SELECT *
    FROM employees
    LIMIT 5;

### Top 5 highest salaries

    SELECT *
    FROM employees
    ORDER BY salary DESC
    LIMIT 5;

---

## 8. Column Alias

Used to give a temporary name to a column.

    SELECT
        name AS employee_name,
        salary AS monthly_salary
    FROM employees;

AS → Rename column in the output.

---

## 9. Comparison Operators

| Operator | Meaning |
|---|---|
| = | Equal |
| <> | Not equal |
| != | Not equal |
| > | Greater than |
| < | Less than |
| >= | Greater than or equal |
| <= | Less than or equal |

Example:

    SELECT *
    FROM employees
    WHERE salary >= 50000;

---

## 10. AND

Both conditions must be true.

    SELECT *
    FROM employees
    WHERE department = 'IT'
    AND salary > 50000;

---

## 11. OR

At least one condition must be true.

    SELECT *
    FROM employees
    WHERE department = 'IT'
    OR department = 'HR';

---

## 12. NOT

Used to exclude a condition.

    SELECT *
    FROM employees
    WHERE NOT department = 'HR';

---

## 13. IN

Used to check multiple values.

Instead of:

    WHERE department = 'IT'
    OR department = 'HR'
    OR department = 'Finance'

Use:

    WHERE department IN ('IT', 'HR', 'Finance');

---

## 14. BETWEEN

Used to filter values within a range.

    SELECT *
    FROM employees
    WHERE salary BETWEEN 40000 AND 60000;

Important:

BETWEEN includes both values.

---

## 15. LIKE

Used for pattern matching.

### Starts with A

    SELECT *
    FROM employees
    WHERE name LIKE 'A%';

### Ends with n

    SELECT *
    FROM employees
    WHERE name LIKE '%n';

### Contains "ar"

    SELECT *
    FROM employees
    WHERE name LIKE '%ar%';

### Single character

    SELECT *
    FROM employees
    WHERE name LIKE 'A_';

Remember:

    % → Any number of characters
    _ → Exactly one character

---

## 16. IS NULL

Used to find missing values.

    SELECT *
    FROM employees
    WHERE department IS NULL;

---

## 17. IS NOT NULL

Used to find non-missing values.

    SELECT *
    FROM employees
    WHERE department IS NOT NULL;

Wrong:

    WHERE department = NULL

Correct:

    WHERE department IS NULL

---

# SQL Query Order

Remember this order:

    SELECT
    FROM
    WHERE
    ORDER BY
    LIMIT

Example:

    SELECT name, salary
    FROM employees
    WHERE salary > 50000
    ORDER BY salary DESC
    LIMIT 5;

---

# Real-World Data Analyst Examples

## Find all IT employees

    SELECT *
    FROM employees
    WHERE department = 'IT';

## Find employees earning more than 60000

    SELECT *
    FROM employees
    WHERE salary > 60000;

## Find top 10 salaries

    SELECT *
    FROM employees
    ORDER BY salary DESC
    LIMIT 10;

## Find unique departments

    SELECT DISTINCT department
    FROM employees;

## Find employees with salary between 40000 and 70000

    SELECT *
    FROM employees
    WHERE salary BETWEEN 40000 AND 70000;

## Find employees whose name starts with A

    SELECT *
    FROM employees
    WHERE name LIKE 'A%';

## Find employees whose department is either IT or HR

    SELECT *
    FROM employees
    WHERE department IN ('IT', 'HR');

## Find employees whose department is missing

    SELECT *
    FROM employees
    WHERE department IS NULL;

---

# Interview Quick Notes

    SELECT       → Choose columns
    FROM         → Choose table
    WHERE        → Filter rows
    DISTINCT     → Remove duplicates
    ORDER BY     → Sort results
    LIMIT        → Limit rows
    AS           → Rename column
    IN           → Match multiple values
    BETWEEN      → Filter a range
    LIKE         → Pattern matching
    IS NULL      → Find missing values
    IS NOT NULL  → Find available values
    AND          → Both conditions must be true
    OR           → At least one condition must be true
    NOT          → Exclude a condition

---

# Data Analyst Thinking

When you get a SQL question, think:

    1. What data do I need?
    2. Which table has the data?
    3. Do I need to filter rows?
    4. Do I need to sort?
    5. Do I need only a few rows?

Example:

Question: Find the top 5 highest-paid employees.

Thinking:

    What?   → Employee name and salary
    Table?  → employees
    Filter? → No
    Sort?   → Salary DESC
    Rows?   → Top 5

Query:

    SELECT name, salary
    FROM employees
    ORDER BY salary DESC
    LIMIT 5;

---

# Practice Questions

Use the employees table.

### Q1
Display all employees.

### Q2
Display only employee name and salary.

### Q3
Find employees from the IT department.

### Q4
Find employees earning more than 50000.

### Q5
Display unique departments.

### Q6
Find the 5 highest-paid employees.

### Q7
Find employees with salary between 40000 and 70000.

### Q8
Find employees whose name starts with A.

### Q9
Find employees whose department is either IT or HR.

### Q10
Find employees whose department is missing.

---

# Key Takeaways

    SELECT    → What do I need?
    FROM      → Where is the data?
    WHERE     → Which rows do I need?
    ORDER BY  → How should I sort?
    LIMIT     → How many rows do I need?

---

## Day 1 Goal

Understand basic SQL queries and confidently retrieve, filter, sort, and limit data.
