# Day 01 - Power BI Fundamentals

## 🎯 Goal

Learn the basic Power BI concepts required for a Data Analyst.

---

# 1. What is Power BI?

Power BI is a Business Intelligence and Data Visualization tool developed by Microsoft.

It is mainly used to:

- Connect to data
- Clean data
- Transform data
- Analyze data
- Create dashboards
- Create reports
- Share business insights

---

# 2. Why Power BI is Used by Data Analysts

A Data Analyst uses Power BI to:

- Analyze sales
- Track KPIs
- Find trends
- Compare performance
- Create interactive dashboards
- Present insights to business teams

---

# 3. Main Power BI Components

Power BI mainly includes:

1. Power BI Desktop
2. Power BI Service
3. Power BI Mobile
4. Power BI Report Server

---

# 4. Power BI Desktop

Power BI Desktop is used to build reports and dashboards.

Main tasks:

- Import data
- Clean data
- Transform data
- Create relationships
- Create DAX measures
- Create visualizations
- Build reports

---

# 5. Power BI Service

Power BI Service is the online platform.

It is used to:

- Publish reports
- Share reports
- Create dashboards
- Collaborate with teams
- Manage workspaces
- Schedule data refresh

---

# 6. Power BI Mobile

Power BI Mobile allows users to view reports and dashboards on mobile devices.

---

# 7. Power BI Basic Workflow

Typical Power BI workflow:

Data Source
↓
Get Data
↓
Power Query
↓
Data Cleaning
↓
Data Modeling
↓
DAX
↓
Visualizations
↓
Report
↓
Publish
↓
Power BI Service

---

# 8. Get Data

Power BI can connect to many data sources.

Examples:

- Excel
- CSV
- SQL Server
- MySQL
- PostgreSQL
- Oracle
- Web
- SharePoint
- APIs

Example:

Excel File
→ Power BI
→ Transform Data
→ Create Report

---

# 9. Import Data

To import data:

Home
→ Get Data
→ Select Data Source
→ Select File
→ Load

Example:

Home
→ Get Data
→ Excel
→ Select File
→ Select Sheet
→ Load

---

# 10. Load vs Transform Data

Load:

Loads the data directly into Power BI.

Transform Data:

Opens Power Query Editor for cleaning and transformation.

For Data Analysts:

Prefer:

Get Data
→ Transform Data
→ Clean Data
→ Close & Apply

---

# 11. Power Query

Power Query is used for data cleaning and transformation.

Common operations:

- Remove duplicates
- Remove null values
- Change data types
- Rename columns
- Split columns
- Merge columns
- Replace values
- Filter rows
- Remove columns
- Add custom columns

---

# 12. Data Cleaning Example

Suppose the data contains:

Customer Name
Age
City
Sales
Category

Problems:

- Missing values
- Duplicate rows
- Incorrect data types
- Extra spaces
- Incorrect values

Power Query can be used to clean these problems.

---

# 13. Power Query Example

Example:

Sales column contains:

1000
2000
3000
null
4000

We can replace or remove null values depending on the business requirement.

---

# 14. Power BI Data Types

Common data types:

- Text
- Whole Number
- Decimal Number
- Date
- Date/Time
- True/False
- Percentage

Correct data types are important for accurate analysis.

---

# 15. Power BI Report

A report contains one or more report pages.

A report can contain:

- Charts
- Tables
- Cards
- Slicers
- KPIs
- Maps
- Filters

---

# 16. Power BI Dashboard

A dashboard is a single-page view of important business information.

It usually contains important:

- KPIs
- Charts
- Business metrics
- Trends
- Performance indicators

---

# 17. Report vs Dashboard

Report:

- Can have multiple pages
- Detailed analysis
- More visualizations
- Built mainly in Power BI Desktop

Dashboard:

- Single page
- High-level overview
- Mainly available in Power BI Service

---

# 18. Visualizations

Common Power BI visuals:

- Bar Chart
- Column Chart
- Line Chart
- Pie Chart
- Donut Chart
- Area Chart
- Table
- Matrix
- Card
- KPI
- Map
- Slicer

---

# 19. Bar Chart

Used to compare categories.

Example:

Category | Sales

Electronics | 50000
Clothing | 35000
Furniture | 25000

Bar chart helps compare sales between categories.

---

# 20. Line Chart

Used to analyze trends over time.

