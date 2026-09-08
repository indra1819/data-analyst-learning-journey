# SQL Day 02 – Filtering & Operators

## 1. WHERE Clause

The `WHERE` clause is used to filter rows based on a condition.

### Example

```sql
SELECT *
FROM employees
WHERE department = 'IT';
2. Comparison Operators
Comparison operators are used to compare values.
Operator	Meaning
=	Equal to
>	Greater than
<	Less than
>=	Greater than or equal to
<=	Less than or equal to
<>	Not equal to
!=	Not equal to


Examples
SELECT *
FROM employees
WHERE salary > 50000;
SELECT *
FROM employees
WHERE salary <= 50000;
SELECT *
FROM employees
WHERE department <> 'HR';
3. AND Operator
AND is used when all conditions must be true.
SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 50000;
Both conditions must be satisfied.
4. OR Operator
OR is used when at least one condition must be true.
SELECT *
FROM employees
WHERE department = 'IT'
OR department = 'Sales';
Employees from either IT or Sales are returned.
5. NOT Operator
NOT reverses a condition.
SELECT *
FROM employees
WHERE NOT department = 'HR';
This returns employees who are not in HR.
6. BETWEEN Operator
BETWEEN is used to filter values within a range.
SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 60000;
BETWEEN includes both boundary values.
7. IN Operator
IN is used to match multiple possible values.
Instead of:
SELECT *
FROM employees
WHERE department = 'IT'
OR department = 'HR'
OR department = 'Sales';
We can write:
SELECT *
FROM employees
WHERE department IN ('IT', 'HR', 'Sales');
IN makes queries shorter and easier to read.
8. NOT IN
NOT IN excludes specified values.
SELECT *
FROM employees
WHERE department NOT IN ('HR', 'Sales');
This returns employees who are not in HR or Sales.
9. LIKE Operator
LIKE is used for pattern matching.
Starts with
SELECT *
FROM employees
WHERE first_name LIKE 'A%';
Returns names starting with A.
Ends with
SELECT *
FROM employees
WHERE first_name LIKE '%a';
Returns names ending with a.
Contains
SELECT *
FROM employees
WHERE first_name LIKE '%an%';
Returns names containing an.
10. Wildcards
SQL commonly uses these wildcards with LIKE.
Wildcard	Meaning
%	Zero or more characters
_	Exactly one character


% Example
SELECT *
FROM employees
WHERE first_name LIKE 'R%';
Matches:
Ravi
Rahul
Ramesh
_ Example
SELECT *
FROM employees
WHERE first_name LIKE 'A___';
Matches names with exactly 4 characters starting with A.
11. IS NULL
NULL represents a missing or unknown value.
To find NULL values, use IS NULL.
SELECT *
FROM employees
WHERE manager_id IS NULL;
12. IS NOT NULL
To find records where a value exists:
SELECT *
FROM employees
WHERE manager_id IS NOT NULL;
13. NULL vs 0
NULL and 0 are different.
- NULL → Missing / unknown value
- 0 → Actual numeric value zero
Example:
salary = NULL
means salary information is missing.
salary = 0
means salary is actually zero.
14. Combining Multiple Operators
SQL operators can be combined to create business conditions.
Example
Find IT employees earning more than 50,000:
SELECT *
FROM employees
WHERE department = 'IT'
AND salary > 50000;
Example
Find employees from IT or Sales earning more than 50,000:
SELECT *
FROM employees
WHERE (department = 'IT' OR department = 'Sales')
AND salary > 50000;
Parentheses help control the order in which conditions are evaluated.
15. Practical Data Analyst Examples
Employees earning between 40,000 and 70,000
SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 70000;
Employees from selected departments
SELECT *
FROM employees
WHERE department IN ('IT', 'Finance', 'Sales');
Customers whose name starts with 'S'
SELECT *
FROM customers
WHERE customer_name LIKE 'S%';
Products with missing category
SELECT *
FROM products
WHERE category IS NULL;
Orders above 10,000
SELECT *
FROM orders
WHERE sales > 10000;
16. Important Difference
WHERE + AND
WHERE salary > 50000
AND department = 'IT'
Both conditions must be true.
WHERE + OR
WHERE department = 'IT'
OR department = 'Sales'
At least one condition must be true.
BETWEEN
Used for ranges.
WHERE salary BETWEEN 40000 AND 60000
IN
Used for multiple specific values.
WHERE department IN ('IT', 'HR', 'Sales')
LIKE
Used for pattern matching.
WHERE first_name LIKE 'A%'
IS NULL
Used to check missing values.
WHERE manager_id IS NULL
17. Key Interview Points
- WHERE filters rows.
- AND requires all conditions to be true.
- OR requires at least one condition to be true.
- NOT reverses a condition.
- BETWEEN filters a range and includes boundary values.
- IN checks multiple possible values.
- LIKE is used for pattern matching.
- % represents zero or more characters.
- _ represents exactly one character.
- Use IS NULL to check NULL values.
- Use IS NOT NULL to check non-NULL values.
- NULL is not equal to 0.
- Parentheses can be used to control condition evaluation.
Day 02 Summary
Today we learned how to filter data using:
WHERE
=
>
<
>=
<=
<>
!=
AND
OR
NOT
BETWEEN
IN
NOT IN
LIKE
IS NULL
IS NOT NULL
