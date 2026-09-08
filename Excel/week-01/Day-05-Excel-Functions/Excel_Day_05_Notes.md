# Excel Day 05 – Power Query Data Cleaning

## 1. What is Power Query?

Power Query is an Excel data transformation tool used to:

- Import data
- Clean data
- Transform data
- Combine data
- Prepare data for analysis and reporting

Power Query is especially useful when working with large or messy datasets.

---

# 2. Why Data Cleaning is Important

Raw data often contains problems such as:

- Duplicate records
- Extra spaces
- Inconsistent text capitalization
- Missing values
- N/A values
- Mixed date formats
- Invalid dates
- Numbers stored as text
- Currency symbols and commas

Data cleaning helps make the dataset accurate and ready for analysis.

---

# 3. Opening Power Query

In Excel:

```text
4. Remove Duplicate Rows
Duplicate records can affect calculations and analysis.
Steps
Select the required columns
→ Home
→ Remove Rows
→ Remove Duplicates
Power Query keeps one copy of the duplicate record.
5. Remove Extra Spaces
Extra spaces can cause problems while filtering, grouping, or matching data.
Example
Before:
"  Laptop  "
After:
"Laptop"
Steps
Select Column
→ Transform
→ Format
→ Trim
Trim removes unnecessary spaces from the beginning and end of text.
6. Clean Text
Power Query provides text transformation options.
Common options include:
- Uppercase
- Lowercase
- Capitalize Each Word
- Trim
- Clean
Example
Before:
laptop
LAPTOP
Laptop
After applying a consistent format:
Laptop
Laptop
Laptop
Consistent text makes analysis easier.
7. Handle Missing Values
Missing values can appear as blank cells or null.
Example:
Product	Sales
Laptop	50000
Mouse	null
Keyboard	30000


Possible actions:
- Replace with 0
- Replace with a suitable value
- Remove the row
- Keep as null if missingness has meaning
The correct approach depends on the business requirement.
8. Replace Values
Power Query can replace incorrect or unwanted values.
Steps
Select Column
→ Transform
→ Replace Values
Example:
N/A → null
or:
Hyderbad → Hyderabad
This helps standardize the dataset.
9. Change Data Types
Correct data types are important for calculations and analysis.
Common Power Query data types:
Data Type	Example
Text	Laptop
Whole Number	100
Decimal Number	99.50
Date	2026-09-08
Date/Time	2026-09-08 10:30
True/False	TRUE


Steps
Select Column
→ Data Type
→ Choose Required Type
10. Numbers Stored as Text
Sometimes numbers are imported as text.
Example:
"5000"
"7500"
"10000"
These may not behave correctly in calculations.
Convert the column to:
Whole Number
or:
Decimal Number
depending on the data.
11. Currency Symbols and Commas
Raw sales data may contain values such as:
$50,000
$25,500
$10,000
These may need cleaning before numerical analysis.
The currency symbol and formatting should be handled appropriately so the column can be converted to a numeric data type.
12. Date Cleaning
Dates may appear in different formats:
01/08/2026
2026-08-01
01-Aug-2026
For analysis, dates should be converted into a consistent date type.
Steps
Select Date Column
→ Data Type
→ Date
If Power Query interprets the date incorrectly, use:
Change Type
→ Using Locale
and select the appropriate locale/date format.
13. Invalid Dates
Some records may contain invalid date values.
Example:
31/02/2026
If Power Query identifies an invalid value, you can:
- Replace the error
- Remove the error
- Correct the source data
Options
Home
→ Remove Rows
→ Remove Errors
or use:
Replace Errors
14. Remove Errors
Power Query can identify cells containing errors.
Steps
Select Column
→ Home
→ Remove Rows
→ Remove Errors
Use this carefully because removing errors also removes those records.
15. Fill Down
Fill Down copies the value from the cell above into empty cells below.
Example:
Category
Electronics
null
null
Furniture
null


After Fill Down:
Category
Electronics
Electronics
Electronics
Furniture
Furniture


Steps
Select Column
→ Transform
→ Fill
→ Down
16. Remove Unnecessary Columns
If a column is not required for analysis, it can be removed.
Steps
Select Column
→ Right Click
→ Remove
Removing unnecessary columns makes the dataset cleaner and easier to work with.
17. Rename Columns
Clear column names improve readability.
Example:
Before:
Cust_Name
Prod_Name
Amt
After:
Customer Name
Product Name
Sales Amount
Steps
Double-click Column Name
→ Enter New Name
18. Split Columns
A single column may contain multiple pieces of information.
Example:
Ravi - Hyderabad
We can split it into:
Name	City
Ravi	Hyderabad


Steps
Select Column
→ Transform
→ Split Column
→ By Delimiter
19. Merge Columns
Multiple columns can also be combined.
Example:
First Name	Last Name
Ravi	Kumar


After merging:
Ravi Kumar
Steps
Select Columns
→ Transform
→ Merge Columns
20. Close & Load
After completing the transformations:
Home
→ Close & Load
The cleaned data is loaded back into Excel.
21. Power Query Transformation Workflow
A typical data-cleaning workflow is:
Import Raw Data
      ↓
Remove Duplicates
      ↓
Remove Extra Spaces
      ↓
Clean Text
      ↓
Handle Missing Values
      ↓
Replace Incorrect Values
      ↓
Change Data Types
      ↓
Clean Dates
      ↓
Remove Errors
      ↓
Remove Unnecessary Columns
      ↓
Close & Load
22. Practical E-Commerce Data Cleaning
For an e-commerce dataset, common cleaning tasks include:
Product Column
- Remove extra spaces
- Standardize capitalization
- Correct spelling mistakes
Sales Column
- Remove currency symbols
- Remove unnecessary commas
- Convert to numeric type
Order Date
- Convert to Date type
- Standardize date format
- Handle invalid dates
Customer Column
- Remove extra spaces
- Handle missing customer names
Duplicate Orders
- Identify and remove duplicate records when appropriate
23. Power Query vs Excel Formulas
Power Query	Excel Formulas
Best for data transformation	Best for calculations
Good for repeatable cleaning	Good for cell-level calculations
Can handle large datasets efficiently	Can become complex with large datasets
Transformations can be refreshed	Formulas recalculate in the worksheet
Useful for ETL workflows	Useful for analysis and reporting


24. Key Interview Points
- Power Query is used for importing, cleaning, and transforming data.
- It is useful for preparing raw data for analysis.
- Power Query transformations can be refreshed when source data changes.
- Trim removes extra spaces.
- Remove Duplicates removes duplicate records.
- Data types should be correctly assigned.
- Missing values should be handled according to business requirements.
- Fill Down copies values into empty cells below.
- Split Column separates one column into multiple columns.
- Merge Columns combines multiple columns.
- Close & Load loads the transformed data back into Excel.
Day 05 Summary
Today I learned Power Query Data Cleaning.
Topics covered:
Power Query
Data Cleaning
Remove Duplicates
Trim
Clean Text
Replace Values
Missing Values
Change Data Types
Numbers Stored as Text
Currency Cleaning
Date Cleaning
Invalid Dates
Remove Errors
Fill Down
Remove Columns
Rename Columns
Split Columns
Merge Columns
Close & Load
Data
→ Get Data
→ From Table/Range