Example:

Month | Sales

January | 10000
February | 15000
March | 18000
April | 22000

Line chart helps identify whether sales are increasing or decreasing.

---

# 21. Pie Chart

Used to show contribution or proportion.

Example:

Category
Electronics
Clothing
Furniture

Useful when there are limited categories.

---

# 22. Card Visual

A Card displays a single important number.

Examples:

Total Sales
Total Customers
Total Orders
Average Sales

Example:

Total Sales = ₹5,00,000

---

# 23. Table Visual

A table displays detailed data.

Example:

Customer | City | Sales

Indra | Hyderabad | 50000
Ravi | Bangalore | 40000
Kiran | Chennai | 35000

---

# 24. Matrix Visual

Matrix is useful for summarized data with rows and columns.

Example:

Region | Product | Sales

North | Laptop | 50000
South | Mobile | 40000

---

# 25. Slicer

A slicer is an interactive filter.

Example:

Year
2024
2025
2026

When the user selects 2026, the report updates based on the selection.

---

# 26. Filters

Power BI provides different types of filters.

Common filters:

- Visual-level filter
- Page-level filter
- Report-level filter

---

# 27. Visual-Level Filter

Applies to one visual only.

Example:

A sales chart can show only:

Category = Electronics

Other visuals are not affected.

---

# 28. Page-Level Filter

Applies to all visuals on one report page.

Example:

Year = 2026

All visuals on that page show 2026 data.

---

# 29. Report-Level Filter

Applies across the entire report.

Example:

Country = India

All report pages can be filtered to India.

---

# 30. Data Modeling

Data modeling means organizing tables and creating relationships between them.

Example:

Customers
Orders
Products
Calendar

These tables can be connected using common columns.

---

# 31. Relationships

Example:

Customers
Customer_ID
↓
Orders
Customer_ID

Customer_ID connects the two tables.

---

# 32. Relationship Types

Common relationship types:

- One-to-One
- One-to-Many
- Many-to-One
- Many-to-Many

Most common in Data Analytics:

One-to-Many

Example:

One customer
→
Many orders

---

# 33. Fact Table

A fact table contains measurable business transactions.

Example:

Sales Fact

- Order_ID
- Customer_ID
- Product_ID
- Date_ID
- Quantity
- Sales
- Profit

---

# 34. Dimension Table

Dimension tables contain descriptive information.

Examples:

Customer Dimension
Product Dimension
Date Dimension
Location Dimension

---

# 35. Star Schema

A common Power BI data model is the Star Schema.

Example:

              Customers
                  |
                  |
Products ---- Sales ---- Calendar
                  |
                  |
              Location

Sales = Fact Table

Customers, Products, Calendar, Location = Dimension Tables

---

# 36. DAX

DAX stands for:

Data Analysis Expressions

DAX is used to create:

- Measures
- Calculated Columns
- Calculated Tables

---

# 37. Basic DAX Measure

Example:

Total Sales =
SUM(Sales[SalesAmount])

This measure calculates total sales.

---

# 38. COUNT Example

Total Orders =
COUNT(Sales[Order_ID])

---

# 39. DISTINCTCOUNT Example

Total Customers =
DISTINCTCOUNT(Sales[Customer_ID])

---

# 40. AVERAGE Example

Average Sales =
AVERAGE(Sales[SalesAmount])

---

# 41. Power BI Calculated Column

A calculated column creates a value for each row.

Example:

Profit =
Sales[SalesAmount] - Sales[Cost]

---

# 42. Measure vs Calculated Column

Measure:

- Calculated when needed
- Used mainly for aggregations
- Responds to filters
- Preferred for KPIs

Calculated Column:

- Calculated row by row
- Stored in the model
- Useful for row-level calculations

---

# 43. KPI

KPI means:

Key Performance Indicator

Examples:

- Total Sales
- Total Profit
- Profit Margin
- Customer Count
- Conversion Rate
- Sales Growth

---

# 44. Example Business Dashboard

A Sales Dashboard can contain:

Total Sales
Total Profit
Total Orders
Total Customers

And visuals:

Sales by Category
Sales by Region
Monthly Sales Trend
Top 10 Products

Slicers:

Year
Region
Category

---

# 45. Data Analyst Power BI Process

Step 1:
Understand the business requirement.

Step 2:
Connect to the data.

