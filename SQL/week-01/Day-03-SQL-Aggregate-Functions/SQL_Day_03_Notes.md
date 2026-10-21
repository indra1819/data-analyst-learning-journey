# SQL Day 03 — Aggregate Functions

## 1. Day 3 Objective

Learn:

- Aggregate Functions
- COUNT()
- SUM()
- AVG()
- MIN()
- MAX()
- COUNT(*)
- COUNT(column)
- COUNT(DISTINCT column)
- Aggregate functions with WHERE
- GROUP BY
- HAVING
- Real Data Analyst business questions

Remember:

Aggregate Functions = Summarize Data

---

## 2. What are Aggregate Functions?

Aggregate functions perform calculations on multiple rows and return a single result.

Common aggregate functions:

COUNT() = Count rows
SUM()   = Total
AVG()   = Average
MIN()   = Minimum
MAX()   = Maximum

---

## 3. COUNT()

COUNT() counts records.

Example:

SELECT COUNT(*)
FROM employees;

Returns the total number of employees.

---

## 4. COUNT(*)

COUNT(*) counts all rows.

SELECT COUNT(*)
FROM employees;

Remember:

COUNT(*) = Total rows

---

## 5. COUNT(column)

COUNT(column) counts non-NULL values in that column.

SELECT COUNT(salary)
FROM employees;

Important:

NULL values are not counted.

---

## 6. COUNT(DISTINCT)

Used to count unique values.

Example:

SELECT COUNT(DISTINCT department)
FROM employees;

Meaning:

Count the number of unique departments.

Remember:

COUNT(DISTINCT column) = Number of unique values

---

## 7. SUM()

SUM() calculates the total.

Example:

SELECT SUM(salary)
FROM employees;

Meaning:

Total salary of all employees.

---

## 8. AVG()

AVG() calculates the average.

SELECT AVG(salary)
FROM employees;

Example:

If salaries are:

30000
40000
50000

Average:

40000

---

## 9. MIN()

MIN() returns the smallest value.

SELECT MIN(salary)
FROM employees;

---

## 10. MAX()

MAX() returns the largest value.

SELECT MAX(salary)
FROM employees;

---

## 11. Aggregate Functions Together

You can use multiple aggregate functions in one query.

SELECT
    COUNT(*) AS total_employees,
    SUM(salary) AS total_salary,
    AVG(salary) AS average_salary,
    MIN(salary) AS minimum_salary,
    MAX(salary) AS maximum_salary
FROM employees;

This gives a complete summary.

---

## 12. Column Aliases

Use AS to give a meaningful name to the result.

SELECT
    AVG(salary) AS average_salary
FROM employees;

Instead of:

avg(salary)

Result:

average_salary

Remember:

AS = Rename output

---

## 13. Aggregate Functions with WHERE

You can filter rows before aggregation.

Example:

SELECT AVG(salary)
FROM employees
WHERE department = 'IT';

Meaning:

Calculate average salary only for IT employees.

---

## 14. SUM with WHERE

SELECT SUM(salary)
FROM employees
WHERE department = 'Sales';

Meaning:

Total salary of Sales employees.

---

## 15. COUNT with WHERE

SELECT COUNT(*)
FROM employees
WHERE city = 'Hyderabad';

Meaning:

Count employees from Hyderabad.

---

## 16. MIN and MAX with WHERE

SELECT
    MIN(salary) AS minimum_salary,
    MAX(salary) AS maximum_salary
FROM employees
WHERE department = 'IT';

---

## 17. What is GROUP BY?

GROUP BY creates separate groups and calculates aggregate results for each group.

Example:

SELECT department, COUNT(*)
FROM employees
GROUP BY department;

Result:

IT       20
HR       10
Sales    15
Finance  8

Remember:

GROUP BY = Summary for each category

---

## 18. GROUP BY with SUM()

SELECT
    department,
    SUM(salary) AS total_salary
FROM employees
GROUP BY department;

Shows total salary for each department.

---

## 19. GROUP BY with AVG()

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department;

Shows average salary for each department.

---

## 20. GROUP BY with MIN()

SELECT
    department,
    MIN(salary) AS minimum_salary
FROM employees
GROUP BY department;

---

## 21. GROUP BY with MAX()

SELECT
    department,
    MAX(salary) AS maximum_salary
FROM employees
GROUP BY department;

---

## 22. Multiple Aggregates with GROUP BY

SELECT
    department,
    COUNT(*) AS employee_count,
    SUM(salary) AS total_salary,
    AVG(salary) AS average_salary,
    MIN(salary) AS minimum_salary,
    MAX(salary) AS maximum_salary
FROM employees
GROUP BY department;

This is very common in Data Analyst interviews.

---

## 23. GROUP BY Multiple Columns

You can group by more than one column.

Example:

SELECT
    department,
    city,
    COUNT(*) AS employee_count
FROM employees
GROUP BY department, city;

Meaning:

Count employees for each department and city combination.

---

## 24. WHERE vs GROUP BY

WHERE filters rows before grouping.

GROUP BY creates groups.

Example:

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
WHERE salary > 30000
GROUP BY department;

Thinking:

1. Remove salaries <= 30000
2. Group remaining employees by department
3. Calculate average salary

---

## 25. What is HAVING?

HAVING filters grouped results.

Example:

SELECT
    department,
    COUNT(*) AS employee_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 10;

Meaning:

Show only departments having more than 10 employees.

Remember:

WHERE = Filter rows

HAVING = Filter groups

---

## 26. WHERE vs HAVING

WHERE:

Filters individual rows.

HAVING:

Filters aggregated/grouped results.

Example:

WHERE:

WHERE salary > 50000

