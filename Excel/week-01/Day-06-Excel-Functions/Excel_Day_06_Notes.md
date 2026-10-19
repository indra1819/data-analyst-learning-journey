# Excel Day 06 – Lookup Functions

## 1. What are Lookup Functions?

Lookup functions are used to search for a value in a dataset and return related information.

Common lookup functions:

- VLOOKUP
- XLOOKUP
- HLOOKUP
- INDEX
- MATCH
- INDEX + MATCH

---

## 2. VLOOKUP

VLOOKUP means Vertical Lookup.

It searches for a value in the first column of a table and returns a value from another column.

### Syntax

=VLOOKUP(lookup_value, table_array, col_index_num, FALSE)

### Example

| ID | Name | Salary |
|---|---|---:|
| 101 | Ravi | 40000 |
| 102 | Arun | 35000 |
| 103 | Sita | 50000 |

Find salary for ID 102:

=VLOOKUP(102,A2:C4,3,FALSE)

Result:

35000

---

## 3. VLOOKUP Arguments

Example:

=VLOOKUP(102,A2:C4,3,FALSE)

102
→ Lookup value

A2:C4
→ Table range

3
→ Column number to return

FALSE
→ Exact match

---

## 4. Exact Match vs Approximate Match

### FALSE

Used for exact matching.

Example:

=VLOOKUP(A2,E2:G10,3,FALSE)

Commonly used for:

- Employee ID
- Customer ID
- Product ID
- Order ID

### TRUE

Used for approximate matching.

Useful for:

- Salary slabs
- Commission slabs
- Grade ranges
- Tax ranges

---

## 5. VLOOKUP Limitation

VLOOKUP normally searches from:

LEFT → RIGHT

Example:

| ID | Name | Salary |
|---|---|---:|
| 101 | Ravi | 40000 |
| 102 | Arun | 35000 |
| 103 | Sita | 50000 |

We can search ID and return Name or Salary.

But we cannot normally search Salary and return ID because ID is on the left.

---

## 6. XLOOKUP

XLOOKUP is a modern and flexible lookup function.

### Syntax

=XLOOKUP(lookup_value, lookup_array, return_array)

### Example

=XLOOKUP(102,A2:A4,C2:C4)

Result:

35000

---

## 7. XLOOKUP Advantages

XLOOKUP can:

- Search left
- Search right
- Return exact matches
- Handle missing values
- Work without column numbers
- Use separate lookup and return ranges

---

## 8. XLOOKUP Not Found

We can specify what should appear when a value is not found.

### Example

=XLOOKUP(105,A2:A4,C2:C4,"Not Found")

Result:

Not Found

---

## 9. VLOOKUP vs XLOOKUP

| Feature | VLOOKUP | XLOOKUP |
|---|---|---|
| Vertical lookup | Yes | Yes |
| Exact match | Yes | Yes |
| Left lookup | No | Yes |
| Column number required | Yes | No |
| Custom Not Found | Limited | Yes |
| Flexibility | Less | More |

### Interview Point

VLOOKUP → Traditional vertical lookup

XLOOKUP → Modern flexible lookup

---

## 10. HLOOKUP

HLOOKUP means Horizontal Lookup.

It is used when data is arranged horizontally.

### Example

| ID | 101 | 102 | 103 |
|---|---|---|---|
| Name | Ravi | Arun | Sita |
| Salary | 40000 | 35000 | 50000 |

Formula:

=HLOOKUP(102,A1:D3,3,FALSE)

Result:

35000

---

## 11. MATCH

MATCH finds the position of a value in a range.

### Example

| Name |
|---|
| Ravi |
| Arun |
| Sita |

Formula:

=MATCH("Arun",A2:A4,0)

Result:

2

Because Arun is in the second position.

### Syntax

=MATCH(lookup_value, lookup_array, 0)

0 means exact match.

---

## 12. INDEX

INDEX returns a value from a specific position.

### Example

| Name | Salary |
|---|---:|
| Ravi | 40000 |
| Arun | 35000 |
| Sita | 50000 |

Formula:

=INDEX(B2:B4,2)

Result:

35000

---

## 13. INDEX + MATCH

INDEX + MATCH is a powerful lookup combination.

### Formula

=INDEX(C2:C4,MATCH(102,A2:A4,0))

### How it works

