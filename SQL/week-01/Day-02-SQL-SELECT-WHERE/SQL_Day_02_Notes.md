# SQL Day 02 — SELECT, WHERE & Filtering

## 1. Day 2 Objective

Learn:

- SELECT
- WHERE
- DISTINCT
- Comparison Operators
- AND
- OR
- NOT
- IN
- BETWEEN
- LIKE
- IS NULL
- IS NOT NULL
- ORDER BY
- LIMIT

Remember:

SELECT → Choose columns
WHERE → Filter rows
ORDER BY → Sort results
LIMIT → Restrict results

---

## 2. SELECT

Used to retrieve data from a table.

SELECT column_name
FROM table_name;

Example:

SELECT name
FROM employees;

---

## 3. Select Multiple Columns

SELECT name, salary, department
FROM employees;

---

## 4. Select All Columns

SELECT *
FROM employees;

Interview note:

Use specific columns instead of * when you only need certain columns.

---

## 5. WHERE

Used to filter rows based on a condition.

SELECT *
FROM employees
WHERE salary > 50000;

Meaning:

Return employees whose salary is greater than 50000.

---

## 6. Comparison Operators

=   Equal
>   Greater than
<   Less than
>=  Greater than or equal
<=  Less than or equal
<>  Not equal

Examples:

SELECT *
FROM employees
WHERE salary = 50000;

SELECT *
FROM employees
WHERE salary >= 50000;

SELECT *
FROM employees
WHERE salary <> 50000;

---

## 7. AND

Used when ALL conditions must be true.

SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 50000;

Meaning:

Department must be IT
AND
Salary must be greater than 50000.

---

## 8. OR

Used when ANY condition can be true.

SELECT *
FROM employees
WHERE department = 'IT'
OR department = 'HR';

---

## 9. NOT

Used to exclude a condition.

SELECT *
FROM employees
WHERE NOT department = 'HR';

---

## 10. DISTINCT

Used to return unique values.

SELECT DISTINCT department
FROM employees;

Example:

IT
HR
Sales
Finance

---

## 11. IN

Used to match multiple values.

SELECT *
FROM employees
WHERE department IN ('IT', 'HR', 'Sales');

Same idea as:

department = 'IT'
OR department = 'HR'
OR department = 'Sales'

Remember:

IN = Multiple exact values

---

## 12. NOT IN

Used to exclude multiple values.

SELECT *
FROM employees
WHERE department NOT IN ('HR', 'Finance');

---

## 13. BETWEEN

Used to filter values within a range.

SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 80000;

Important:

BETWEEN includes both boundary values.

---

## 14. NOT BETWEEN

SELECT *
FROM employees
WHERE salary NOT BETWEEN 40000 AND 80000;

---

## 15. LIKE

Used for pattern matching.

### Starts with

SELECT *
FROM employees
WHERE name LIKE 'A%';

A%

Means starts with A.

### Ends with

SELECT *
FROM employees
WHERE name LIKE '%a';

### Contains

SELECT *
FROM employees
WHERE name LIKE '%an%';

---

## 16. LIKE Wildcards

% = Any number of characters

_ = Exactly one character

Example:

'A%' 
Starts with A

'%a'
Ends with a

'%an%'
Contains an

'_n%'
Second character is n

---

## 17. IS NULL

Used to find missing values.

SELECT *
FROM employees
WHERE manager_id IS NULL;

Important:

Never use:

manager_id = NULL

Correct:

manager_id IS NULL

---

## 18. IS NOT NULL

Used to find non-missing values.

SELECT *
FROM employees
WHERE manager_id IS NOT NULL;

---

## 19. ORDER BY

Used to sort results.

Ascending:

SELECT *
FROM employees
ORDER BY salary ASC;

Descending:

SELECT *
FROM employees
ORDER BY salary DESC;

Remember:

ASC = Small → Large

DESC = Large → Small

---

## 20. ORDER BY Multiple Columns

SELECT *
FROM employees
ORDER BY department ASC, salary DESC;

First sorts by department.

Then salary within each department.

---

## 21. LIMIT

Used to restrict the number of rows returned.

SELECT *
FROM employees
LIMIT 5;

Returns only 5 rows.

---

## 22. Top 5 Highest Salaries

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;

Thinking:

1. Sort salary high to low
2. Take first 5

---

## 23. Top 10 Lowest Salaries

SELECT *
FROM employees
ORDER BY salary ASC
LIMIT 10;

---

## 24. SQL Execution Thinking

