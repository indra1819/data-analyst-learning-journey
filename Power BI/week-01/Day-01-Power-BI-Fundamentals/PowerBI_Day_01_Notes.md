# Day 1 — Power BI Fundamentals

## 1. What is Power BI?

Power BI is a Business Intelligence and Data Visualization tool developed by Microsoft.

### Why Power BI for Data Analytics?

- Connect to different data sources
- Clean and transform data
- Analyze data
- Create interactive dashboards
- Create reports
- Share business insights
- Build data models
- Create DAX measures

---

## 2. Power BI Components

Main Power BI components:

- Power BI Desktop
- Power BI Service
- Power BI Mobile
- Power Query
- DAX
- Power BI Gateway

### Power BI Desktop

Used to:

- Connect data
- Clean data
- Create relationships
- Create calculations
- Build reports
- Create dashboards

### Power BI Service

Used to:

- Publish reports
- Share reports
- Create dashboards
- Collaborate with users
- Schedule data refresh

### Power BI Mobile

Used to view Power BI reports and dashboards on mobile devices.

---

## 3. Power BI Workflow

Basic Power BI workflow:

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
    Visualization
        ↓
    Report
        ↓
    Publish

---

## 4. Get Data

Power BI can connect to many data sources.

Common sources:

- Excel
- CSV
- SQL Server
- MySQL
- PostgreSQL
- Web
- SharePoint
- Folder
- Azure
- Oracle

### Example

Excel → Power BI

    Get Data
        ↓
    Excel Workbook
        ↓
    Select File
        ↓
    Select Sheet
        ↓
    Load / Transform Data

---

## 5. Power BI Desktop Views

Power BI Desktop mainly contains:

### Report View

Used to create visualizations and reports.

### Data View

Used to view table data.

### Model View

Used to create and manage relationships between tables.

---

## 6. Power Query

Power Query is used for data cleaning and transformation.

Common Power Query tasks:

- Remove duplicates
- Remove null values
- Change data types
- Rename columns
- Remove columns
- Replace values
- Split columns
- Merge columns
- Filter rows
- Add custom columns

---

## 7. Data Cleaning

Before creating a dashboard:

    Check Missing Values
          ↓
    Check Duplicates
          ↓
    Check Data Types
          ↓
    Rename Columns
          ↓
    Remove Unwanted Columns
          ↓
    Validate Data

---

## 8. Data Types in Power BI

Common Power BI data types:

- Text
- Whole Number
- Decimal Number
- Fixed Decimal Number
- Date/Time
- Date
- Time
- True/False

### Example

| Column | Data Type |
|--------|-----------|
| Customer_Name | Text |
| Quantity | Whole Number |
| Sales | Decimal Number |
| Order_Date | Date |
| Is_Active | True/False |

---

## 9. Power Query Editor

Power Query Editor is the main area for data transformation.

Basic steps:

    Home
      ↓
    Transform Data
      ↓
    Power Query Editor
      ↓
    Clean Data
      ↓
    Close & Apply

---

## 10. Remove Duplicates

Used when duplicate rows exist.

Steps:

    Select Column
        ↓
    Remove Rows
        ↓
    Remove Duplicates

---

## 11. Remove Null Values

Null means missing value.

Example:

| Customer | Sales |
|----------|-------|
| A | 1000 |
| B | null |
| C | 2000 |

Possible actions:

- Remove row
- Replace null
- Keep null depending on business requirement

---

## 12. Change Data Type

Correct data types are important.

Example:

    Sales → Decimal Number
    Quantity → Whole Number
    Order Date → Date
    Customer → Text

---

## 13. Rename Columns

Clear column names improve readability.

Example:

    Cust_Nm → Customer_Name
    Ord_Dt → Order_Date
    Amt → Sales

---

## 14. Data Model

A data model defines how tables are connected.

Example:

    Sales
       |
       | Customer_ID
       |
    Customers

---

## 15. Tables

Two common table types:

### Fact Table

Contains business transactions.

Example:

    Sales

Columns:

    Order_ID
    Customer_ID
    Product_ID
    Order_Date
    Quantity
    Sales

### Dimension Table

Contains descriptive information.

Example:

    Customers

Columns:

    Customer_ID
    Customer_Name
    City
    Segment

---

## 16. Relationships

Relationships connect tables using common columns.

Example:

    Sales[Customer_ID]
            |
            ↓
    Customers[Customer_ID]

Common relationship types:

- One-to-One
- One-to-Many
- Many-to-One
- Many-to-Many

---

## 17. Star Schema

Star schema is commonly used in Power BI data modeling.

Example:

              Customers
                  |
                  |
    Products — Sales — Date
                  |
                  |
               Region

### Fact Table

    Sales

### Dimension Tables

    Customers
    Products
    Date
    Region

---

## 18. Cardinality

Cardinality describes the relationship between tables.

Common types:

    One-to-One
    One-to-Many
    Many-to-One
    Many-to-Many

Most common in analytics:

    Dimension → Fact
       1          *

Example:

    Customers[Customer_ID]
             1
             |
             *
    Sales[Customer_ID]

---

## 19. Measures

Measures are calculations created using DAX.

Example:

    Total Sales =
    SUM(Sales[Sales])

Measures calculate values dynamically based on filters.

---

## 20. Calculated Columns

Calculated columns create a new column for each row.

Example:

    Profit =
    Sales[Sales] - Sales[Cost]

---

## 21. Measure vs Calculated Column

| Measure | Calculated Column |
|---------|-------------------|
| Calculated when needed | Calculated row by row |
| Uses DAX | Uses DAX |
| Good for aggregations | Good for row-level logic |
| Dynamic with filters | Stored in model |

### Interview Tip

Use a **measure** for dynamic business calculations such as:

    Total Sales
    Total Profit
    Average Sales
    Sales Growth

---

## 22. DAX

DAX means:

    Data Analysis Expressions

DAX is used to create:

- Measures
- Calculated columns
- Calculated tables

---

## 23. Basic DAX Functions

Important functions:

    SUM()
    AVERAGE()
    COUNT()
    COUNTROWS()
    DISTINCTCOUNT()
    MIN()
    MAX()
    CALCULATE()
    FILTER()
    DIVIDE()

---

## 24. SUM()

Used to calculate total.

    Total Sales =
    SUM(Sales[Sales])

---

## 25. AVERAGE()

Used to calculate average.

    Average Sales =
    AVERAGE(Sales[Sales])

---

## 26. COUNT()

Counts values in a column.

    Total Orders =
    COUNT(Sales[Order_ID])

---

## 27. COUNTROWS()

Counts rows in a table.

    Total Rows =
    COUNTROWS(Sales)

---

## 28. DISTINCTCOUNT()

Counts unique values.

    Total Customers =
    DISTINCTCOUNT(Sales[Customer_ID])

---

## 29. MIN()

Returns minimum value.

    Minimum Sales =
    MIN(Sales[Sales])

---

## 30. MAX()

Returns maximum value.

    Maximum Sales =
    MAX(Sales[Sales])

---

## 31. DIVIDE()

Used for safe division.

    Profit Margin =
    DIVIDE([Total Profit], [Total Sales])

---

## 32. CALCULATE()

`CALCULATE()` changes the filter context of a calculation.

Example:

    Online Sales =
    CALCULATE(
        [Total Sales],
        Sales[Channel] = "Online"
    )

---

## 33. Visualizations

Common Power BI visuals:

- Card
- Table
- Matrix
- Bar Chart
- Column Chart
- Line Chart
- Pie Chart
- Donut Chart
- Area Chart
- Scatter Chart
- Map
- Slicer

---

## 34. Card Visual

Used to display a single KPI.

Examples:

    Total Sales
    Total Profit
    Total Customers
    Total Orders

Example:

    Total Sales = ₹25,00,000

