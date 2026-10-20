# Power BI Day 02 — Data Loading & Power Query Basics

## 1. Day 2 Objective

Learn how to:
- Import data into Power BI
- Understand Power BI data sources
- Use Power Query
- Clean and transform data
- Understand Applied Steps
- Load clean data into Power BI

---

# 2. Power BI Data Flow

Basic Power BI workflow:

Data Source
    ↓
Get Data
    ↓
Power Query
    ↓
Clean & Transform
    ↓
Close & Apply
    ↓
Data Model
    ↓
Visualizations
    ↓
Dashboard

Remember:

**Get → Clean → Model → Visualize**

---

# 3. Get Data

In Power BI Desktop:

Home → Get Data

Common data sources:

- Excel
- CSV
- SQL Server
- MySQL
- Web
- Folder
- SharePoint
- Text/CSV
- JSON

For Data Analyst jobs, the most common:

**Excel + CSV + SQL + Web**

---

# 4. Import Excel Data

Steps:

1. Open Power BI Desktop
2. Click Home
3. Click Get Data
4. Select Excel
5. Select the Excel file
6. Select required sheet/table
7. Click Transform Data

Important:

**Transform Data = Open Power Query**

---

# 5. Import CSV Data

Steps:

1. Home
2. Get Data
3. Text/CSV
4. Select CSV file
5. Check preview
6. Click Transform Data

Power BI automatically detects:

- Column names
- Data types
- Delimiter
- Headers

Always verify the data types.

---

# 6. Power Query

Power Query is used for:

**Data Cleaning + Data Transformation**

Common tasks:

- Remove columns
- Rename columns
- Change data types
- Remove duplicates
- Replace values
- Filter rows
- Remove nulls
- Split columns
- Merge columns
- Add custom columns
- Fill missing values

---

# 7. Power Query Editor

Important areas:

### Queries Pane
Shows all imported tables.

### Data Preview
Shows the selected table.

### Formula Bar
Shows the Power Query M expression.

### Applied Steps
Shows every transformation performed on the data.

---

# 8. Applied Steps

Example:

Source
↓
Promoted Headers
↓
Changed Type
↓
Removed Columns
↓
Filtered Rows
↓
Removed Duplicates

Power Query records each transformation as an Applied Step.

Important:

**Applied Steps = Transformation History**

---

# 9. Change Data Type

Correct data types are very important.

Example:

Order_ID → Whole Number

Customer → Text

Order_Date → Date

Sales → Decimal Number

Quantity → Whole Number

Important data types:

- Text
- Whole Number
- Decimal Number
- Date
- Date/Time
- True/False
- Percentage

---

# 10. Remove Unnecessary Columns

If a column is not required:

Select column
→ Right Click
→ Remove

Example:

Dataset:

Order_ID
Customer
Product
Sales
Quantity
Internal_Code

If Internal_Code is not required:

Remove Internal_Code

Rule:

**Keep only useful columns.**

---

# 11. Rename Columns

Good column names make analysis easier.

Example:

cust_name → Customer_Name

ord_dt → Order_Date

amt → Sales

Use:

Right Click Column
→ Rename

---

# 12. Remove Duplicates

Duplicates can affect analysis.

Example:

Order_ID
1001
1002
1002
1003

If Order_ID must be unique:

Select Order_ID
→ Remove Rows
→ Remove Duplicates

Always understand the business meaning before removing duplicates.

---

# 13. Remove Null Values

Null means missing value.

Example:

Customer
Indra
Rahul
null
Anil

Possible actions:

- Remove row
- Replace with value
- Keep as null
- Fill Down
- Fill Up

Do NOT automatically delete every null.

First understand why the value is missing.

---

# 14. Replace Values

Example:

City column:

HYD
HYD
Hyd
Hyderabad

You can standardize:

HYD → Hyderabad
Hyd → Hyderabad

Power Query:

Transform
→ Replace Values

Goal:

**Standardized Data**

---

# 15. Filter Rows

Example:

Sales > 10000

Power Query:

Column Filter
→ Number Filters
→ Greater Than
→ 10000

Another example:

City = Hyderabad

Filter:

City
→ Hyderabad

---

# 16. Split Column

Example:

Full_Name

Indra Muchugiri

Split into:

First_Name → Indra
Last_Name → Muchugiri

Power Query:

Transform
→ Split Column
→ By Delimiter

Delimiter examples:

- Space
- Comma
- Hyphen
- Underscore

---

# 17. Merge Columns

Example:

First_Name | Last_Name

Indra | Muchugiri

Merge:

Full_Name

Indra Muchugiri

Power Query:

Select columns
→ Merge Columns

---

# 18. Add Custom Column

Power Query can create new columns.

