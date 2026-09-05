# Python Day 01 – Fundamentals

## What is Python?

Python is a high-level, interpreted programming language widely used for:

- Data Analysis
- Automation
- Data Science
- Machine Learning
- Web Development

For a Data Analyst, Python is mainly used for data cleaning, analysis, automation, and visualization.

---

# 1. Variables

A variable is used to store data.

### Example

```python
name = "Ravi"
age = 25
salary = 50000
Here:
- name stores a string
- age stores an integer
- salary stores a number
2. Data Types
Python provides different data types for storing different kinds of data.
Common Data Types
name = "Ravi"        # str
age = 25             # int
salary = 50000.50    # float
is_active = True     # bool
Main Data Types
Data Type	Example	Purpose
str	"Ravi"	Text
int	25	Whole numbers
float	50000.50	Decimal numbers
bool	True	True/False


3. print()
print() is used to display output.
Example
name = "Ravi"
print(name)
Output:
Ravi
Multiple Values
name = "Ravi"
age = 25

print(name, age)
4. input()
input() is used to take information from the user.
Example
name = input("Enter your name: ")
print(name)
By default, input() returns the value as a string.
5. Type Casting
Type casting means converting one data type into another.
String to Integer
age = int(input("Enter your age: "))
String to Float
salary = float(input("Enter your salary: "))
Integer to String
age = 25
age_text = str(age)
Common functions:
int()
float()
str()
bool()
6. Operators
Operators are used to perform operations on values.
Arithmetic Operators
a = 10
b = 3

print(a + b)   # Addition
print(a - b)   # Subtraction
print(a * b)   # Multiplication
print(a / b)   # Division
print(a % b)   # Modulus
print(a ** b)  # Power
7. Comparison Operators
Comparison operators compare two values.
a = 10
b = 5

print(a > b)
print(a < b)
print(a == b)
print(a != b)
print(a >= b)
print(a <= b)
The result is either True or False.
8. Conditional Statements
Conditional statements are used to make decisions.
if
salary = 75000

if salary > 60000:
    print("High Salary")
if-else
salary = 50000

if salary > 60000:
    print("High Salary")
else:
    print("Regular Salary")
if-elif-else
salary = 75000

if salary >= 80000:
    print("High")
elif salary >= 60000:
    print("Medium")
else:
    print("Low")
Python checks conditions from top to bottom.
9. Logical Operators
Logical operators are used to combine conditions.
AND
Both conditions must be True.
age = 25
salary = 70000

if age > 18 and salary > 60000:
    print("Eligible")
OR
At least one condition must be True.
department = "Engineering"
salary = 50000

if department == "Engineering" or salary > 60000:
    print("Eligible")
NOT
Reverses the condition.
is_active = True

if not is_active:
    print("Inactive")
10. Data Analyst Thinking
When solving a Python problem, first identify:
1. What data do I have?
2. What result do I need?
3. What condition is required?
4. What calculation is required?
5. Which Python concept can solve it?
Example business question:
"Find employees whose salary is greater than ₹60,000."
Thinking:
Data
 ↓
Employee salary

Condition
 ↓
salary > 60000

Python concept
 ↓
if
Code:
salary = 75000

if salary > 60000:
    print("Eligible")
Python Fundamentals Summary
Concept	Purpose
Variable	Store data
Data Type	Define type of data
print()	Display output
input()	Take user input
Type Casting	Convert data types
Operators	Perform calculations/comparisons
if	Check a condition
if-else	Choose between two conditions
if-elif-else	Handle multiple conditions
and	All conditions must be True
or	At least one condition must be True
not	Reverse a condition


Data Analyst Relevance
Python fundamentals are the foundation for:
- Pandas
- NumPy
- Data Cleaning
- Data Analysis
- Data Visualization
- Automation
- Streamlit Applications
Status
Python Day 01 – Fundamentals Completed ✅
