# Day 01 - Python Basics

## 🎯 Goal
Learn the basic Python concepts required for a Data Analyst.

---

## 1. Python Introduction

Python is a programming language widely used for:

- Data Analysis
- Data Cleaning
- Automation
- Data Visualization
- Machine Learning

Important Python libraries for Data Analysts:

- Pandas
- NumPy
- Matplotlib
- Seaborn

---

## 2. print()

Used to display output.

Example:

print("Hello World")
print(100)

name = "Indra"
print(name)

---

## 3. Variables

A variable stores a value.

Example:

name = "Indra"
age = 22
salary = 50000

print(name)
print(age)
print(salary)

---

## 4. Data Types

Common Python data types:

str    → Text
int    → Whole numbers
float  → Decimal numbers
bool   → True / False
list   → Multiple values
tuple  → Multiple values
dict   → Key-value pairs
set    → Unique values

Example:

name = "Indra"
age = 22
salary = 50000.50
is_active = True

print(type(name))
print(type(age))
print(type(salary))
print(type(is_active))

---

## 5. Strings

A string is text.

Example:

name = "Indra"
city = "Hyderabad"

print(name)
print(city)

Useful operations:

print(name.upper())
print(name.lower())
print(len(name))

---

## 6. Integers

Integers are whole numbers.

Example:

age = 22
quantity = 10
employees = 100

---

## 7. Float

Float represents decimal numbers.

Example:

salary = 45000.50
price = 99.99
rating = 4.5

---

## 8. Boolean

Boolean has two values:

True
False

Example:

is_employee = True
is_active = False

---

## 9. Arithmetic Operators

+   → Addition
-   → Subtraction
*   → Multiplication
/   → Division
//  → Floor Division
%   → Modulus
**  → Power

Example:

a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)

---

## 10. Comparison Operators

==  → Equal
!=  → Not equal
>   → Greater than
<   → Less than
>=  → Greater than or equal
<=  → Less than or equal

Example:

salary = 60000

print(salary > 50000)
print(salary == 60000)

---

## 11. Logical Operators

### AND

Both conditions must be True.

age = 25
salary = 60000

print(age > 18 and salary > 50000)

### OR

At least one condition must be True.

print(age > 18 or salary > 100000)

### NOT

Reverses the result.

is_active = True

print(not is_active)

---

## 12. Type Conversion

Convert one data type into another.

Common functions:

int()
float()
str()
bool()

Example:

age = "22"

age = int(age)

print(age)
print(type(age))

Another example:

price = 100

price_text = str(price)

print(price_text)
print(type(price_text))

---

## 13. User Input

Used to get input from the user.

Example:

name = input("Enter your name: ")

print(name)

Important:

input() returns a string by default.

Example:

age = int(input("Enter your age: "))

print(age)

---

## 14. Comments

Comments are used to explain code.

Example:

# This is a comment

salary = 50000

Comments are ignored by Python.

---

## 15. if Statement

Used to make decisions.

Example:

age = 22

if age >= 18:
    print("Adult")

---

## 16. if - else

Example:

salary = 60000

if salary > 50000:
    print("High salary")
else:
    print("Low salary")

---

## 17. if - elif - else

Used when there are multiple conditions.

Example:

salary = 60000

if salary >= 80000:
    print("High")
elif salary >= 50000:
    print("Medium")
else:
    print("Low")

---

## 18. Lists

A list stores multiple values.

Example:

sales = [1000, 2000, 3000, 4000]

Access values using index:

print(sales[0])
print(sales[1])

Important:

Index starts from 0.

Useful methods:

sales.append(5000)
sales.remove(2000)
sales.sort()

Example:

sales = [3000, 1000, 4000, 2000]

sales.sort()

print(sales)

---

## 19. Tuples

A tuple stores multiple values and normally cannot be changed after creation.

Example:

coordinates = (10, 20, 30)

print(coordinates[0])
print(coordinates[1])

---

## 20. Dictionaries

