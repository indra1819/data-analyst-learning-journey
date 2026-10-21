# Python Day 03 — Filtering Data

## 1. Day 3 Objective

Learn:

- What is filtering?
- Comparison operators
- Boolean conditions
- Filter rows
- Filter using one condition
- Filter using multiple conditions
- AND / OR conditions
- isin()
- Between values
- String filtering
- NULL filtering
- Data Analyst practical examples

Remember:

Filter = Select only the rows you need.

---

## 2. What is Filtering?

Filtering means selecting only the rows that satisfy a condition.

Example:

If we have employee data and want employees with salary > 50000:

df[df["Salary"] > 50000]

---

## 3. Basic Filtering

Example DataFrame:

import pandas as pd

data = {
    "Name": ["Indra", "Rahul", "Anil", "Priya"],
    "City": ["Hyderabad", "Chennai", "Bangalore", "Hyderabad"],
    "Salary": [50000, 40000, 60000, 70000]
}

df = pd.DataFrame(data)

Filter salary greater than 50000:

df[df["Salary"] > 50000]

---

## 4. Comparison Operators

>   Greater than

<   Less than

>=  Greater than or equal

<=  Less than or equal

==  Equal

!=  Not equal

Example:

df[df["Salary"] >= 60000]

---

## 5. Filter Equal Value

Find employees from Hyderabad:

df[df["City"] == "Hyderabad"]

Important:

Use == for comparison.

Do NOT use:

df[df["City"] = "Hyderabad"]

Correct:

df[df["City"] == "Hyderabad"]

---

## 6. Filter Not Equal

Find employees who are not from Hyderabad:

df[df["City"] != "Hyderabad"]

---

## 7. Filter Greater Than

Find employees earning more than 50000:

df[df["Salary"] > 50000]

---

## 8. Filter Less Than

Find employees earning less than 50000:

df[df["Salary"] < 50000]

---

## 9. Filter Multiple Conditions — AND

Use & for AND.

Example:

Hyderabad employees with salary above 50000:

df[(df["City"] == "Hyderabad") & (df["Salary"] > 50000)]

Remember:

AND = &

Important:

Put each condition inside parentheses.

---

## 10. Filter Multiple Conditions — OR

Use | for OR.

Example:

Employees from Hyderabad OR Chennai:

df[(df["City"] == "Hyderabad") | (df["City"] == "Chennai")]

Remember:

OR = |

---

## 11. NOT Condition

Use ~ to reverse a condition.

Example:

Employees who are NOT from Hyderabad:

df[~(df["City"] == "Hyderabad")]

Remember:

NOT = ~

---

## 12. Filter Multiple Values Using isin()

Instead of:

df[(df["City"] == "Hyderabad") | (df["City"] == "Chennai")]

Use:

df[df["City"].isin(["Hyderabad", "Chennai"])]

Remember:

isin() = Match multiple values

---

## 13. NOT IN Using isin()

Employees who are not from Hyderabad or Chennai:

df[~df["City"].isin(["Hyderabad", "Chennai"])]

---

## 14. Filter Range Using Between

Find salaries between 40000 and 70000:

df[df["Salary"].between(40000, 70000)]

Important:

between() includes the boundary values by default.

---

## 15. Multiple Numeric Conditions

Example:

Salary between 40000 and 70000:

df[(df["Salary"] >= 40000) & (df["Salary"] <= 70000)]

Better shortcut:

df[df["Salary"].between(40000, 70000)]

---

## 16. Filter Text Using str.contains()

Find names containing "a":

df[df["Name"].str.contains("a")]

Case-insensitive:

df[df["Name"].str.contains("a", case=False, na=False)]

Remember:

str.contains() = Search text pattern

---

## 17. Starts With

Find names starting with "A":

df[df["Name"].str.startswith("A")]

---

## 18. Ends With

Find names ending with "a":

df[df["Name"].str.endswith("a")]

---

## 19. Case-Insensitive Text Filtering

Example:

df[df["City"].str.contains("hyderabad", case=False, na=False)]

This matches:

Hyderabad
HYDERABAD
hyderabad

---

## 20. Handle NULL Values While Filtering

Example:

df[df["City"].notna()]

Returns rows where City is not missing.

Find missing City:

df[df["City"].isna()]

Remember:

isna() = Missing values

notna() = Non-missing values

---

## 21. Filter Using Two Columns

Example:

Find Hyderabad employees earning more than 60000:

df[(df["City"] == "Hyderabad") & (df["Salary"] > 60000)]

---

## 22. Filter Using Three Conditions

Example:

Hyderabad employees
AND
Salary > 50000
AND
Name starts with A

df[
    (df["City"] == "Hyderabad") &
    (df["Salary"] > 50000) &
    (df["Name"].str.startswith("A"))
]

---

## 23. Filtering and Selecting Columns

Suppose we want only Name and Salary for employees earning above 50000.

df.loc[
    df["Salary"] > 50000,
    ["Name", "Salary"]
]

This is very useful in Data Analyst work.

Remember:

loc[rows, columns]

---

## 24. Filtering With loc()

Example:

df.loc[df["City"] == "Hyderabad"]

Filter and select columns:

df.loc[
    df["City"] == "Hyderabad",
    ["Name", "Salary"]
]

---

## 25. Filtering With iloc()

iloc is mainly position-based.

Example:

df.iloc[0:3]

This selects rows by position.

For condition-based filtering, loc[] is usually more appropriate.

---

## 26. Filter and Sort

Find employees earning above 50000 and sort by salary descending:

df[df["Salary"] > 50000].sort_values(
    "Salary",
    ascending=False
)

This combines:

Filter → Sort

---

## 27. Filter and Count Rows

Count employees earning above 50000:

len(df[df["Salary"] > 50000])

Another method:

(df["Salary"] > 50000).sum()

---

## 28. Data Analyst Example

Dataset:

Order_ID | Customer | City | Sales

1001 | Indra | Hyderabad | 50000
1002 | Rahul | Chennai | 40000
1003 | Anil | Bangalore | 60000
1004 | Priya | Hyderabad | 80000
1005 | Kiran | Pune | 30000

Business question:

"Find orders with sales above 50000."

Solution:

df[df["Sales"] > 50000]

---

## 29. Business Question Examples

### Question 1

Find Hyderabad orders.

df[df["City"] == "Hyderabad"]

### Question 2

Find sales above 50000.

df[df["Sales"] > 50000]

### Question 3

Find sales between 40000 and 70000.

df[df["Sales"].between(40000, 70000)]

### Question 4

Find Hyderabad and Chennai orders.

df[df["City"].isin(["Hyderabad", "Chennai"])]

### Question 5

Find orders below 50000.

df[df["Sales"] < 50000]

### Question 6

Find customers whose names contain "an".

df[df["Customer"].str.contains("an", case=False, na=False)]

---

## 30. Common Filtering Mistakes

### Mistake 1

Using = instead of ==

Wrong:

df[df["Salary"] = 50000]

Correct:

df[df["Salary"] == 50000]

### Mistake 2

Using "and"

Wrong:

df[(df["Salary"] > 50000) and (df["City"] == "Hyderabad")]

Correct:

df[(df["Salary"] > 50000) & (df["City"] == "Hyderabad")]

### Mistake 3

Forgetting parentheses

Wrong:

df[df["Salary"] > 50000 & df["Age"] > 25]

Correct:

df[(df["Salary"] > 50000) & (df["Age"] > 25)]

---

## 31. Data Analyst Thinking

When a business gives you a filtering question, think:

What rows do I need?

What column should I check?

What condition?

One condition or multiple?

AND or OR?

Do I need specific columns only?

Example:

"Show Hyderabad customers with sales above 50000."

Think:

Rows:
Hyderabad customers

Condition 1:
City = Hyderabad

Condition 2:
Sales > 50000

Connection:
AND

Query:

df[(df["City"] == "Hyderabad") & (df["Sales"] > 50000)]

---

## 32. Interview Questions

### Q1. How do you filter rows in Pandas?