Example:

Sales = 10000
Cost = 7000

Profit:

Sales - Cost

Custom Column:

Profit = [Sales] - [Cost]

Result:

Profit = 3000

---

# 19. Conditional Column

Example:

Sales:

5000
15000
25000

Create Sales_Category:

If Sales >= 20000 → High
If Sales >= 10000 → Medium
Else → Low

Result:

5000 → Low
15000 → Medium
25000 → High

---

# 20. Power Query vs Excel Formulas

Excel formulas:

Used mainly inside Excel worksheets.

Power Query:

Used mainly for repeatable data cleaning and transformation.

Data Analyst rule:

**If the same cleaning process happens repeatedly → Power Query is useful.**

---

# 21. Close & Apply

After cleaning:

Home
→ Close & Apply

This loads the transformed data into the Power BI data model.

Remember:

**Transform → Close & Apply**

---

# 22. Data Cleaning Checklist

Before loading data:

[ ] Check column names
[ ] Check data types
[ ] Check missing values
[ ] Check duplicates
[ ] Check incorrect values
[ ] Remove unnecessary columns
[ ] Standardize text
[ ] Check date columns
[ ] Check numeric columns
[ ] Validate the final data

---

# 23. Data Analyst Example

Dataset:

Order_ID | Customer | City | Product | Sales | Quantity

Example:

1001 | Indra | Hyderabad | Laptop | 60000 | 1
1002 | Rahul | Hyderabad | Mouse | 1000 | 2
1003 | Anil | Chennai | Keyboard | 3000 | 1
1004 | Priya | Hyderabad | Laptop | 55000 | 1

Cleaning tasks:

1. Check duplicate Order_ID
2. Check missing Customer
3. Check City spelling
4. Check Sales data type
5. Check Quantity data type
6. Check Product names
7. Remove unnecessary columns
8. Load cleaned data

---

# 24. Interview Questions

### Q1. What is Power Query?

Power Query is a data transformation and cleaning tool used in Power BI.

### Q2. Why do we use Power Query?

To clean, transform and prepare raw data before analysis.

### Q3. What are Applied Steps?

Applied Steps show the sequence of transformations performed on the data.

### Q4. What is Close & Apply?

It applies the Power Query transformations and loads the data into Power BI.

### Q5. Can Power Query remove duplicates?

Yes.

### Q6. Can Power Query handle missing values?

Yes. We can remove, replace, fill, or keep missing values depending on the business requirement.

### Q7. What is the difference between Power Query and Power BI?

Power Query is mainly for data preparation.

Power BI is used for data modeling, analysis and visualization.

---

# 25. Data Analyst Thinking

When you receive a raw dataset, don't immediately create charts.

Think:

1. What is the business requirement?
2. What data do I have?
3. Are the columns correct?
4. Are there missing values?
5. Are there duplicates?
6. Are data types correct?
7. Is the data standardized?
8. What transformations are required?
9. Is the final data ready for analysis?

Remember:

**Clean data first → Analyze second → Visualize third**

---

# 26. Day 2 Practice

Take an Excel or CSV dataset and perform:

1. Import the dataset
2. Open Power Query
3. Rename 2 columns
4. Change data types
5. Remove 1 unnecessary column
6. Remove duplicates
7. Check null values
8. Replace incorrect values
9. Filter rows
10. Create one conditional column
11. Create one custom column
12. Review Applied Steps
13. Click Close & Apply

---

# 27. Quick Cheat Sheet

Get Data
→ Import data

Transform Data
→ Open Power Query

Power Query
→ Clean + Transform

Applied Steps
→ Transformation history

Changed Type
→ Correct data types

Remove Duplicates
→ Remove repeated records

Replace Values
→ Standardize incorrect values

Filter Rows
→ Keep required records

Custom Column
→ Create calculation

Conditional Column
→ Create rule-based category

Close & Apply
→ Load transformed data

---

# 28. Day 2 Key Memory

**GET → CLEAN → TRANSFORM → APPLY**

Power Query =

**Clean + Transform + Prepare**

Most important rule:

**Never build a dashboard before checking the data.**

---

# Day 2 Checklist

[ ] Understand Get Data
[ ] Import Excel
[ ] Import CSV
[ ] Understand Power Query
[ ] Change data types
[ ] Remove duplicates
[ ] Handle null values
[ ] Replace values
[ ] Filter rows
[ ] Split columns
[ ] Merge columns
[ ] Create custom column
[ ] Create conditional column
[ ] Understand Applied Steps
[ ] Use Close & Apply

# Day 2 Goal

By the end of Day 2, you should be able to:

**Import raw data → Clean it in Power Query → Transform it → Load it into Power BI.**

# Power BI Day 2 Completed