A dictionary stores data as key-value pairs.

Example:

employee = {
    "name": "Indra",
    "age": 22,
    "salary": 50000
}

Access values:

print(employee["name"])
print(employee["salary"])

---

## 21. Sets

A set stores unique values.

Example:

numbers = {10, 20, 20, 30}

print(numbers)

Duplicate values are automatically removed.

---

# 💼 Data Analyst Example

employee_name = "Indra"
department = "Data Analytics"
salary = 50000
experience = 1

print(employee_name)
print(department)
print(salary)
print(experience)

---

# 💼 Business Example - Total Sales

product_price = 1000
quantity = 5

total_sales = product_price * quantity

print(total_sales)

Output:

5000

---

# 💼 Business Example - Salary Check

salary = 60000

if salary > 50000:
    print("High salary")
else:
    print("Low salary")

---

# 🧠 QTHINK Method

When solving a Python question, think:

WHAT?
What information/result is required?

GIVEN?
What data is provided?

NEED?
What calculation or operation is required?

HOW?
Which Python concept should be used?

Example:

Question:
Calculate total sales.

WHAT?
Total sales

GIVEN?
Price and Quantity

NEED?
Price × Quantity

HOW?
Multiplication

Code:

total_sales = price * quantity

---

# ⚡ Quick Revision

print()       → Display output
Variable      → Store data
str           → Text
int           → Whole number
float         → Decimal number
bool          → True / False
list          → Multiple values
tuple         → Fixed collection
dict          → Key-value pairs
set           → Unique values
if            → Condition
elif          → Additional condition
else          → Alternative condition
input()       → Get user input
type()        → Check data type
int()         → Convert to integer
float()       → Convert to float
str()         → Convert to string
bool()        → Convert to boolean

---

# 📝 Practice Questions

1. Print your name.
2. Store your age in a variable and print it.
3. Store your salary and check its data type.
4. Add two numbers.
5. Subtract two numbers.
6. Multiply two numbers.
7. Calculate the total price of 5 products.
8. Check whether salary is greater than 50,000.
9. Check whether a person is eligible based on age.
10. Create a list of 5 sales values.
11. Add a new sales value to the list.
12. Sort a sales list.
13. Create a dictionary containing employee information.
14. Remove duplicate values using a set.
15. Convert a string number into an integer.
16. Take a user's name as input and print it.
17. Find the highest value from a small list.
18. Calculate the average of 5 sales values.
19. Create a salary classification using if-elif-else.
20. Calculate total sales using price × quantity.

---

# 🎯 Interview Quick Questions

Q1. What is Python?

Python is a high-level programming language widely used for data analysis, automation, visualization, and machine learning.

Q2. What is a variable?

A variable is a name used to store a value.

Q3. What is a list?

A list is an ordered collection that can store multiple values and can be modified.

Q4. What is a tuple?

A tuple is an ordered collection that generally cannot be modified after creation.

Q5. What is a dictionary?

A dictionary stores data in key-value pairs.

Q6. What is a set?

A set stores unique values and removes duplicates.

Q7. What is the difference between int and float?

int stores whole numbers.
float stores decimal numbers.

Q8. What does type() do?

type() returns the data type of a value.

Q9. What does input() do?

input() takes information from the user.

Q10. What is the difference between = and ==?

= assigns a value.
== compares two values.

---

# ✅ Day 01 Topics

✓ Python Introduction
✓ print()
✓ Variables
✓ Data Types
✓ Strings
✓ Integers
✓ Floats
✓ Boolean
✓ Arithmetic Operators
✓ Comparison Operators
✓ Logical Operators
✓ Type Conversion
✓ User Input
✓ Comments
✓ if / elif / else
✓ Lists
✓ Tuples
✓ Dictionaries
✓ Sets
✓ Data Analyst Examples
✓ QTHINK Problem Solving
✓ Practice Questions
✓ Interview Basics

---

# 🚀 Next Day

Day 02 - Python Lists, Tuples, Dictionaries & Sets
