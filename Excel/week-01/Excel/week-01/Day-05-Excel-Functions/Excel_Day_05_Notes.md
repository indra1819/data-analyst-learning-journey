# Excel Day 05 – Power Query Data Cleaning

## Overview

Power Query is an Excel data transformation tool used to import, clean,
transform, and prepare raw data for analysis and reporting.

In Day 05, I practiced cleaning a messy e-commerce dataset using Power Query.

---

## Dataset

The dataset contained messy e-commerce transaction data with issues such as:

- Duplicate records
- Extra spaces
- Inconsistent text capitalization
- Missing values
- N/A values
- Mixed date formats
- Invalid dates
- Numbers stored as text
- Currency symbols and commas
- Negative values
- Incorrect/outlier values
- Inconsistent category and payment values

---

# Data Cleaning Steps

## 1. Remove Duplicates

Identified duplicate transaction records and removed duplicates
where appropriate.

### Business Purpose

Duplicate records can increase sales, transaction counts, and other KPIs
incorrectly.

---

## 2. Remove Extra Spaces

Used Power Query text transformation to remove unnecessary spaces
from text columns.

### Example

```text
"  Hyderabad  "
        ↓
"Hyderabad"
Business Purpose
Extra spaces can create duplicate categories or cities during analysis.
3. Standardize Text Values
Identified inconsistent capitalization and standardized text values.
Example
hyderabad
Hyderabad
HYDERABAD
These should represent the same city.
4. Handle Missing Values
Checked columns for null/missing values.
Important principle:
Do not automatically replace missing values with 0.
The correct treatment depends on the business meaning of the missing value.
For example:
Missing Quantity → investigate before replacing
Missing Unit Price → check whether the price can be recovered
Missing Sales Rep → may remain null if information is unavailable
5. Handle N/A Values
Identified values such as:
N/A
and treated them as missing/invalid values where appropriate.
6. Clean Numeric Columns
Checked numeric columns for:
Numbers stored as text
Currency symbols
Commas
Negative values
Invalid numeric values
Example
₹50,000
    ↓
50000
After cleaning, the column can be converted to an appropriate numeric data type.
7. Validate Outliers
Extreme values were not removed blindly.
An unusual value must first be investigated to determine whether it is:
A genuine business value
A data-entry error
An invalid value
Example
A Unit Price of:
₹999,999
was identified as a data-entry error and validated against the expected product price before correction.
Key Principle
Validate before removing or correcting an outlier.
8. Handle Invalid Values
Checked values that violate business rules.
Example
A negative Unit Price such as:
-₹5000
should be investigated because a negative product price may not be valid for a normal sales transaction.
9. Date Cleaning
The dataset contained different date formats and invalid date values.
Examples:
27/02/2025
2025-06-04
05-06-2025
Feb 24, 2025
Dates need to be standardized before converting the column to the Date data type.
Important
Mixed date formats can cause incorrect date interpretation if the wrong locale is used.
10. Product-wise Missing Value Analysis
To find missing Unit Price values by Product:
Return to the detailed-data step before Group By.
Filter Unit Price for null values.
Group by Product.
Count the rows.
Business Purpose
This helps identify which products have missing pricing information.
Power Query Workflow
Raw Data
   ↓
Import into Power Query
   ↓
Inspect Data
   ↓
Remove Duplicates
   ↓
Clean Text
   ↓
Handle Missing / N/A Values
   ↓
Clean Numeric Columns
   ↓
Validate Outliers
   ↓
Clean Dates
   ↓
Set Correct Data Types
   ↓
Validate Clean Data
   ↓
Load for Analysis
Data Analyst Principles
1. Never Guess Data
If a value is missing, do not automatically assume what it should be.
2. Do Not Delete Outliers Blindly
First determine whether the value is a genuine observation or an error.
3. Understand Business Rules
Data cleaning decisions should be based on business logic.
4. Preserve Data Quality
The objective of cleaning is to make data reliable for analysis, not simply to make the dataset look clean.
Power Query vs Manual Excel
Manual Excel
Power Query
Repetitive
Repeatable
Time-consuming
Faster for large datasets
More manual steps
Transformation steps are recorded
Difficult to reproduce
Easy to refresh
Higher manual-error risk
Better for consistent workflows
Data Analyst Use Cases
Power Query can be used for:
Data cleaning
Data transformation
Combining files
Removing duplicates
Handling missing values
Standardizing text
Changing data types
Preparing data for Power BI
Preparing data for Excel reports
Repeatable data-cleaning workflows
Key Learning
Power Query is not just about removing errors.
A Data Analyst should ask:
What is wrong with the data?
Why is it wrong?
Can the correct value be determined?
What business rule should be applied?
How can the cleaning process be made repeatable?
Status
Excel Day 05 – Power Query Data Cleaning Completed ✅
