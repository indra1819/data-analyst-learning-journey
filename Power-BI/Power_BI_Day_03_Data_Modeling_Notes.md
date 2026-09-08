# Power BI Day 03 – Data Modeling

## 1. What is Data Modeling?

Data modeling is the process of connecting and organizing tables so that Power BI can analyze data correctly.

A good data model helps:

- Create accurate reports
- Improve performance
- Build reliable DAX measures
- Filter data correctly
- Analyze data across multiple tables

---

# 2. Tables in Power BI

A Power BI model can contain multiple tables.

Example:

### Sales Table

| Order_ID | Product_ID | Customer_ID | Sales | Quantity |
|---|---|---|---:|---:|
| 1001 | P01 | C01 | 50000 | 2 |
| 1002 | P02 | C02 | 30000 | 1 |
| 1003 | P01 | C03 | 45000 | 3 |

### Product Table

| Product_ID | Product | Category |
|---|---|---|
| P01 | Laptop | Electronics |
| P02 | Chair | Furniture |

### Customer Table

| Customer_ID | Customer_Name | Region |
|---|---|---|
| C01 | Ravi | Hyderabad |
| C02 | Priya | Vijayawada |
| C03 | Arun | Chennai |

---

# 3. Relationships

Relationships connect tables using common columns.

Example:

```text
Sales[Product_ID]
        ↓
Product[Product_ID]
4. Primary Key
A primary key uniquely identifies each record in a table.
Example:
Product_ID
P01
P02
P03
Each Product_ID should be unique in the Product table.
5. Foreign Key
A foreign key is a column that references a key in another table.
Example:
Sales Table

Product_ID
P01
P02
P01
Here Product_ID can act as a foreign key because it connects Sales with the Product table.
6. Cardinality
Cardinality defines how records in two tables are related.
Common relationship types:
- One-to-One
- One-to-Many
- Many-to-One
- Many-to-Many
7. One-to-Many Relationship
One of the most common relationships in Power BI.
Example:
Product Table          Sales Table

P01 ────────────────→ P01
P02 ────────────────→ P02
P03 ────────────────→ P03
                      P01
                      P02
                      P01
One product can have many sales records.
This is:
Product (1) → Sales (*)
8. Many-to-One Relationship
The same relationship can be viewed from the opposite direction:
Sales (*) → Product (1)
Many sales records can belong to one product.
9. Many-to-Many Relationship
Many-to-many occurs when multiple records on both sides can match.
Example:
Students ↔ Courses
A student can take many courses.
A course can have many students.
Many-to-many relationships should be used carefully because they can create ambiguity.
10. Relationship Direction
Cross-filter direction controls how filters move between tables.
Common options:
- Single
- Both
Single Direction
Filters generally flow from the dimension/lookup table toward the fact table.
Example:
Product → Sales
Both Directions
Filters can flow in both directions.
Product ↔ Sales
Use bidirectional filtering only when it is actually required.
11. Star Schema
A star schema is a common and recommended approach for Power BI data modeling.
It contains:
- Fact table
- Dimension tables
Example:
                Product
                   |
                   |
Customer ─────── Sales ─────── Date
                   |
                   |
                Region
The central table is the fact table.
12. Fact Table
A fact table contains measurable business events.
Example:
Sales
Orders
Transactions
Payments
Typical columns:
Order_ID
Product_ID
Customer_ID
Date_ID
Quantity
Sales
Cost
Profit
13. Dimension Table
Dimension tables contain descriptive information.
Examples:
Product
Customer
Date
Region
Employee
Category
They provide context for analyzing the fact table.
14. Fact vs Dimension
Fact Table	Dimension Table
Stores business events	Stores descriptive information
Usually contains many rows	Usually contains fewer rows
Contains numeric measures	Contains descriptive attributes
Example: Sales	Example: Product
Example: Orders	Example: Customer


15. Date Table
A Date table is important for time-based analysis.
Typical columns:
Date
Year
Quarter
Month
Month Number
Month Name
Day
Example:
Date	Year	Month	Month Number
2026-01-01	2026	January	1
2026-02-01	2026	February	2
2026-03-01	2026	March	3


16. Why Use a Date Table?
A Date table helps analyze:
- Daily sales
- Monthly sales
- Quarterly sales
- Yearly sales
- Year-over-year performance
- Time-based trends
17. Creating a Simple Date Table
DAX can be used to create a Date table.
DateTable =
CALENDAR(
    DATE(2026,1,1),
    DATE(2026,12,31)
)
Additional columns can then be created for:
- Year
- Month
- Quarter
- Month Number
18. Measures
Measures are calculations created using DAX.
Example:
Total Sales = SUM(Sales[Sales])
Another example:
Total Profit =
SUM(Sales[Sales]) - SUM(Sales[Cost])
Measures dynamically respond to filters and slicers.
19. Calculated Column vs Measure
Calculated Column	Measure
Calculated row by row	Calculated when used in a visual
Stored in the model	Calculation is evaluated dynamically
Useful for categories/attributes	Useful for KPIs and aggregations
Increases model size	Usually more efficient for aggregations


20. Example Data Model
A simple e-commerce model can look like:
                 DimProduct
                     |
                     |
DimCustomer ───── FactSales ───── DimDate
                     |
                     |
                 DimRegion
FactSales
Order_ID
Product_ID
Customer_ID
Date_ID
Quantity
Sales
Cost
DimProduct
Product_ID
Product_Name
Category
DimCustomer
Customer_ID
Customer_Name
Region
DimDate
Date_ID
Date
Year
Month
Quarter
21. Benefits of a Good Data Model
A good data model provides:
- Accurate calculations
- Better filtering
- Better report performance
- Easier DAX development
- Cleaner report structure
- Better scalability
- Easier maintenance
22. Common Data Modeling Mistakes
Avoid:
- Unnecessary duplicate tables
- Incorrect relationships
- Ambiguous relationships
- Too many bidirectional relationships
- Incorrect data types
- Missing Date table
- Many-to-many relationships without understanding their impact
- Mixing unrelated tables
23. Practical Data Analyst Workflow
A typical Power BI workflow is:
Import Data
     ↓
Clean Data
     ↓
Identify Fact & Dimension Tables
     ↓
Create Relationships
     ↓
Build Data Model
     ↓
Create Measures
     ↓
Create Visuals
     ↓
Add Slicers & Filters
     ↓
Analyze Insights
24. Key Interview Points
- Data modeling connects and organizes tables for analysis.
- Relationships connect tables using common columns.
- Primary keys uniquely identify records.
- Foreign keys connect records to another table.
- One-to-many is one of the most common Power BI relationships.
- Star schema is commonly used for Power BI models.
- Fact tables contain business events and measurements.
- Dimension tables contain descriptive attributes.
- Date tables are important for time intelligence.
- Measures are dynamic DAX calculations.
- Avoid unnecessary bidirectional relationships.
- A good data model improves accuracy, performance, and maintainability.
Day 03 Summary
Today I learned:
Data Modeling
Tables
Relationships
Primary Key
Foreign Key
Cardinality
One-to-Many
Many-to-One
Many-to-Many
Cross-Filter Direction
Star Schema
Fact Tables
Dimension Tables
Date Tables
Measures
Calculated Columns
Data Modeling Best Practices
