# Day 1 — Power BI Fundamentals

## Topics Covered

- Power BI Desktop
- Importing Excel data
- Selecting the required table
- Checking data types
- Report canvas setup
- Setting page size to 16:9
- Setting report background
- Creating a dashboard header
- Basic report layout

---

## 1. Power BI Desktop

### What is Power BI?

Power BI is a Business Intelligence tool used to:

- Import data
- Clean and transform data
- Analyze data
- Create visualizations
- Build interactive dashboards
- Share business insights

### Main Power BI Workflow

```text
Data → Transform → Model → Visualize → Report
2. Importing Excel Data
Business Scenario
We have an Excel file containing e-commerce sales data and want to create a Power BI dashboard.
Steps
1. Open Power BI Desktop
2. Select Get Data
3. Select Excel
4. Choose the Excel file
5. Select the required worksheet/table
6. Click Load
Important Point
Before loading the data, check whether the correct table or worksheet has been selected.
3. Selecting Cleaned Data
For the project, the cleaned dataset was named:
Cleaned_Data
Why use cleaned data?
Cleaned data helps us avoid problems such as:
- Duplicate records
- Missing values
- Incorrect data types
- Inconsistent values
- Incorrect calculations
Data Flow
Raw Data
   ↓
Data Cleaning
   ↓
Cleaned_Data
   ↓
Power BI
   ↓
Dashboard
4. Checking Data Types
After importing the data, check whether each column has the correct data type.
Examples:
Column	Data Type
Order ID	Text / Whole Number
Product	Text
Category	Text
Quantity	Whole Number
Sales	Decimal Number
Cost	Decimal Number
Profit	Decimal Number
Order Date	Date


Why Data Types Matter
Correct data types are important for:
- Calculations
- Filtering
- Sorting
- Date analysis
- Visualizations
- DAX measures
5. Report Canvas Setup
After importing the data, prepare the report canvas before creating visuals.
Page Size
Set the report page to:
16:9
Why 16:9?
16:9 is a standard widescreen format and provides a professional dashboard layout.
It works well for:
- Desktop screens
- Presentations
- Business dashboards
- KPI cards
- Charts
- Slicers
6. Dashboard Background
Background Color
The dashboard background was configured with:
HEX: #0B1220
Transparency: 0%
Why use a consistent background?
A consistent background helps:
- Improve visual hierarchy
- Make the dashboard look professional
- Separate the report sections
- Improve readability
7. Dashboard Header
A rectangle shape was added at the top of the report to create the dashboard header.
Purpose of Header
The header provides a clear area for:
- Dashboard title
- Company/project name
- Report period
- Other important information
Basic Layout
┌──────────────────────────────────────────────┐
│              E-COMMERCE SALES ANALYSIS       │
├──────────────────────────────────────────────┤
│                                              │
│              Dashboard Area                  │
│                                              │
└──────────────────────────────────────────────┘
8. Basic Dashboard Layout
Before adding charts, the report page should have a clear structure.
Example:
┌──────────────────────────────────────────────┐
│          E-COMMERCE SALES ANALYSIS           │
├────────────┬────────────┬────────────┬───────┤
│ Total Sales│ Total Cost │Total Profit│ Orders│
├────────────┴────────────┴────────────┴───────┤
│                                              │
│              Charts / Analysis               │
│                                              │
├───────────────────────┬──────────────────────┤
│       Chart 1         │       Chart 2        │
│                       │                      │
└───────────────────────┴──────────────────────┘
Day 1 Key Learning
Power BI Basic Workflow
1. Open Power BI Desktop
2. Import Excel data
3. Select Cleaned_Data
4. Check data types
5. Set report canvas
6. Set page size to 16:9
7. Set dashboard background
8. Create dashboard header
9. Prepare the report layout
Interview Questions
Q1. What is Power BI?
Power BI is a Business Intelligence tool used to analyze data and create interactive reports and dashboards.
Q2. Why should we check data types after importing data?
Correct data types are required for accurate calculations, filtering, sorting, date analysis, and visualizations.
Q3. Why is dashboard layout important?
A proper layout makes the report easier to understand and helps users quickly identify important business insights.
Q4. Why do we use 16:9 for dashboards?
16:9 provides a standard widescreen layout that works well for desktop dashboards and presentations.
Day 1 Status
Power BI Day 1 — Completed