---

## 35. Bar Chart

Used to compare categories.

Example:

    Sales by Category

    Electronics     █████████
    Clothing        ███████
    Furniture       █████

---

## 36. Column Chart

Used to compare values vertically.

Example:

    Sales by Region

    North
    South
    East
    West

---

## 37. Line Chart

Used to analyze trends over time.

Example:

    Monthly Sales Trend

    Jan → 100K
    Feb → 120K
    Mar → 150K
    Apr → 140K

---

## 38. Pie / Donut Chart

Used to show contribution or percentage.

Example:

    Sales by Category

    Electronics → 45%
    Clothing → 30%
    Furniture → 25%

Use these charts only when the number of categories is manageable.

---

## 39. Table Visual

Used to display detailed data.

Example:

| Product | Sales | Profit |
|---------|------:|-------:|
| Laptop | 220000 | 40000 |
| Keyboard | 9000 | 2500 |
| Mouse | 5000 | 1500 |

---

## 40. Matrix Visual

Matrix is useful for summarized data with rows and columns.

Example:

| Region | 2025 | 2026 |
|--------|-----:|-----:|
| North | 100K | 120K |
| South | 150K | 170K |
| East | 90K | 110K |

---

## 41. Slicer

Slicer is used to filter report data interactively.

Common slicers:

    Year
    Month
    Region
    Category
    Product

Example:

    Region
    [All]
    [North]
    [South]
    [East]
    [West]

---

## 42. Filters

Power BI has different filter levels.

### Visual Level Filter

Affects one visual.

### Page Level Filter

Affects all visuals on one page.

### Report Level Filter

Affects the entire report.

---

## 43. KPI

KPI means:

    Key Performance Indicator

Examples:

    Total Sales
    Total Profit
    Profit Margin
    Total Orders
    Customer Count
    Sales Growth

---

## 44. Dashboard vs Report

### Report

- Usually contains multiple pages
- Interactive
- Contains multiple visuals
- Used for detailed analysis

### Dashboard

- Single-page view
- Contains important KPIs and visuals
- Used for monitoring business performance
- Available in Power BI Service

---

## 45. Power BI Dashboard Structure

A basic business dashboard can contain:

    -----------------------------------------
    | Total Sales | Profit | Orders | Customers |
    -----------------------------------------
    |             Sales Trend               |
    -----------------------------------------
    | Sales by Category | Sales by Region    |
    -----------------------------------------
    |             Product Table              |
    -----------------------------------------

---

## 46. Executive Dashboard

Executive dashboards focus on important business KPIs.

Recommended KPIs:

    Total Revenue
    Total Profit
    Total Orders
    Total Customers
    Profit Margin

Recommended visuals:

    KPI Cards
    Sales Trend
    Sales by Category
    Sales by Region
    Top Products
    Slicers

---

## 47. Power BI Color and Layout

Good dashboard design should have:

- Consistent colors
- Clear titles
- Proper spacing
- Simple visuals
- Readable fonts
- Important KPIs at the top

Avoid:

- Too many colors
- Too many charts
- Unnecessary 3D visuals
- Too much text
- Crowded layouts

---

## 48. Basic Dashboard Workflow

    1. Import Data
    2. Open Power Query
    3. Clean Data
    4. Set Data Types
    5. Load Data
    6. Create Relationships
    7. Create DAX Measures
    8. Add Visualizations
    9. Add Slicers
    10. Format Dashboard
    11. Validate Numbers
    12. Publish

---

## 49. Data Validation

Always check whether Power BI numbers match the source data.

Check:

    Total Rows
    Total Sales
    Total Orders
    Total Customers
    Missing Values
    Duplicate Records

---

## 50. Power BI Example

Suppose we have:

| Order_ID | Product | Category | Sales | Profit |
|----------|---------|----------|------:|-------:|
| 101 | Laptop | Electronics | 80000 | 12000 |
| 102 | Mouse | Electronics | 2000 | 500 |
| 103 | Chair | Furniture | 10000 | 2000 |
| 104 | Keyboard | Electronics | 5000 | 1000 |

