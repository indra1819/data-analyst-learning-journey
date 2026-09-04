Day 3 — Excel Functions
Topics Covered
- IF
- IFS
- AND
- OR
- NOT
- IFERROR
- MAXIFS
- MINIFS
1. IF
Business Question
If an employee's salary is greater than ₹80,000, classify them as Senior Salary, otherwise Regular Salary.
Formula
=IF(staff[salary]>80000,"Senior Salary","Regular Salary")
How Excel evaluates
Excel checks each employee's salary:
- Salary > 80,000 → Senior Salary
- Salary ≤ 80,000 → Regular Salary
Interview Meaning
IF is used when we need to make a decision based on a condition.
2. IFS
Business Question
Classify employees based on salary:
- ₹80,000 or more → High
- ₹60,000 or more → Medium
- Below ₹60,000 → Low
Formula
=IFS(staff[salary]>=80000,"High",staff[salary]>=60000,"Medium",staff[salary]<60000,"Low")
Important Point
IFS checks conditions from top to bottom and returns the result for the first TRUE condition.
Therefore, arrange conditions carefully.
Interview Meaning
IFS is useful when there are multiple conditions and multiple possible results.
3. AND
Business Question
An employee is eligible for a bonus only if:
- Employee Type = Permanent
- AND Salary > ₹70,000
Formula
=AND(staff[employee type]="Permanent",staff[salary]>70000)
Practical Formula
=IF(AND(staff[employee type]="Permanent",staff[salary]>70000),"Bonus Eligible","Not Eligible")
Interview Meaning
AND returns TRUE only when all conditions are TRUE.
AND = All conditions must be TRUE.

4. OR
Business Question
An employee gets a special benefit if:
- Department = Engineering
- OR Salary > ₹90,000
Formula
=OR(staff[department]="Engineering",staff[salary]>90000)
Practical Formula
=IF(OR(staff[department]="Engineering",staff[salary]>90000),"Special Benefit","Not Eligible")
Interview Meaning
OR returns TRUE when at least one condition is TRUE.
OR = Any one condition can be TRUE.

5. NOT
Business Question
Identify employees who are not from the Engineering department.
Formula
=NOT(staff[department]="Engineering")
Practical Formula
=IF(NOT(staff[department]="Engineering"),"Non-Engineering","Engineering")
Interview Meaning
NOT reverses TRUE and FALSE.
TRUE → FALSE
FALSE → TRUE

6. IFERROR
Business Question
Calculate Profit Margin. If the calculation produces an error, display Invalid Calculation.
Syntax
=IFERROR(value,value_if_error)
Formula
=IFERROR(staff[profit]/staff[sales],"Invalid Calculation")
Example
If:
Profit = 10,000
Sales = 0
Normal calculation:
10,000 / 0
produces an error.
IFERROR replaces that error with:
Invalid Calculation
Interview Meaning
IFERROR is used to handle formula errors and display a meaningful result instead of an Excel error.
7. MAXIFS
Business Question
Find the highest salary among Permanent employees.
Formula
=MAXIFS(staff[salary],staff[employee type],"Permanent")
Result
₹95,000
Multiple Conditions
Find the highest salary among Permanent Engineering employees:
=MAXIFS(staff[salary],staff[department],"Engineering",staff[employee type],"Permanent")
Interview Meaning
MAXIFS returns the maximum value after applying one or more conditions.
MAXIFS = Highest value with conditions.

8. MINIFS
Business Question
Find the lowest salary among Permanent employees.
Formula
=MINIFS(staff[salary],staff[employee type],"Permanent")
Result
₹65,000
Multiple Conditions
Find the lowest salary among Contract employees in Engineering:
=MINIFS(staff[salary],staff[department],"Engineering",staff[employee type],"Contract")
Interview Meaning
MINIFS returns the minimum value after applying one or more conditions.
MINIFS = Lowest value with conditions.

Day 3 Quick Revision
Function	Purpose
IF	One condition → two possible results
IFS	Multiple conditions → multiple results
AND	All conditions must be TRUE
OR	At least one condition must be TRUE
NOT	Reverses TRUE/FALSE
IFERROR	Handles formula errors
MAXIFS	Highest value with conditions
MINIFS	Lowest value with conditions


Day 3 Completed ✅