MATCH
→ Finds the position of 102.

INDEX
→ Returns the value from that position.

Result:

35000

---

## 14. Why INDEX + MATCH?

Advantages:

- Flexible lookup
- Can lookup left or right
- Does not require a fixed column number
- Useful with changing datasets
- Important for interviews

---

## 15. IFERROR with Lookup

If a lookup value does not exist, Excel may return:

#N/A

We can handle this using IFERROR.

### Example

=IFERROR(VLOOKUP("P999",A2:D6,4,FALSE),"Not Found")

Result:

Not Found

---

## 16. Data Analyst Example

### Customer Data

| Customer_ID | Customer | City | Sales |
|---|---|---|---:|
| C101 | Ravi | Hyderabad | 50000 |
| C102 | Arun | Chennai | 35000 |
| C103 | Sita | Bangalore | 60000 |

Find sales for C103.

### Using VLOOKUP

=VLOOKUP("C103",A2:D4,4,FALSE)

Result:

60000

### Using XLOOKUP

=XLOOKUP("C103",A2:A4,D2:D4)

Result:

60000

### Using INDEX + MATCH

=INDEX(D2:D4,MATCH("C103",A2:A4,0))

Result:

60000

---

## 17. Product Lookup Example

| Product_ID | Product | Category | Price |
|---|---|---|---:|
| P101 | Laptop | Electronics | 55000 |
| P102 | Mouse | Accessories | 1000 |
| P103 | Keyboard | Accessories | 2000 |
| P104 | Monitor | Electronics | 15000 |
| P105 | Headphones | Accessories | 3000 |

### Find P103 Price

VLOOKUP:

=VLOOKUP("P103",A2:D6,4,FALSE)

Result:

2000

XLOOKUP:

=XLOOKUP("P103",A2:A6,D2:D6)

Result:

2000

INDEX + MATCH:

=INDEX(D2:D6,MATCH("P103",A2:A6,0))

Result:

2000

---

## 18. Common Data Analyst Uses

Lookup functions are useful for:

- Customer information
- Employee details
- Product prices
- Product categories
- Order details
- Sales information
- ID mapping
- Data validation
- Combining information from different tables

---

## 19. Interview Stick Notes

### VLOOKUP

Vertical lookup.

=VLOOKUP(value,table,column,FALSE)

### XLOOKUP

Modern flexible lookup.

=XLOOKUP(value,lookup_array,return_array)

### HLOOKUP

Horizontal lookup.

=HLOOKUP(value,table,row,FALSE)

### MATCH

Finds position.

=MATCH(value,range,0)

### INDEX

Returns value by position.

=INDEX(range,position)

### INDEX + MATCH

Flexible lookup.

=INDEX(return_range,MATCH(value,lookup_range,0))

### IFERROR

Handles errors.

=IFERROR(formula,"Not Found")

---

## 20. Practice Questions

Use this dataset:

| Product_ID | Product | Category | Price |
|---|---|---|---:|
| P101 | Laptop | Electronics | 55000 |
| P102 | Mouse | Accessories | 1000 |
| P103 | Keyboard | Accessories | 2000 |
| P104 | Monitor | Electronics | 15000 |
| P105 | Headphones | Accessories | 3000 |

Practice:

1. Find P103 price using VLOOKUP.

2. Find P104 category using XLOOKUP.

3. Find P105 product name using XLOOKUP.

4. Search P999 and return "Not Found".

5. Find P103 position using MATCH.

6. Return P103 price using INDEX.

7. Find P104 price using INDEX + MATCH.

8. Use IFERROR with VLOOKUP.

---

## 21. Quick Comparison

VLOOKUP
→ Vertical lookup

XLOOKUP
→ Modern flexible lookup

HLOOKUP
→ Horizontal lookup

MATCH
→ Finds position

INDEX
→ Returns value

INDEX + MATCH
→ Advanced flexible lookup

IFERROR
→ Handles errors

---

# DAY 06 COMPLETE

Topics Completed:

✓ VLOOKUP
✓ XLOOKUP
✓ HLOOKUP
✓ INDEX
✓ MATCH
✓ INDEX + MATCH
✓ IFERROR
✓ Exact Match
✓ Approximate Match
✓ Lookup Errors
✓ Data Analyst Lookup Scenarios
✓ Practice Questions