Create measures:

    Total Sales =
    SUM(Sales[Sales])

    Total Profit =
    SUM(Sales[Profit])

    Total Orders =
    COUNTROWS(Sales)

    Profit Margin =
    DIVIDE([Total Profit], [Total Sales])

---

## 51. Business Questions Power BI Should Answer

A Data Analyst dashboard should answer questions such as:

### Sales

    How much are we selling?

### Profit

    How much profit are we making?

### Trend

    Are sales increasing or decreasing?

### Category

    Which category generates the most sales?

### Product

    Which products perform best?

### Region

    Which region generates the most revenue?

### Customer

    Which customers generate the most revenue?

---

## 52. Data Analyst Thinking

When creating a Power BI dashboard:

    1. Understand the business requirement
    2. Identify important KPIs
    3. Understand the data
    4. Clean the data
    5. Build relationships
    6. Create measures
    7. Select appropriate visuals
    8. Add filters
    9. Validate results
    10. Present insights

---

## 53. Interview Quick Notes

### What is Power BI?

Power BI is Microsoft's Business Intelligence and data visualization tool used to connect, transform, analyze and visualize data.

### What is Power Query?

Power Query is used for data extraction, cleaning and transformation.

### What is DAX?

DAX stands for Data Analysis Expressions and is used to create calculations in Power BI.

### What is a Measure?

A measure is a dynamic DAX calculation evaluated based on the current filter context.

### What is a Calculated Column?

A calculated column is calculated row by row and stored in the data model.

### What is a Slicer?

A slicer is an interactive visual used to filter report data.

### What is a Relationship?

A relationship connects tables using common columns.

### What is a Star Schema?

A star schema contains a central fact table connected to multiple dimension tables.

### Power BI Desktop vs Service

    Desktop → Build and develop reports
    Service → Publish, share and collaborate

### Power Query vs DAX

    Power Query → Data cleaning and transformation
    DAX → Data analysis and calculations

---

## 54. Day 1 Practice

### Practice 1

Import an Excel or CSV sales dataset into Power BI.

### Practice 2

Check:

    Number of Rows
    Number of Columns
    Data Types
    Missing Values
    Duplicate Values

### Practice 3

Clean the dataset using Power Query.

### Practice 4

Create these measures:

    Total Sales
    Total Profit
    Total Orders
    Total Customers
    Average Sales

### Practice 5

Create these visuals:

    Total Sales Card
    Total Profit Card
    Sales by Category
    Sales by Region
    Monthly Sales Trend

### Practice 6

Add slicers for:

    Year
    Region
    Category

### Practice 7

Create a simple one-page sales dashboard.

---

## 55. Day 1 Checklist

- [x] Power BI Introduction
- [x] Power BI Components
- [x] Power BI Workflow
- [x] Get Data
- [x] Power BI Desktop
- [x] Report View
- [x] Data View
- [x] Model View
- [x] Power Query
- [x] Data Cleaning
- [x] Data Types
- [x] Fact Tables
- [x] Dimension Tables
- [x] Relationships
- [x] Star Schema
- [x] Cardinality
- [x] Measures
- [x] Calculated Columns
- [x] DAX
- [x] Basic DAX Functions
- [x] Visualizations
- [x] Slicers
- [x] Filters
- [x] KPIs
- [x] Dashboard vs Report
- [x] Executive Dashboard
- [x] Data Validation
- [x] Data Analyst Thinking
- [x] Practice Questions

---

## Day 1 Summary

    Get Data
         ↓
    Power Query
         ↓
    Data Cleaning
         ↓
    Data Model
         ↓
    Relationships
         ↓
    DAX
         ↓
    Visualizations
         ↓
    Dashboard
         ↓
    Business Insights

**Day 1 completed — Power BI Fundamentals**
