# Python Day 02 — DataFrame & Series

## 1. Day 2 Objective

Learn:
- What is a Series?
- What is a DataFrame?
- Create Series
- Create DataFrame
- Select columns
- Select rows
- Check rows and columns
- Understand index
- Inspect datasets
- Basic Data Analyst usage

---

## 2. What is a Series?

A Pandas Series is a one-dimensional labeled data structure.

Remember:

Series = 1 Column

Example:

10
20
30
40

A Series contains:
- Values
- Index

---

## 3. Import Pandas

import pandas as pd

Pandas is used for:
- Data cleaning
- Data analysis
- Data manipulation
- Data preparation

---

## 4. Create a Series

sales = pd.Series([1000, 2000, 3000, 4000])

print(sales)

---

## 5. Series with Custom Index

sales = pd.Series(
    [1000, 2000, 3000],
    index=["Jan", "Feb", "Mar"]
)

print(sales)

---

## 6. Access Series Value

print(sales["Jan"])

Using position:

print(sales.iloc[0])

---

## 7. What is a DataFrame?

A DataFrame is a two-dimensional tabular data structure.

It contains:
- Rows
- Columns
- Index

Remember:

Series = 1D
DataFrame = 2D

DataFrame = Excel-like table

---

## 8. Create a DataFrame

data = {
    "Name": ["Indra", "Rahul", "Anil"],
    "City": ["Hyderabad", "Chennai", "Bangalore"],
    "Sales": [50000, 40000, 60000]
}

df = pd.DataFrame(data)

print(df)

---

## 9. DataFrame Columns

print(df.columns)

Shows all column names.

---

## 10. Select One Column

print(df["Name"])

One column returns a Series.

Remember:

df["Name"] = Series

---

## 11. Select Multiple Columns

print(df[["Name", "Sales"]])

Multiple columns return a DataFrame.

Remember:

df["Name"] = One column

df[["Name", "Sales"]] = Multiple columns

---

## 12. Check Rows and Columns

print(df.shape)

Example:

(3, 3)

Meaning:

3 Rows
3 Columns

Remember:

shape = (rows, columns)

---

## 13. Check Column Names

print(df.columns)

Useful when you don't remember the dataset column names.

---

## 14. Check Index

print(df.index)

Default index starts from 0.

---

## 15. Check Data Types

print(df.dtypes)

Example:

Name      object
City      object
Sales      int64

Always check data types before analysis.

---

## 16. First Rows

print(df.head())

Shows first 5 rows.

First 10 rows:

print(df.head(10))

---

## 17. Last Rows

print(df.tail())

Shows last 5 rows.

Last 10 rows:

print(df.tail(10))

---

## 18. Basic Information

df.info()

Shows:
- Number of rows
- Number of columns
- Column names
- Data types
- Non-null values

Very important for Data Analysts.

---

## 19. Statistical Summary

df.describe()

Shows:

- count
- mean
- standard deviation
- minimum
- 25%
- 50%
- 75%
- maximum

---

## 20. Check Missing Values

print(df.isnull().sum())

Shows missing values in each column.

Example:

Name     0
City     1
Sales    0

---

## 21. Access Row by Position

print(df.iloc[0])

First row.

Second row:

print(df.iloc[1])

---

## 22. Access Multiple Rows

print(df.iloc[0:3])

Returns rows 0, 1 and 2.

---

## 23. Access Specific Cell

print(df.iloc[0, 2])

Meaning:

Row 0
Column 2

---

## 24. Access Column by Position

print(df.iloc[:, 0])

Meaning:

All rows
First column

---

## 25. Add a New Column

df["Bonus"] = [5000, 4000, 6000]

print(df)

---

## 26. Create Calculated Column

df["Total"] = df["Sales"] + df["Bonus"]

Total = Sales + Bonus

Very common in Data Analyst projects.

---

## 27. Rename a Column

df = df.rename(columns={"Sales": "Total_Sales"})

Sales becomes Total_Sales.

---

## 28. Delete a Column

df = df.drop(columns=["Bonus"])

Bonus column is removed.

---

## 29. Get Column Names as List

columns = df.columns.tolist()

print(columns)

---

## 30. Series vs DataFrame

Series:
- 1D
- One column
- Has index

DataFrame:
- 2D
- Multiple columns
- Rows + columns + index

Remember:

Series = Column

DataFrame = Table

---

## 31. Data Analyst Example

