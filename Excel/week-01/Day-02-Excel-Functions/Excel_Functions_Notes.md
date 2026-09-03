# Day 02 - Excel Functions for Data Analysts

## Dataset Used

Excel Table Name: `staff`

| employee | department | employee type | salary |
|---|---|---|---:|
| Ravi | Accounting | Permanent | 70000 |
| Sita | Accounting | Contract | 50000 |
| Arun | Engineering | Permanent | 85000 |
| Kumar | Accounting | Permanent | 65000 |
| Priya | Engineering | Contract | 60000 |
| Ramesh | Marketing | Permanent | 75000 |
| Kiran | Engineering | Permanent | 95000 |
| Anu | Marketing | Contract | 45000 |

---

# 1. COUNTIF

## Definition

`COUNTIF` is used to count the number of rows/cells that satisfy **one condition**.

## Syntax

```excel
=COUNTIF(range,condition)Example 1
Question
How many Permanent employees are there?
Formula
=COUNTIF(staff[employee type],"Permanent")
Result
5
Explanation
Excel checks the employee type column:
- Ravi → Permanent → Yes
- Sita → Contract → No
- Arun → Permanent → Yes
- Kumar → Permanent → Yes
- Priya → Contract → No
- Ramesh → Permanent → Yes
- Kiran → Permanent → Yes
- Anu → Contract → No
Total Permanent employees = 5
Example 2
Question
How many employees have salary greater than 70000?
Formula
=COUNTIF(staff[salary],">70000")
Result
3
Matching salaries:
- 85000
- 75000
- 95000
Memory Rule
COUNTIF = One condition + Count
2. COUNTIFS
Definition
COUNTIFS is used to count rows that satisfy multiple conditions.
All conditions must be TRUE for a row to be counted.
It normally works like AND logic.
Syntax
=COUNTIFS(range1,condition1,range2,condition2,...)
Example 1
Question
How many Permanent employees are there in Accounting?
Formula
=COUNTIFS(staff[department],"Accounting",staff[employee type],"Permanent")
Result
2
Row-by-row checking
- Ravi → Accounting + Permanent → YES
- Sita → Accounting + Contract → NO
- Arun → Engineering + Permanent → NO
- Kumar → Accounting + Permanent → YES
- Priya → Engineering + Contract → NO
- Ramesh → Marketing + Permanent → NO
- Kiran → Engineering + Permanent → NO
- Anu → Marketing + Contract → NO
Total = 2
Example 2
Question
How many Engineering employees are Permanent and earn more than 80000?
Formula
=COUNTIFS(staff[department],"Engineering",staff[employee type],"Permanent",staff[salary],">80000")
Result
2
Matching employees:
- Arun → Engineering + Permanent + 85000 → YES
- Kiran → Engineering + Permanent + 95000 → YES
Total = 2
Memory Rule
COUNTIFS = Multiple conditions + Count
3. SUMIF
Definition
SUMIF is used to add values based on one condition.
Syntax
=SUMIF(criteria_range,criteria,sum_range)
Example
Question
What is the total salary of Accounting employees?
Formula
=SUMIF(staff[department],"Accounting",staff[salary])
Matching employees
- Ravi → 70000
- Sita → 50000
- Kumar → 65000
Calculation
70000 + 50000 + 65000 = 185000
Result
185000
Formula Thinking
Which rows?  → Accounting
What to add? → Salary
Memory Rule
SUMIF = One condition + Sum
4. SUMIFS
Definition
SUMIFS is used to add values based on multiple conditions.
Syntax
=SUMIFS(sum_range,criteria_range1,criteria1,criteria_range2,criteria2,...)
Important
In SUMIFS, the first argument is the sum range.
Example 1
Question
What is the total salary of Permanent employees in Accounting?
Formula
=SUMIFS(staff[salary],staff[department],"Accounting",staff[employee type],"Permanent")
Matching employees
- Ravi → 70000
- Kumar → 65000
Calculation
70000 + 65000 = 135000
Result
135000
Example 2
Question
What is the total salary of Permanent employees earning more than 70000?
Formula
=SUMIFS(staff[salary],staff[employee type],"Permanent",staff[salary],">70000")
Matching employees
- Arun → 85000
- Ramesh → 75000
- Kiran → 95000
Calculation
85000 + 75000 + 95000 = 255000
Result
255000
Memory Rule
SUMIFS = Multiple conditions + Sum
5. AVERAGEIF
Definition
AVERAGEIF calculates the average of values that satisfy one condition.
Syntax
=AVERAGEIF(criteria_range,criteria,average_range)
Example
Question
What is the average salary of Accounting employees?
Formula
=AVERAGEIF(staff[department],"Accounting",staff[salary])
Matching salaries
- 70000
- 50000
- 65000
Calculation
(70000 + 50000 + 65000) / 3
= 61666.67
Result
61666.67
Memory Rule
AVERAGEIF = One condition + Average
6. AVERAGEIFS
Definition
AVERAGEIFS calculates the average of values that satisfy multiple conditions.
Syntax
=AVERAGEIFS(average_range,criteria_range1,criteria1,criteria_range2,criteria2,...)
Example
Question
What is the average salary of Permanent employees in Engineering?
Formula
=AVERAGEIFS(staff[salary],staff[department],"Engineering",staff[employee type],"Permanent")
Matching employees
- Arun → 85000
- Kiran → 95000
Calculation
(85000 + 95000) / 2
= 90000
Result
90000
Memory Rule
AVERAGEIFS = Multiple conditions + Average
7. COUNTA
Definition
COUNTA counts cells that are not empty.
It can count text, numbers, dates, etc.
Syntax
=COUNTA(range)
Example
Question
How many employee names are available?
Formula
=COUNTA(staff[employee])
Result
8
Because all 8 employee names are filled.
Memory Rule
COUNTA = Count non-empty cells
8. COUNTBLANK
Definition
COUNTBLANK counts the number of empty cells in a range.
Syntax
=COUNTBLANK(range)
Example
Suppose some salary cells are blank.
Formula
=COUNTBLANK(staff[salary])
If 2 salary cells are blank:
Result
2
Memory Rule
COUNTBLANK = Count empty cells
9. ROUND
Definition
ROUND rounds a number using normal mathematical rounding rules.
Syntax
=ROUND(number,num_digits)
Example 1
=ROUND(67845.6789,2)
Result
67845.68
The third decimal digit is 8, so the second decimal digit is rounded up.
Example 2 - 1 Decimal Place
=ROUND(67845.678,1)
Result
67845.7
Example 3 - Whole Number
=ROUND(67845.678,0)
Result
67846
Example 4 - Nearest 10
=ROUND(67845.678,-1)
Result
67850
Example 5 - Nearest 100
=ROUND(67845.678,-2)
Result
67800
num_digits Meaning
num_digits	Meaning
2	2 decimal places
1	1 decimal place
0	Whole number
-1	Nearest 10
-2	Nearest 100


Memory Rule
ROUND = Normal mathematical rounding
10. ROUNDUP
Definition
ROUNDUP rounds a number up/away from zero when digits are removed.
Syntax
=ROUNDUP(number,num_digits)
Example 1
=ROUNDUP(67845.671,2)
Result
67845.68
Example 2
=ROUNDUP(67845.601,2)
Result
67845.61
Memory Rule
ROUNDUP = Round upward
11. ROUNDDOWN
Definition
ROUNDDOWN rounds a number down/toward zero when digits are removed.
Syntax
=ROUNDDOWN(number,num_digits)
Example
=ROUNDDOWN(67845.689,2)
Result
67845.68
Memory Rule
ROUNDDOWN = Round downward
Quick Comparison
Function	Purpose	Conditions
COUNTIF	Count	One
COUNTIFS	Count	Multiple
SUMIF	Sum	One
SUMIFS	Sum	Multiple
AVERAGEIF	Average	One
AVERAGEIFS	Average	Multiple
COUNTA	Count non-empty	None
COUNTBLANK	Count blank	None
ROUND	Normal rounding	None
ROUNDUP	Round up	None
ROUNDDOWN	Round down	None


Formula Selection Method
When a business question comes, first identify what you need.
If you need COUNT
1 condition  → COUNTIF
Multiple conditions → COUNTIFS
If you need SUM
1 condition  → SUMIF
Multiple conditions → SUMIFS
If you need AVERAGE
1 condition  → AVERAGEIF
Multiple conditions → AVERAGEIFS
Interview Question Understanding
Question
How many Permanent employees in Engineering earn more than 80000?
Step 1 - What do I need?
Count
Step 2 - Conditions
- Department = Engineering
- Employee Type = Permanent
- Salary > 80000
Step 3 - Choose function
Multiple conditions + Count
COUNTIFS
Step 4 - Build formula
=COUNTIFS(staff[department],"Engineering",staff[employee type],"Permanent",staff[salary],">80000")
Result
2
Day 02 Completed Topics
- COUNTIF
- COUNTIFS
- SUMIF
- SUMIFS
- AVERAGEIF
- AVERAGEIFS
- COUNTA
- COUNTBLANK
- ROUND
- ROUNDUP
- ROUNDDOWN
Day 02 Status
COMPLETED
Key Learning
Today I learned how to:
- Count data based on conditions
- Count data using multiple conditions
- Sum values based on conditions
- Sum values using multiple conditions
- Calculate averages based on conditions
- Count non-empty cells
- Count blank cells
- Round numbers normally
- Round numbers up
- Round numbers down
- Select the correct Excel function based on a business question