Step 3:
Clean the data using Power Query.

Step 4:
Create relationships.

Step 5:
Build the data model.

Step 6:
Create DAX measures.

Step 7:
Create visualizations.

Step 8:
Add slicers and filters.

Step 9:
Format the dashboard.

Step 10:
Validate the numbers.

Step 11:
Publish to Power BI Service.

---

# 🧠 QTHINK Method

When solving a Power BI problem:

WHAT?
What does the business want?

GIVEN?
What data is available?

NEED?
What KPI or analysis is required?

HOW?
Which Power BI feature should be used?

Example:

Question:
Management wants to know monthly sales.

WHAT?
Monthly sales

GIVEN?
Sales amount + Date

NEED?
Sales by month

HOW?
Date field + Sales measure + Line Chart

---

# 💼 Business Scenario

Question:

Management wants to know which category generates the highest sales.

WHAT?
Highest sales category

GIVEN?
Category + Sales

NEED?
Sales by category

HOW?

1. Create Total Sales measure.
2. Add Category.
3. Add Total Sales.
4. Use Bar Chart.
5. Sort by Sales descending.

DAX:

Total Sales =
SUM(Sales[SalesAmount])

---

# 💼 Business Scenario 2

Question:

Management wants to know monthly sales performance.

WHAT?
Monthly sales trend

GIVEN?
Date + Sales

NEED?
Sales by month

HOW?

1. Create Total Sales measure.
2. Use Date field.
3. Add Month to X-axis.
4. Add Total Sales to Y-axis.
5. Use Line Chart.

---

# ⚡ Quick Revision

Power BI
→ Business Intelligence and Visualization tool

Power BI Desktop
→ Build reports

Power BI Service
→ Publish and share reports

Power BI Mobile
→ View reports on mobile

Power Query
→ Clean and transform data

DAX
→ Create calculations and measures

Measure
→ Dynamic calculation

Calculated Column
→ Row-level calculation

Slicer
→ Interactive filter

Card
→ Show one important number

Bar Chart
→ Compare categories

Line Chart
→ Show trends

Table
→ Detailed data

Matrix
→ Summary with rows and columns

Fact Table
→ Transactions/measures

Dimension Table
→ Descriptive information

Star Schema
→ Fact + Dimension model

KPI
→ Important business metric

---

# 📝 Practice Questions

1. What is Power BI?
2. Why is Power BI used by Data Analysts?
3. What is Power BI Desktop?
4. What is Power BI Service?
5. What is Power Query?
6. What is DAX?
7. What is a measure?
8. What is a calculated column?
9. What is a slicer?
10. What is a dashboard?
11. What is a report?
12. What is the difference between report and dashboard?
13. What is a fact table?
14. What is a dimension table?
15. What is a relationship?
16. What is a star schema?
17. What is a KPI?
18. When do you use a bar chart?
19. When do you use a line chart?
20. What is the difference between a measure and calculated column?

---

# 🎯 Day 01 Practice Task

Create a simple Sales Dashboard using:

Columns:

Order_ID
Date
Customer
Category
Product
Region
Quantity
Sales
Profit

Create these KPIs:

- Total Sales
- Total Profit
- Total Orders
- Total Customers

Create these visuals:

- Sales by Category → Bar Chart
- Monthly Sales → Line Chart
- Sales by Region → Column Chart
- Top Products → Bar Chart
- Sales Details → Table

Add slicers:

- Year
- Region
- Category

---

# ✅ Day 01 Topics

✓ Power BI Introduction
✓ Power BI Desktop
✓ Power BI Service
✓ Power BI Mobile
✓ Get Data
✓ Data Sources
✓ Load Data
✓ Transform Data
✓ Power Query
✓ Data Cleaning
✓ Data Types
✓ Reports
✓ Dashboards
✓ Visualizations
✓ Bar Chart
✓ Line Chart
✓ Pie Chart
✓ Card
✓ Table
✓ Matrix
✓ Slicer
✓ Filters
✓ Data Modeling
✓ Relationships
✓ Fact Table
✓ Dimension Table
✓ Star Schema
✓ DAX Introduction
✓ Measures
✓ Calculated Columns
✓ KPIs
✓ Business Scenarios
✓ QTHINK Problem Solving

---

# 🚀 Next Day

Day 02 - Power BI Dashboard Design & Visualizations