Dataset:

Order_ID | Customer | City | Sales

1001 | Indra | Hyderabad | 50000
1002 | Rahul | Chennai | 40000
1003 | Anil | Bangalore | 60000

Create DataFrame:

data = {
    "Order_ID": [1001, 1002, 1003],
    "Customer": ["Indra", "Rahul", "Anil"],
    "City": ["Hyderabad", "Chennai", "Bangalore"],
    "Sales": [50000, 40000, 60000]
}

df = pd.DataFrame(data)

print(df)

---

## 32. Data Analyst Inspection

After loading data:

print(df.head())
print(df.shape)
print(df.columns)
print(df.dtypes)
df.info()
print(df.describe())
print(df.isnull().sum())

Remember:

Load → Inspect → Clean → Analyze

---

## 33. Common Pandas Commands

df.head()
= First rows

df.tail()
= Last rows

df.shape
= Rows and columns

df.columns
= Column names

df.dtypes
= Data types

df.info()
= Dataset information

df.describe()
= Statistical summary

df.isnull().sum()
= Missing values

---

## 34. Interview Questions

Q1. What is Pandas?

Pandas is a Python library used for data manipulation and analysis.

Q2. What is a Series?

A Series is a one-dimensional labeled data structure.

Q3. What is a DataFrame?

A DataFrame is a two-dimensional tabular data structure with rows and columns.

Q4. Difference between Series and DataFrame?

Series represents one-dimensional data, while DataFrame represents two-dimensional tabular data.

Q5. How do you check rows and columns?

df.shape

Q6. How do you check data types?

df.dtypes

Q7. How do you see first 5 rows?

df.head()

Q8. How do you check missing values?

df.isnull().sum()

Q9. How do you get statistical information?

df.describe()

Q10. How do you select a column?

df["Sales"]

---

## 35. Data Analyst Thinking

When you receive a dataset:

1. Load the data
2. Understand the structure
3. Check rows and columns
4. Check data types
5. Check missing values
6. Check basic statistics
7. Start cleaning
8. Start analysis

Ask yourself:

"What data do I have?"

"What does each column mean?"

"Is the data ready for analysis?"

---

## 36. Day 2 Practice

Create this DataFrame:

Order_ID:
1001, 1002, 1003, 1004, 1005

Customer:
Indra, Rahul, Anil, Priya, Kiran

City:
Hyderabad, Chennai, Bangalore, Hyderabad, Pune

Sales:
50000, 40000, 60000, 55000, 45000

Practice:

1. Create the DataFrame
2. Print the DataFrame
3. Print first 3 rows
4. Print last 2 rows
5. Check shape
6. Check columns
7. Check data types
8. Check missing values
9. Select Customer column
10. Select Customer and Sales
11. Add a new column
12. Rename Sales
13. Remove the new column
14. Use describe()
15. Use info()

---

## 37. Quick Cheat Sheet

import pandas as pd
= Import Pandas

pd.Series()
= Create Series

pd.DataFrame()
= Create DataFrame

df.head()
= First rows

df.tail()
= Last rows

df.shape
= Rows + columns

df.columns
= Column names

df.dtypes
= Data types

df.info()
= Dataset information

df.describe()
= Statistics

df.isnull().sum()
= Missing values

df["Sales"]
= Select one column

df[["Customer", "Sales"]]
= Select multiple columns

df.iloc[0]
= Select row

---

## 38. Day 2 Key Memory

Series = 1D

DataFrame = 2D

head() = First rows

tail() = Last rows

shape = Rows + Columns

columns = Column names

dtypes = Data Types

info() = Dataset Information

describe() = Statistics

isnull().sum() = Missing Values

iloc[] = Position-based Selection

---

## Day 2 Checklist

[ ] Understand Series
[ ] Understand DataFrame
[ ] Create Series
[ ] Create DataFrame
[ ] Select columns
[ ] Select rows
[ ] Understand index
[ ] Use head()
[ ] Use tail()
[ ] Use shape
[ ] Use columns
[ ] Use dtypes
[ ] Use info()
[ ] Use describe()
[ ] Check missing values
[ ] Add columns
[ ] Rename columns
[ ] Remove columns
[ ] Practice DataFrame inspection

---

## Day 2 Goal

By the end of Day 2, you should be able to:

Create a Pandas DataFrame → Inspect the dataset → Select rows and columns → Understand the basic structure of data.

# Python Day 2 Completed
