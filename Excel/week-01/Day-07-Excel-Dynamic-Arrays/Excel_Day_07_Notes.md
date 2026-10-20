# Day 7 — Excel Revision & Data Analyst Practice

## Objective

Revise the important Excel concepts learned in Week 1 and apply them to Data Analyst-style problems.

---

## 1. Excel Fundamentals

### Excel Table

Shortcut:

Ctrl + T

Benefits:
- Automatic filtering
- Automatic expansion
- Structured references
- Easier data analysis

### Cell References

Relative Reference:

=A2*B2

Changes when copied.

Absolute Reference:

=A2*$F$1

$F$1 remains fixed.

Mixed Reference:

=$A2
=A$2

One part remains fixed.

---

## 2. Data Cleaning

Common Excel data-cleaning tasks:

- Remove duplicates
- Find & Replace
- Remove blank rows
- Correct data types
- Remove extra spaces
- Standardize text
- Handle missing values
- Sort data
- Filter data

### TRIM

=TRIM(A2)

Removes extra spaces.

### CLEAN

=CLEAN(A2)

Removes non-printing characters.

---

## 3. Basic Functions

### SUM

=SUM(B2:B100)

Use: Calculate total.

### AVERAGE

=AVERAGE(B2:B100)

Use: Calculate average.

### COUNT

=COUNT(B2:B100)

Use: Count numeric values.

### COUNTA

=COUNTA(A2:A100)

Use: Count non-empty cells.

### MIN

=MIN(B2:B100)

Use: Find minimum value.

### MAX

=MAX(B2:B100)

Use: Find maximum value.

---

## 4. Logical Functions

### IF

=IF(B2>=50000,"High","Low")

Use: Apply a condition.

### AND

=AND(B2>=50000,C2="Yes")

Use: All conditions must be TRUE.

### OR

=OR(B2>=50000,C2="Yes")

Use: At least one condition must be TRUE.

---

## 5. Conditional Functions

### SUMIF

=SUMIF(A2:A100,"Hyderabad",B2:B100)

Use: Sum values based on one condition.

### SUMIFS

=SUMIFS(D2:D100,A2:A100,"Hyderabad",B2:B100,">50000")

Use: Sum values based on multiple conditions.

### COUNTIF

=COUNTIF(A2:A100,"Hyderabad")

Use: Count based on one condition.

### COUNTIFS

=COUNTIFS(A2:A100,"Hyderabad",B2:B100,">50000")

Use: Count based on multiple conditions.

### AVERAGEIF

=AVERAGEIF(A2:A100,"Hyderabad",B2:B100)

Use: Average based on one condition.

### AVERAGEIFS

=AVERAGEIFS(D2:D100,A2:A100,"Hyderabad",B2:B100,">50000")

Use: Average based on multiple conditions.

---

## 6. Lookup Functions

### VLOOKUP

=VLOOKUP(A2,F2:H100,3,FALSE)

Use: Find a value from a lookup table.

Important:
- A2 → Lookup value
- F2:H100 → Lookup table
- 3 → Return column
- FALSE → Exact match

### XLOOKUP

=XLOOKUP(A2,F2:F100,H2:H100,"Not Found")

Advantages:
- Can search left or right
- Exact match by default
- Can return custom message
- More flexible than VLOOKUP

### INDEX + MATCH

=INDEX(H2:H100,MATCH(A2,F2:F100,0))

Use: Flexible lookup combination.

---

## 7. Dynamic Array Functions

### FILTER

=FILTER(A2:D100,C2:C100="Hyderabad")

Returns records matching a condition.

### SORT

=SORT(A2:D100,4,-1)

Sorts data dynamically.

### SORTBY

=SORTBY(A2:D100,D2:D100,-1)

Sorts one range based on another range.

### UNIQUE

=UNIQUE(C2:C100)

Returns unique values.

### SEQUENCE

=SEQUENCE(10)

Creates numbers from 1 to 10.

---

# 8. Data Analyst Practice Dataset

Assume the dataset contains:

Order_ID | Customer | City | Product | Sales | Quantity

101 | Ravi | Hyderabad | Laptop | 60000 | 1
102 | Priya | Bangalore | Mouse | 2000 | 2
103 | Arun | Hyderabad | Keyboard | 5000 | 3
104 | Sneha | Chennai | Laptop | 70000 | 1
105 | Kiran | Hyderabad | Monitor | 25000 | 2

---

## 9. Practice Questions

### Task 1 — Total Sales

=SUM(E2:E6)

### Task 2 — Average Sales

=AVERAGE(E2:E6)

### Task 3 — Highest Sales

=MAX(E2:E6)

### Task 4 — Lowest Sales

=MIN(E2:E6)

### Task 5 — Number of Orders

=COUNT(A2:A6)

### Task 6 — Hyderabad Sales

=SUMIF(C2:C6,"Hyderabad",E2:E6)

### Task 7 — Hyderabad Orders

=COUNTIF(C2:C6,"Hyderabad")

### Task 8 — Orders Above ₹25,000

=COUNTIF(E2:E6,">25000")

### Task 9 — Sales Category

=IF(E2>=50000,"High","Low")

### Task 10 — Hyderabad Orders Above ₹20,000

=COUNTIFS(C2:C6,"Hyderabad",E2:E6,">20000")

---

# 10. Business Scenarios

## Scenario 1 — Highest Sales City

Requirement:

Find which city generated the highest sales.

Approach:

1. Group sales by city.
2. Calculate total sales.
3. Compare cities.
4. Identify the highest-performing city.

---

## Scenario 2 — Premium Customers

Requirement:

Customers with Sales >= ₹50,000 are Premium.

Formula:

=IF(E2>=50000,"Premium","Regular")

Count Premium customers:

=COUNTIF(G2:G100,"Premium")

---

## Scenario 3 — High-Value Orders

Requirement:

Find orders where Sales > ₹50,000.

Formula:

=FILTER(A2:F100,E2:E100>50000)

---

## Scenario 4 — Hyderabad High-Value Orders

Formula:

=FILTER(A2:F100,(C2:C100="Hyderabad")*(E2:E100>20000))

---

# 11. Interview Questions

### Q1. What is the difference between COUNT and COUNTA?

COUNT counts numeric values.

COUNTA counts all non-empty values.

### Q2. What is the difference between SUMIF and SUMIFS?

SUMIF uses one condition.

SUMIFS uses multiple conditions.

### Q3. What is the difference between VLOOKUP and XLOOKUP?

VLOOKUP searches vertically and normally requires the lookup column to be on the left.

XLOOKUP is more flexible and can search in either direction.

### Q4. What is an absolute reference?

An absolute reference remains fixed when a formula is copied.

Example:

=$A$1

### Q5. What is FILTER used for?

FILTER returns only the records that satisfy a condition.

### Q6. Why are Excel Tables useful?

Tables make filtering, sorting, formulas and data expansion easier.

---

# 12. Data Analyst Thinking

Always follow:

Requirement → Data → Formula → Result → Business Insight

Example:

Requirement:
Which city has the highest sales?

Data:
City + Sales

Method:
SUMIF / Pivot Table

Result:
Highest-sales city

Insight:
Focus more business activity on the highest-performing city.

---

# 13. Day 7 Practice Challenge

Using a real-world sales dataset:

1. Find total sales.
2. Find average sales.
3. Find maximum sales.
4. Find minimum sales.
5. Count total orders.
6. Find total sales by city.
7. Count orders by city.
8. Find orders above ₹50,000.
9. Create High/Low sales categories.
10. Create Premium/Regular customer categories.
11. Use XLOOKUP to retrieve customer information.
12. Use FILTER to return high-value orders.
13. Use UNIQUE to find unique cities.
14. Sort customers by sales.
15. Answer one business question using Excel.

---

# 14. Week 1 Quick Revision

Excel Tables
→ Data Cleaning
→ Cell References
→ Basic Functions
→ Logical Functions
→ Conditional Functions
→ Lookup Functions
→ Dynamic Array Functions
→ Business Analysis

---

# 15. Important Formula Cheat Sheet

SUM:
=SUM(B2:B100)

AVERAGE:
=AVERAGE(B2:B100)

COUNT:
=COUNT(B2:B100)

COUNTA:
=COUNTA(A2:A100)

MIN:
=MIN(B2:B100)

MAX:
=MAX(B2:B100)

IF:
=IF(B2>=50000,"High","Low")

AND:
=AND(B2>=50000,C2="Yes")

OR:
=OR(B2>=50000,C2="Yes")

SUMIF:
=SUMIF(A2:A100,"Hyderabad",B2:B100)

SUMIFS:
=SUMIFS(D2:D100,A2:A100,"Hyderabad",B2:B100,">50000")

COUNTIF:
=COUNTIF(A2:A100,"Hyderabad")

COUNTIFS:
=COUNTIFS(A2:A100,"Hyderabad",B2:B100,">50000")

VLOOKUP:
=VLOOKUP(A2,F2:H100,3,FALSE)

XLOOKUP:
=XLOOKUP(A2,F2:F100,H2:H100,"Not Found")

INDEX + MATCH:
=INDEX(H2:H100,MATCH(A2,F2:F100,0))

FILTER:
=FILTER(A2:D100,C2:C100="Hyderabad")

SORT:
=SORT(A2:D100,4,-1)

SORTBY:
=SORTBY(A2:D100,D2:D100,-1)

UNIQUE:
=UNIQUE(C2:C100)

SEQUENCE:
=SEQUENCE(10)

---

# Day 7 Checklist

- [ ] Excel Tables
- [ ] Cell References
- [ ] Data Cleaning
- [ ] SUM
- [ ] AVERAGE
- [ ] COUNT
- [ ] COUNTA
- [ ] MIN
- [ ] MAX
- [ ] IF
- [ ] AND
- [ ] OR
- [ ] SUMIF
- [ ] SUMIFS
- [ ] COUNTIF
- [ ] COUNTIFS
- [ ] AVERAGEIF
- [ ] AVERAGEIFS
- [ ] VLOOKUP
- [ ] XLOOKUP
- [ ] INDEX + MATCH
- [ ] FILTER
- [ ] SORT
- [ ] SORTBY
- [ ] UNIQUE
- [ ] SEQUENCE
- [ ] Business Scenarios
- [ ] Interview Questions

---

# Day 7 Goal

By the end of Day 7, I should be able to:

- Clean basic Excel data.
- Use important Excel formulas.
- Perform conditional analysis.
- Perform lookups.
- Filter and sort data.
- Solve basic Data Analyst business problems.
- Explain Excel concepts confidently in interviews.

---

# Week 1 Completed — Excel Foundation
