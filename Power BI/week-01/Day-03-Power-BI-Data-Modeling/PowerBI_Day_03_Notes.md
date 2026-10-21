# Power BI Day 03 — Data Modeling

## 1. Day 3 Objective

Learn:

- What is Data Modeling?
- Tables in Power BI
- Relationships
- Primary Key
- Foreign Key
- One-to-Many relationship
- Fact and Dimension tables
- Star Schema
- Relationship direction
- Basic data model best practices

Remember:

Data → Model → Analyze → Visualize

---

## 2. What is Data Modeling?

Data Modeling means organizing tables and creating relationships between them so that Power BI can analyze the data correctly.

Example:

Customers
    ↓
Orders
    ↓
Products

The tables are connected using common columns.

---

## 3. Why Data Modeling is Important?

Good data modeling helps:

- Calculate correct results
- Avoid duplicate data
- Improve report performance
- Create accurate relationships
- Build better dashboards
- Write simpler DAX

Remember:

Good Model = Reliable Analysis

---

## 4. What is a Table?

A table contains:

- Rows
- Columns
- Data

Example:

Customers

Customer_ID | Customer_Name | City

101 | Indra | Hyderabad
102 | Rahul | Chennai
103 | Anil | Bangalore

---

## 5. Primary Key

A Primary Key uniquely identifies each record in a table.

Example:

Customer_ID

101
102
103

Each Customer_ID should be unique.

Remember:

Primary Key = Unique Identifier

---

## 6. Foreign Key

A Foreign Key connects one table to another table.

Example:

Customers:

Customer_ID

101
102
103

Orders:

Order_ID | Customer_ID

5001 | 101
5002 | 102
5003 | 101

Here:

Customers[Customer_ID]

is connected to:

Orders[Customer_ID]

Orders[Customer_ID] is the Foreign Key.

---

## 7. Relationship

A relationship connects two tables using a common column.

Example:

Customers
Customer_ID

↓

Orders
Customer_ID

Power BI uses relationships to combine information from different tables.

---

## 8. One-to-Many Relationship

Most common relationship in Power BI.

Example:

One Customer can have many Orders.

Customers:

Customer_ID
101
102
103

Orders:

Order_ID | Customer_ID
5001 | 101
5002 | 101
5003 | 102
5004 | 101

Relationship:

Customers (1) → Orders (*)

Remember:

1 = One

* = Many

---

## 9. One-to-One Relationship

One record in Table A matches one record in Table B.

Example:

Employee
Employee_ID

Employee_Profile
Employee_ID

1 → 1

This relationship is less common in typical reporting models.

---

## 10. Many-to-Many Relationship

Many records in Table A can relate to many records in Table B.

Example:

Students ↔ Courses

One student can take many courses.

One course can have many students.

This creates:

Many ↔ Many

Use carefully because it can create ambiguity and incorrect calculations if the model is not designed properly.

---

## 11. Fact Table

A Fact Table contains business transactions or measurable events.

Examples:

- Sales
- Orders
- Transactions
- Payments
- Bookings

Example:

Sales_Fact

Order_ID
Customer_ID
Product_ID
Date_ID
Quantity
Sales

Remember:

Fact = Business Events + Numbers

---

## 12. Dimension Table

A Dimension Table contains descriptive information.

Examples:

- Customer
- Product
- Date
- Employee
- Location

Example:

Customer_Dim

Customer_ID
Customer_Name
City
State
Age

Remember:

Dimension = Description

---

## 13. Fact vs Dimension

Fact Table:

- Transactions
- Measures
- Numeric values
- Many rows

Dimension Table:

- Descriptions
- Categories
- Attributes
- Usually fewer rows

Remember:

FACT = What happened?

DIMENSION = Who / What / Where / When?

---

## 14. Star Schema

Star Schema is a common Power BI data model design.

Example:

              Date
               |
               |
Customer → Sales ← Product
               |
               |
             Store

Sales = Fact Table

Customer, Product, Date, Store = Dimension Tables

It looks like a star.

---

## 15. Star Schema Structure

Fact Table:

Sales_Fact

Columns:

Order_ID
Customer_ID
Product_ID
Date_ID
Quantity
Sales

Dimension Tables:

Customer_Dim
Product_Dim
Date_Dim

Relationships:

Customer_Dim → Sales_Fact

Product_Dim → Sales_Fact

Date_Dim → Sales_Fact

---

## 16. Why Star Schema?

Benefits:

- Simple model
- Better performance
- Easier DAX
- Easier reporting
- Easier maintenance
- Clear relationships

Remember:

Star Schema = Fact in Center + Dimensions Around It

---

## 17. Relationship Cardinality

Cardinality defines how records relate.

Common types:

1. One-to-One
2. One-to-Many
3. Many-to-One
4. Many-to-Many

Most common in Power BI:

One-to-Many

---

## 18. Cross Filter Direction

Cross-filter direction controls how filtering moves between tables.

Common options:

Single

Both

Best practice:

Use Single direction when possible.

Avoid Both unless there is a clear business requirement.

---

## 19. Creating a Relationship

In Power BI:

Model View
→ Drag one matching column onto another

Example:

Customer_Dim[Customer_ID]

to:

Sales_Fact[Customer_ID]

Power BI creates the relationship.

---

## 20. Relationship Example

Customer Table:

Customer_ID | Customer_Name

101 | Indra
102 | Rahul
103 | Anil

