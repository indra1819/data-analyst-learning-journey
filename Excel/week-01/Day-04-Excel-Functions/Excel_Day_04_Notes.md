# Excel Day 04 – Conditional & Lookup Functions

## Topics Completed

1. COUNTIF
2. COUNTIFS
3. SUMIF
4. SUMIFS
5. AVERAGEIF
6. AVERAGEIFS
7. VLOOKUP
8. XLOOKUP
9. INDEX + MATCH

---

## 1. COUNTIF

Counts cells that satisfy a single condition.

### Syntax
=COUNTIF(range, criteria)

### Example
=COUNTIF(staff[department],"Engineering")

### Use
Find the number of employees in a particular department.

---

## 2. COUNTIFS

Counts rows based on multiple conditions.

### Syntax
=COUNTIFS(range1, criteria1, range2, criteria2)

### Example
=COUNTIFS(staff[department],"Engineering",staff[employee type],"Permanent")

### Use
Find permanent employees working in Engineering.

---

## 3. SUMIF

Adds values based on a single condition.

### Syntax
=SUMIF(criteria_range, criteria, sum_range)

### Example
=SUMIF(staff[department],"Engineering",staff[salary])

### Use
Calculate total salary paid to Engineering employees.

---

## 4. SUMIFS

Adds values based on multiple conditions.

### Syntax
=SUMIFS(sum_range, criteria_range1, criteria1, criteria_range2, criteria2)

### Example
=SUMIFS(staff[salary],staff[department],"Engineering",staff[employee type],"Permanent")

### Use
Calculate total salary of permanent Engineering employees.

---

## 5. AVERAGEIF

Calculates the average based on one condition.

### Syntax
=AVERAGEIF(criteria_range, criteria, average_range)

### Example
=AVERAGEIF(staff[department],"Engineering",staff[salary])

### Use
Find the average salary of Engineering employees.

---

## 6. AVERAGEIFS

Calculates the average based on multiple conditions.

### Syntax
=AVERAGEIFS(average_range, criteria_range1, criteria1, criteria_range2, criteria2)

### Example
=AVERAGEIFS(staff[salary],staff[department],"Engineering",staff[employee type],"Permanent")

### Use
Find the average salary of permanent Engineering employees.

---

# Lookup Functions

## 7. VLOOKUP

Searches for a value vertically and returns a related value from another column.

### Syntax
=VLOOKUP(lookup_value, table, column_index, FALSE)

### Example
=VLOOKUP("Arun",staff,4,FALSE)

### Use
Find Arun's salary from the staff table.

### Important
VLOOKUP searches from the first column of the selected table and returns a value from a column to the right.

---

## 8. XLOOKUP

Modern lookup function used to search for a value and return a corresponding value.

### Syntax
=XLOOKUP(lookup_value, lookup_array, return_array)

### Example
=XLOOKUP("Arun",staff[employee],staff[salary])

### Use
Find an employee's salary using the employee name.

### Advantage
XLOOKUP is more flexible than VLOOKUP because the lookup and return columns can be independent.

---

## 9. INDEX + MATCH

Combination used for flexible lookups.

### Syntax
=INDEX(return_range,MATCH(lookup_value,lookup_range,0))

### Example
=INDEX(staff[salary],MATCH("Arun",staff[employee],0))

### Use
Find Arun's salary using INDEX and MATCH.

---

# Data Analyst Practical Applications

These functions are commonly used for:

- Employee analysis
- Sales analysis
- Customer analysis
- Department-wise reporting
- Conditional calculations
- KPI preparation
- Data validation
- Finding related information
- Business reporting
- Dashboard preparation

---

# Key Difference

| Function | Purpose |
|---|---|
| COUNTIF | Count with 1 condition |
| COUNTIFS | Count with multiple conditions |
| SUMIF | Sum with 1 condition |
| SUMIFS | Sum with multiple conditions |
| AVERAGEIF | Average with 1 condition |
| AVERAGEIFS | Average with multiple conditions |
| VLOOKUP | Vertical lookup |
| XLOOKUP | Flexible lookup |
| INDEX + MATCH | Flexible lookup combination |

---

# Data Analyst Thinking

When a business question asks:

**"How many?"** → COUNTIF / COUNTIFS

**"How much total?"** → SUMIF / SUMIFS

**"What is the average?"** → AVERAGEIF / AVERAGEIFS

**"Find information related to this ID/name."** → XLOOKUP / VLOOKUP

**"Need a flexible lookup."** → XLOOKUP or INDEX + MATCH

---

## Status

Excel Day 04 – Conditional & Lookup Functions Completed ✅
