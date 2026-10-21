# Excel Day 08 — Data Validation

## 1. Day 8 Objective

Learn:

- What is Data Validation?
- Create dropdown lists
- Restrict numbers
- Restrict dates
- Restrict text length
- Custom validation
- Input messages
- Error alerts
- Data validation for Data Analyst work

Remember:

Data Validation = Control what users can enter

---

## 2. What is Data Validation?

Data Validation is an Excel feature used to control and restrict the type of data entered into a cell.

Examples:

- Only numbers
- Only dates
- Only specific text
- Dropdown selections
- Values within a range

---

## 3. Why Data Validation is Important?

It helps to:

- Reduce data-entry errors
- Maintain consistent data
- Standardize values
- Improve data quality
- Make dashboards more reliable

Remember:

Good Input → Good Data → Good Analysis

---

## 4. Data Validation Location

Excel:

Data → Data Validation

Shortcut:

Alt + A + V + V

---

## 5. Create a Dropdown List

Example:

Department:

IT
HR
Finance
Sales

Steps:

1. Select the cells
2. Data → Data Validation
3. Allow → List
4. Enter:

IT,HR,Finance,Sales

5. Click OK

Now users can select from a dropdown.

---

## 6. Dropdown from a Cell Range

Suppose:

H2 = IT
H3 = HR
H4 = Finance
H5 = Sales

Data Validation:

Allow → List

Source:

=$H$2:$H$5

This is better than manually typing values.

---

## 7. Number Validation

Example:

Allow only numbers between 1 and 100.

Steps:

Data → Data Validation

Allow:
Whole Number

Data:
between

Minimum:
1

Maximum:
100

Now values outside the range are rejected.

---

## 8. Decimal Validation

Example:

Allow sales between 0 and 1,000,000.

Allow:

Decimal

Data:

between

Minimum:

0

Maximum:

1000000

Useful for:

- Sales
- Revenue
- Price
- Discount

---

## 9. Date Validation

Example:

Allow dates only from 01-Jan-2026 to 31-Dec-2026.

Allow:

Date

Data:

between

Start date:

01/01/2026

End date:

31/12/2026

Useful for:

- Order Date
- Joining Date
- Transaction Date

---

## 10. Time Validation

Data Validation can also restrict time.

Example:

Allow time between:

09:00 AM

and

06:00 PM

Useful for:

- Working hours
- Appointment time
- Shift timing

---

## 11. Text Length Validation

Example:

Allow maximum 10 characters.

Allow:

Text length

Data:

less than or equal to

Maximum:

10

Useful for:

- Employee IDs
- Product Codes
- Phone-related inputs
- Short codes

---

## 12. Custom Validation

Custom validation uses an Excel formula.

Example:

Allow only positive numbers:

=A2>0

Example:

Allow only values greater than 100:

=A2>100

Example:

Prevent duplicate Employee IDs:

=COUNTIF($A:$A,A2)=1

Custom validation is useful when standard rules are not enough.

---

## 13. Input Message

Input Message tells users what they should enter.

Example:

Title:

Sales Entry

Message:

Enter sales amount between 0 and 1000000.

This improves data-entry clarity.

---

## 14. Error Alert

Error Alert appears when a user enters invalid data.

Types:

Stop
Warning
Information

### Stop

Completely prevents invalid data.

Use when accuracy is critical.

### Warning

Allows the user to continue after confirmation.

### Information

Shows a message but allows the entry.

Remember:

Stop = Strict

Warning = Flexible

Information = Informational

---

## 15. Remove Data Validation

To remove validation:

1. Select cells
2. Data → Data Validation
3. Click Clear All
4. Click OK

---

## 16. Find Invalid Data

Excel can identify values that do not follow validation rules.

Data → Data Validation → Circle Invalid Data

This helps identify existing incorrect entries.

---

## 17. Example: Employee Data

Columns:

Employee_ID
Employee_Name
Department
Age
Joining_Date
Salary

Validation rules:

Employee_ID:
Text/required format

Department:
Dropdown

Age:
18 to 60

Joining_Date:
Valid date

Salary:
Greater than 0

This improves data quality.

---

## 18. Example: Sales Data

Columns:

Order_ID
Customer
City
Product
Quantity
Sales
Order_Date

Validation:

City:
Hyderabad, Chennai, Bangalore, Pune

Quantity:
1 to 1000

Sales:
Greater than 0

Order_Date:
Valid date

This prevents many common data-entry errors.

---

## 19. Data Validation vs Conditional Formatting

Data Validation:

Controls what users can enter.

Conditional Formatting:

Changes the appearance of existing data based on conditions.

Remember:

Validation = Control Input

Conditional Formatting = Highlight Data

---

## 20. Data Validation vs Data Cleaning

Data Validation:

Prevents incorrect data from being entered.

Data Cleaning:

Fixes incorrect or messy data that already exists.

Remember:

Validation = Prevention

Cleaning = Correction

---

## 21. Data Analyst Example

Business requirement:

"Employees should select only valid departments."

Solution:

Create a Department dropdown.

Values:

IT
HR
Finance
Sales
Marketing

Why?

Without validation:

IT
It
I.T
Information Technology

With validation:

Only approved values are selected.

Result:

Consistent data.

---

## 22. Practical Exercise

Create an Employee table:

Employee_ID
Name
Department
Age
Salary

Create these validations:

1. Department → Dropdown
2. Age → 18 to 60
3. Salary → Greater than 0
4. Employee_ID → Maximum 10 characters
5. Add Input Message
6. Add Error Alert
7. Test invalid values

---

## 23. Practical Exercise 2

Create a Sales table:

Order_ID
Customer
City
Product
Quantity
Sales

Create:

City → Dropdown

Hyderabad
Chennai
Bangalore
Pune

Quantity:

1 to 100

Sales:

Greater than 0

Order_Date:

Valid date

Test both valid and invalid entries.

---

## 24. Interview Questions

### Q1. What is Data Validation?

Data Validation controls the type of data that can be entered into an Excel cell.

### Q2. Why is Data Validation important?

It reduces data-entry errors and improves data consistency.

### Q3. How do you create a dropdown?

Data → Data Validation → Allow: List

### Q4. What is the difference between Data Validation and Conditional Formatting?

Data Validation controls input.

Conditional Formatting highlights existing data.

### Q5. What is Custom Validation?

Custom Validation uses an Excel formula to define a specific input rule.

### Q6. What is an Error Alert?

It displays a message when invalid data is entered.

### Q7. What are the three Error Alert styles?

Stop, Warning, Information.

---

## 25. Data Analyst Thinking

When designing an Excel data-entry sheet, ask:

What data should users enter?

What values are valid?

What values are invalid?

Can I use a dropdown?

Can I restrict the range?

Can I prevent duplicates?

Can I standardize the input?

Think:

Prevent bad data before analysis.

---

## 26. Quick Cheat Sheet

Data Validation
= Control input

List
= Dropdown

Whole Number
= Integer restriction

Decimal
= Decimal restriction

Date
= Date restriction

Time
= Time restriction

Text Length
= Character restriction

Custom
= Formula-based validation

Input Message
= Tell user what to enter

Error Alert
= Warn/restrict invalid input

Stop
= Strict restriction

Warning
= User can confirm

Information
= Inform user

---

## 27. Important Excel Formulas

Positive number:

=A2>0

Greater than 100:

=A2>100

Age validation:

=AND(A2>=18,A2<=60)

Prevent duplicate:

=COUNTIF($A:$A,A2)=1

Required cell:

=A2<>""

---

## 28. Day 8 Practice Challenge

Create a professional Employee Data Entry sheet.

Columns:

Employee_ID
Employee_Name
Department
City
Age
Salary
Joining_Date

Apply:

Department → Dropdown

City → Dropdown

Age → 18 to 60

Salary → Greater than 0

Joining_Date → Valid date

Employee_ID → No duplicates

Add:

Input Messages

Error Alerts

Then test:

5 valid records

5 invalid records

Fix all invalid records.

---

## 29. Day 8 Checklist

[ ] Understand Data Validation
[ ] Create dropdown
[ ] Use List validation
[ ] Validate whole numbers
[ ] Validate decimals
[ ] Validate dates
[ ] Validate time
[ ] Validate text length
[ ] Use Custom validation
[ ] Create Input Message
[ ] Create Error Alert
[ ] Understand Stop
[ ] Understand Warning
[ ] Understand Information
[ ] Remove validation
[ ] Find invalid data
[ ] Practice business scenarios

---

## 30. Day 8 Key Memory

Data Validation = Control Input

List = Dropdown

Number = Restrict Range

Date = Restrict Dates

Custom = Formula Rule

Validation = Prevention

Cleaning = Correction

Remember:

PREVENT BAD DATA → GET BETTER ANALYSIS

---

## Day 8 Goal

By the end of Day 8, you should be able to create an Excel data-entry sheet that prevents invalid values and maintains consistent data.

# Excel Day 8 Completed