Sales Table:

Order_ID | Customer_ID | Sales

5001 | 101 | 50000
5002 | 102 | 40000
5003 | 101 | 60000

Relationship:

Customer_Dim[Customer_ID]
        ↓
Sales_Fact[Customer_ID]

Cardinality:

One-to-Many

---

## 21. Date Dimension

A Date Table is very important for Power BI reporting.

Typical columns:

Date
Year
Month
Month Number
Quarter
Day
Week

Example:

Date
01-Jan-2026
02-Jan-2026
03-Jan-2026

Date table helps with:

- Year analysis
- Month analysis
- Quarter analysis
- Time intelligence
- Trend analysis

---

## 22. Example Data Model

Tables:

Customer
Product
Date
Sales

Relationships:

Customer[Customer_ID]
        ↓
Sales[Customer_ID]

Product[Product_ID]
        ↓
Sales[Product_ID]

Date[Date]
        ↓
Sales[Order_Date]

Model:

Customer
   |
Product → Sales ← Date

---

## 23. Data Model Best Practices

### Rule 1

Prefer Star Schema.

### Rule 2

Keep Fact and Dimension tables separate.

### Rule 3

Use unique keys in Dimension tables.

### Rule 4

Avoid unnecessary relationships.

### Rule 5

Avoid many-to-many unless required.

### Rule 6

Use clear table names.

### Rule 7

Use clear column names.

### Rule 8

Keep relationships simple.

---

## 24. Common Modeling Mistakes

Avoid:

- Duplicate keys in dimension tables
- Incorrect relationships
- Unnecessary many-to-many relationships
- Too many calculated columns
- Ambiguous relationships
- Poor naming
- Mixing unrelated tables
- Using Both filter direction unnecessarily

---

## 25. Data Analyst Example

Business requirement:

"Show total sales by customer and product."

Tables:

Customer_Dim

Customer_ID
Customer_Name
City

Product_Dim

Product_ID
Product_Name
Category

Sales_Fact

Order_ID
Customer_ID
Product_ID
Quantity
Sales

Relationships:

Customer_Dim → Sales_Fact

Product_Dim → Sales_Fact

Now Power BI can analyze:

Sales by Customer

Sales by Product

Sales by City

Sales by Category

---

## 26. Interview Questions

### Q1. What is Data Modeling?

Data Modeling is organizing tables and relationships so data can be analyzed correctly.

### Q2. What is a Primary Key?

A column that uniquely identifies each record.

### Q3. What is a Foreign Key?

A column used to connect one table with another table.

### Q4. What is a Fact Table?

A table containing business transactions and measurable values.

### Q5. What is a Dimension Table?

A table containing descriptive attributes used to analyze facts.

### Q6. What is a Star Schema?

A model where a central Fact Table connects to multiple Dimension Tables.

### Q7. What is the most common relationship?

One-to-Many.

### Q8. Why is Star Schema preferred?

It provides a simple, clear and efficient structure for reporting and analysis.

---

## 27. Data Analyst Thinking

When you receive multiple tables, ask:

1. What is the Fact Table?
2. What are the Dimension Tables?
3. What is the Primary Key?
4. What is the Foreign Key?
5. How are the tables connected?
6. Is the relationship one-to-many?
7. Is the model creating duplicate results?
8. Can I build a Star Schema?

Think:

Tables → Keys → Relationships → Model → Analysis

---

## 28. Day 3 Practice

Create these tables:

Customer_Dim

Customer_ID
Customer_Name
City

Product_Dim

Product_ID
Product_Name
Category

Sales_Fact

Order_ID
Customer_ID
Product_ID
Quantity
Sales

Create relationships:

Customer_Dim[Customer_ID]
→ Sales_Fact[Customer_ID]

Product_Dim[Product_ID]
→ Sales_Fact[Product_ID]

Then check:

1. Relationship type
2. Cardinality
3. Filter direction
4. Duplicate keys
5. Model structure

---

## 29. Quick Cheat Sheet

Primary Key
= Unique ID

Foreign Key
= Connection ID

Fact
= Transactions + Numbers

Dimension
= Descriptions

1
= One

*
= Many

One-to-Many
= Most common relationship

Star Schema
= Fact + Dimensions

Model View
= Create/manage relationships

Single Direction
= Preferred when possible

---

## 30. Day 3 Key Memory

Primary Key = Unique

Foreign Key = Connect

Fact = What happened?

Dimension = Who / What / Where / When?

1 → * = One-to-Many

Star Schema = Fact in Center

Good Model = Accurate Analysis

---

## Day 3 Checklist

[ ] Understand Data Modeling
[ ] Understand Tables
[ ] Understand Primary Key
[ ] Understand Foreign Key
[ ] Understand Relationships
[ ] Understand One-to-Many
[ ] Understand One-to-One
[ ] Understand Many-to-Many
[ ] Understand Fact Tables
[ ] Understand Dimension Tables
[ ] Understand Star Schema
[ ] Understand Cardinality
[ ] Understand Cross Filter Direction
[ ] Create Relationships
[ ] Understand Date Dimension
[ ] Practice Data Modeling
[ ] Learn Modeling Best Practices

---

## Day 3 Goal

By the end of Day 3, you should be able to:

Identify Fact and Dimension tables → Find Primary and Foreign Keys → Create relationships → Build a basic Star Schema → Prepare a Power BI model for analysis.

# Power BI Day 3 Completed