HAVING:

HAVING AVG(salary) > 50000

---

## 27. GROUP BY + HAVING

Example:

Find departments with average salary greater than 60000.

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 60000;

---

## 28. GROUP BY + ORDER BY

Example:

Find departments by highest average salary.

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department
ORDER BY average_salary DESC;

---

## 29. Top Department by Average Salary

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department
ORDER BY average_salary DESC
LIMIT 1;

Thinking:

GROUP → Calculate → Sort → Take top 1

---

## 30. Data Analyst Example

Table:

employees

employee_id
name
department
city
salary

Business Question:

"What is the total salary?"

SELECT SUM(salary) AS total_salary
FROM employees;

---

## 31. Business Question Examples

### Question 1

How many employees are there?

SELECT COUNT(*) AS total_employees
FROM employees;

### Question 2

What is the average salary?

SELECT AVG(salary) AS average_salary
FROM employees;

### Question 3

What is the highest salary?

SELECT MAX(salary) AS highest_salary
FROM employees;

### Question 4

What is the lowest salary?

SELECT MIN(salary) AS lowest_salary
FROM employees;

### Question 5

What is the total salary?

SELECT SUM(salary) AS total_salary
FROM employees;

---

## 32. Department Analysis

Question:

"How many employees are in each department?"

SELECT
    department,
    COUNT(*) AS employee_count
FROM employees
GROUP BY department;

---

## 33. Department Salary Analysis

Question:

"Find average salary by department."

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department;

---

## 34. Highest Average Salary Department

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department
ORDER BY average_salary DESC
LIMIT 1;

---

## 35. Departments with More Than 10 Employees

SELECT
    department,
    COUNT(*) AS employee_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 10;

---

## 36. Unique Cities Count

SELECT COUNT(DISTINCT city) AS unique_city_count
FROM employees;

---

## 37. Data Analyst Thinking

Business Question:

"Which department has the highest average salary?"

Think:

What do I need?

→ Department

What calculation?

→ AVG(salary)

How should I group?

→ GROUP BY department

How should I sort?

→ DESC

How many?

→ 1

Query:

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department
ORDER BY average_salary DESC
LIMIT 1;

Remember:

QUESTION
→ METRIC
→ GROUP
→ FILTER
→ SORT
→ RESULT

---

## 38. Interview Questions

### Q1. What are aggregate functions?

Functions that calculate a result from multiple rows.

### Q2. Name five aggregate functions.

COUNT()
SUM()
AVG()
MIN()
MAX()

### Q3. Difference between COUNT(*) and COUNT(column)?

COUNT(*) counts all rows.

COUNT(column) counts non-NULL values.

### Q4. What is GROUP BY?

GROUP BY creates groups for aggregate calculations.

### Q5. Difference between WHERE and HAVING?

WHERE filters rows.

HAVING filters grouped results.

### Q6. Can we use aggregate functions with GROUP BY?

Yes.

### Q7. How do you count unique values?

COUNT(DISTINCT column)

### Q8. How do you find the highest salary?

SELECT MAX(salary)
FROM employees;

---

## 39. Practice Questions

Practice without looking at the answers:

1. Find total number of employees.
2. Find total salary.
3. Find average salary.
4. Find minimum salary.
5. Find maximum salary.
6. Count unique departments.
7. Count employees in each department.
8. Find total salary by department.
9. Find average salary by department.
10. Find minimum salary by department.
11. Find maximum salary by department.
12. Find employee count by city.
13. Find average salary by city.
14. Find departments having more than 10 employees.
15. Find departments with average salary above 60000.
16. Find the department with the highest average salary.
17. Find the department with the lowest average salary.
18. Find the top 3 departments by total salary.
19. Find the number of employees earning above 50000.
20. Find the average salary of employees earning above 50000.

---

## 40. Quick Cheat Sheet

COUNT()
= Count

SUM()
= Total

AVG()
= Average

MIN()
= Minimum

MAX()
= Maximum

COUNT(DISTINCT)
= Unique count

GROUP BY
= Group data

HAVING
= Filter groups

WHERE
= Filter rows

ORDER BY
= Sort results

LIMIT
= Restrict rows

---

## 41. SQL Thinking Pattern

Simple summary:

SELECT aggregate_function(column)
FROM table;

Grouped summary:

SELECT category, aggregate_function(column)
FROM table
GROUP BY category;

Grouped + filtered:

SELECT category, aggregate_function(column)
FROM table
GROUP BY category
HAVING aggregate_function(column) > value;

Remember:

WHERE → Before Grouping

GROUP BY → Create Groups

HAVING → After Grouping

---

## Day 3 Checklist

[ ] COUNT()
[ ] COUNT(*)
[ ] COUNT(column)
[ ] COUNT(DISTINCT)
[ ] SUM()
[ ] AVG()
[ ] MIN()
[ ] MAX()
[ ] Column aliases
[ ] Aggregate + WHERE
[ ] GROUP BY
[ ] GROUP BY multiple columns
[ ] HAVING
[ ] GROUP BY + ORDER BY
[ ] GROUP BY + LIMIT
[ ] Business scenarios
[ ] Interview questions

---

## Day 3 Key Memory

COUNT = How many?

SUM = How much total?

AVG = What is the average?

MIN = Lowest?

MAX = Highest?

GROUP BY = For each category

WHERE = Filter rows

HAVING = Filter groups

Remember:

AGGREGATE → GROUP → FILTER → SORT

---

## Day 3 Goal

By the end of Day 3, you should be able to:

Calculate totals → Count records → Find averages → Group data → Filter groups → Answer real business questions using SQL.

# SQL Day 3 Completed