Basic order:

FROM
↓
WHERE
↓
SELECT
↓
ORDER BY
↓
LIMIT

Remember:

FROM → WHERE → SELECT → ORDER → LIMIT

---

## 25. Data Analyst Example

Table:

employees

Columns:

employee_id
name
department
city
salary
experience

Example questions:

### Question 1
Find employees from Hyderabad.

SELECT *
FROM employees
WHERE city = 'Hyderabad';

### Question 2
Find employees earning above 60000.

SELECT *
FROM employees
WHERE salary > 60000;

### Question 3
Find IT employees earning above 50000.

SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 50000;

### Question 4
Find employees from Hyderabad or Bangalore.

SELECT *
FROM employees
WHERE city IN ('Hyderabad', 'Bangalore');

### Question 5
Find employees with salary between 40000 and 80000.

SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 80000;

### Question 6
Find employees whose names start with A.

SELECT *
FROM employees
WHERE name LIKE 'A%';

### Question 7
Find employees without a manager.

SELECT *
FROM employees
WHERE manager_id IS NULL;

---

## 26. Interview Questions

### Q1. What is WHERE?

WHERE filters rows based on a condition.

### Q2. Difference between WHERE and DISTINCT?

WHERE filters rows.

DISTINCT removes duplicate values from the selected result.

### Q3. Difference between IN and BETWEEN?

IN checks multiple specific values.

BETWEEN checks a range.

### Q4. How do you find NULL values?

Use:

IS NULL

### Q5. How do you find non-NULL values?

Use:

IS NOT NULL

### Q6. What is LIKE?

LIKE is used for pattern matching.

### Q7. Difference between % and _ in LIKE?

% = Any number of characters.

_ = One character.

### Q8. How do you find the top 5 salaries?

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;

---

## 27. Data Analyst Thinking

When a business asks:

"Give me the top 5 employees by salary."

Think:

What data?
→ Employees

What column?
→ Salary

What filter?
→ None

What sorting?
→ DESC

How many?
→ 5

Query pattern:

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;

---

## 28. Practice Questions

Practice without looking at the answers:

1. Find all employees from Hyderabad.
2. Find employees earning more than 50000.
3. Find employees earning less than 40000.
4. Find IT employees.
5. Find IT employees earning more than 60000.
6. Find employees from Hyderabad or Chennai.
7. Find employees from Hyderabad, Chennai, or Bangalore using IN.
8. Find salaries between 50000 and 90000.
9. Find employees whose names start with S.
10. Find employees whose names end with n.
11. Find employees whose names contain 'an'.
12. Find employees with NULL manager_id.
13. Find employees with a manager.
14. Find unique departments.
15. Find the 5 highest salaries.
16. Find the 10 lowest salaries.
17. Sort employees by salary descending.
18. Sort employees by department and salary.
19. Exclude HR and Finance departments.
20. Find employees whose salary is NOT between 40000 and 70000.

---

## 29. Quick Cheat Sheet

SELECT
= Choose columns

WHERE
= Filter rows

DISTINCT
= Unique values

AND
= All conditions true

OR
= Any condition true

NOT
= Exclude condition

IN
= Multiple exact values

BETWEEN
= Range

LIKE
= Pattern matching

IS NULL
= Missing values

IS NOT NULL
= Non-missing values

ORDER BY
= Sort

ASC
= Low → High

DESC
= High → Low

LIMIT
= Number of rows

---

## 30. Day 2 Key Memory

SELECT = What do I need?

FROM = Where is the data?

WHERE = Which rows?

DISTINCT = Unique values

IN = Multiple values

BETWEEN = Range

LIKE = Pattern

IS NULL = Missing

ORDER BY = Sort

LIMIT = How many?

---

## Day 2 Checklist

[ ] SELECT
[ ] WHERE
[ ] DISTINCT
[ ] Comparison Operators
[ ] AND
[ ] OR
[ ] NOT
[ ] IN
[ ] NOT IN
[ ] BETWEEN
[ ] NOT BETWEEN
[ ] LIKE
[ ] Wildcards
[ ] IS NULL
[ ] IS NOT NULL
[ ] ORDER BY
[ ] ASC
[ ] DESC
[ ] LIMIT
[ ] Practice filtering questions
[ ] Practice business scenarios

---

## Day 2 Goal

By the end of Day 2, you should be able to:

Select required data → Filter rows → Find specific records → Handle NULL values → Sort results → Get top/bottom records.

# SQL Day 2 Completed