Use Boolean conditions.

Example:

df[df["Salary"] > 50000]

### Q2. How do you apply AND conditions?

Use &.

df[(condition1) & (condition2)]

### Q3. How do you apply OR conditions?

Use |.

df[(condition1) | (condition2)]

### Q4. How do you filter multiple values?

Use isin().

df[df["City"].isin(["Hyderabad", "Chennai"])]

### Q5. How do you filter a range?

Use between().

df[df["Salary"].between(40000, 70000)]

### Q6. How do you find missing values?

df[df["City"].isna()]

### Q7. How do you find non-missing values?

df[df["City"].notna()]

### Q8. How do you filter text?

Use str.contains(), str.startswith(), or str.endswith().

---

## 33. Quick Cheat Sheet

df[df["Salary"] > 50000]
= Greater than

df[df["Salary"] < 50000]
= Less than

df[df["Salary"] == 50000]
= Equal

df[df["Salary"] != 50000]
= Not equal

df[(condition1) & (condition2)]
= AND

df[(condition1) | (condition2)]
= OR

df[~condition]
= NOT

df[df["City"].isin(["Hyderabad", "Chennai"])]
= Multiple values

df[df["Salary"].between(40000, 70000)]
= Range

df[df["Name"].str.contains("an")]
= Contains text

df[df["Name"].str.startswith("A")]
= Starts with

df[df["Name"].str.endswith("a")]
= Ends with

df[df["City"].isna()]
= Missing values

df[df["City"].notna()]
= Non-missing values

---

## 34. Day 3 Practice

Create this DataFrame:

Order_ID:
1001, 1002, 1003, 1004, 1005, 1006

Customer:
Indra, Rahul, Anil, Priya, Kiran, Arun

City:
Hyderabad, Chennai, Bangalore, Hyderabad, Pune, Hyderabad

Sales:
50000, 40000, 60000, 80000, 30000, 70000

Practice:

1. Find Hyderabad orders.
2. Find sales above 50000.
3. Find sales below 50000.
4. Find sales equal to 50000.
5. Find Hyderabad orders with sales above 50000.
6. Find Hyderabad or Chennai orders.
7. Use isin() for Hyderabad and Pune.
8. Find sales between 40000 and 70000.
9. Find customers whose name starts with A.
10. Find customers whose name contains "an".
11. Exclude Hyderabad orders.
12. Filter and return only Customer and Sales.
13. Filter sales above 50000 and sort descending.
14. Count orders with sales above 50000.
15. Find missing City values if they exist.

---

## 35. Day 3 Challenge

Business requirement:

"Management wants a list of Hyderabad customers whose sales are between 50000 and 100000. Show only Customer, City and Sales, and sort the result from highest sales to lowest."

Think:

Filter 1:
City = Hyderabad

Filter 2:
Sales between 50000 and 100000

Columns:
Customer, City, Sales

Sort:
Sales descending

Try to write the solution yourself before checking your notes.

---

## 36. Day 3 Checklist

[ ] Understand filtering
[ ] Comparison operators
[ ] Equal and not equal
[ ] Greater than
[ ] Less than
[ ] AND
[ ] OR
[ ] NOT
[ ] isin()
[ ] between()
[ ] str.contains()
[ ] startswith()
[ ] endswith()
[ ] isna()
[ ] notna()
[ ] loc[]
[ ] Filter and select columns
[ ] Filter and sort
[ ] Practice business scenarios

---

## 37. Day 3 Key Memory

Filtering = Select required rows

== = Equal

!= = Not Equal

> = Greater

< = Less

& = AND

| = OR

~ = NOT

isin() = Multiple values

between() = Range

str.contains() = Contains text

isna() = Missing

notna() = Not missing

loc[] = Filter + Select

Remember:

QUESTION → CONDITION → FILTER → REQUIRED COLUMNS → RESULT

---

## Day 3 Goal

By the end of Day 3, you should be able to:

Filter rows → Apply multiple conditions → Search text → Handle missing values → Select required columns → Solve real Data Analyst filtering questions.

# Python Day 3 Completed
