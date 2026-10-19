# Day 1 — Python Fundamentals

## 1. What is Python?

Python is a high-level, interpreted programming language.

### Why Python for Data Analytics?

- Easy to learn
- Used for data cleaning
- Used for data analysis
- Used for automation
- Used with Pandas, NumPy, Matplotlib and Scikit-learn

---

## 2. Python Syntax

Python uses indentation instead of `{}`.

    name = "Indra"

    if name == "Indra":
        print("Welcome Indra")

---

## 3. Comments

Comments are used to explain code.

    # This is a single-line comment

    """
    This is a
    multi-line comment
    """

---

## 4. Variables

A variable stores a value.

    name = "Indra"
    age = 22
    salary = 30000

### Multiple Variables

    name, age, salary = "Indra", 22, 30000

---

## 5. Data Types

Main Python data types:

- int
- float
- str
- bool
- list
- tuple
- set
- dict
- NoneType

### Check Data Type

    x = 100
    print(type(x))

Output:

    <class 'int'>

---

## 6. Integer

Integer means whole number.

    age = 22
    count = 100
    sales = 5000

---

## 7. Float

Float means decimal number.

    price = 99.99
    salary = 35000.50
    rating = 4.5

---

## 8. String

String means text.

    name = "Indra"
    city = "Hyderabad"

### String Indexing

    name = "Indra"

    print(name[0])
    print(name[1])
    print(name[-1])

Output:

    I
    n
    a

---

## 9. Boolean

Boolean has two values:

- True
- False

    is_active = True
    is_completed = False

---

## 10. Type Conversion

Convert one data type into another.

### String to Integer

    x = "100"
    x = int(x)
    print(x)

### Integer to Float

    x = 100
    x = float(x)
    print(x)

### Integer to String

    x = 100
    x = str(x)
    print(x)

### Common Conversion Functions

    int()
    float()
    str()
    bool()

---

## 11. Input

`input()` is used to take user input.

    name = input("Enter your name: ")
    print(name)

### Input as Integer

    age = int(input("Enter your age: "))
    print(age)

---

## 12. Print

`print()` displays output.

    name = "Indra"
    age = 22

    print(name)
    print(age)

### Multiple Values

    print("Name:", name)
    print("Age:", age)

---

## 13. Arithmetic Operators

| Operator | Meaning | Example |
|----------|---------|---------|
| + | Addition | 10 + 5 |
| - | Subtraction | 10 - 5 |
| * | Multiplication | 10 * 5 |
| / | Division | 10 / 5 |
| // | Floor Division | 10 // 3 |
| % | Modulus | 10 % 3 |
| ** | Power | 10 ** 2 |

### Example

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

## 14. Comparison Operators

Comparison operators return `True` or `False`.

| Operator | Meaning |
|----------|---------|
| == | Equal |
| != | Not Equal |
| > | Greater Than |
| < | Less Than |
| >= | Greater Than or Equal |
| <= | Less Than or Equal |

### Example

    a = 10
    b = 5

    print(a == b)
    print(a != b)
    print(a > b)
    print(a < b)
    print(a >= b)
    print(a <= b)

---

## 15. Logical Operators

### AND

Returns True when both conditions are True.

    age = 25
    salary = 40000

    print(age > 18 and salary > 30000)

### OR

Returns True when at least one condition is True.

    age = 17
    salary = 40000

    print(age > 18 or salary > 30000)

### NOT

Reverses the result.

    is_active = True

    print(not is_active)

---

## 16. Assignment Operators

    x = 10

    x += 5
    print(x)

    x -= 2
    print(x)

    x *= 2
    print(x)

    x /= 2
    print(x)

Common operators:

    =
    +=
    -=
    *=
    /=

---

## 17. Strings

### String Concatenation

    first_name = "Muchugiri"
    last_name = "Indra"

    full_name = first_name + " " + last_name

    print(full_name)

### String Length

    name = "Indra"
    print(len(name))

---

## 18. String Methods

### lower()

    name = "INDRA"
    print(name.lower())

### upper()

    name = "indra"
    print(name.upper())

### strip()

Removes spaces from beginning and end.

    name = "  Indra  "
    print(name.strip())

### replace()

    name = "Indra"
    print(name.replace("Indra", "Data Analyst"))

### split()

    text = "Python SQL Excel"
    print(text.split())

---

## 19. f-Strings

Used to insert variables inside strings.

    name = "Indra"
    age = 22

    print(f"My name is {name} and I am {age} years old.")

---

## 20. Lists

List stores multiple values.

    skills = ["SQL", "Python", "Excel", "Power BI"]

    print(skills)

### Access List Item

    print(skills[0])
    print(skills[1])

### Add Item

    skills.append("Pandas")

### Remove Item

    skills.remove("Excel")

### List Length

    print(len(skills))

---

## 21. Tuples

Tuple stores multiple values and cannot be changed.

    coordinates = (10, 20)

    print(coordinates)

Access:

    print(coordinates[0])

---

## 22. Sets

Set stores unique values.

    numbers = {10, 20, 20, 30, 30}

    print(numbers)

Duplicate values are removed.

---

## 23. Dictionaries

Dictionary stores data in key-value pairs.

    employee = {
        "name": "Indra",
        "age": 22,
        "role": "Data Analyst",
        "salary": 30000
    }

    print(employee)

### Access Value

    print(employee["name"])
    print(employee["role"])

### Add New Value

    employee["city"] = "Hyderabad"

### Update Value

    employee["salary"] = 35000

---

## 24. None

`None` represents no value.

    result = None
    print(result)

---

## 25. Conditional Statements

### if

    age = 22

    if age >= 18:
        print("Eligible")

### if-else

    age = 16

    if age >= 18:
        print("Eligible")
    else:
        print("Not Eligible")

### if-elif-else

    marks = 75

    if marks >= 90:
        print("A")
    elif marks >= 60:
        print("B")
    else:
        print("C")

---

## 26. Nested if

    age = 25
    salary = 40000

    if age >= 18:
        if salary >= 30000:
            print("Eligible")

---

## 27. Basic For Loop

Used to repeat code.

    for i in range(5):
        print(i)

Output:

    0
    1
    2
    3
    4

### Loop Through List

    skills = ["SQL", "Python", "Excel"]

    for skill in skills:
        print(skill)

---

## 28. While Loop

Runs while condition is True.

    count = 1

    while count <= 5:
        print(count)
        count += 1

---

## 29. break

Stops the loop.

    for i in range(10):

        if i == 5:
            break

        print(i)

---

## 30. continue

Skips the current iteration.

    for i in range(5):

        if i == 2:
            continue

        print(i)

---

## 31. range()

`range()` generates a sequence of numbers.

    range(5)

    for i in range(1, 6):
        print(i)

Output:

    1
    2
    3
    4
    5

---

## 32. Functions

Function is a reusable block of code.

    def greet():
        print("Hello Indra")

    greet()

---

## 33. Function with Parameters

    def greet(name):
        print(f"Hello {name}")

    greet("Indra")

---

## 34. Function with Return

    def add(a, b):
        return a + b

    result = add(10, 20)

    print(result)

---

## 35. Basic Exception Handling

Used to handle errors.

    try:
        number = int(input("Enter number: "))
        print(number)

    except ValueError:
        print("Please enter a valid number")

---

## 36. Important Python Functions

    print()
    input()
    type()
    len()
    int()
    float()
    str()
    bool()
    range()

---

## 37. Data Analyst Example

    sales = [1000, 1500, 2000, 1200, 1800]

    total_sales = sum(sales)

    average_sales = total_sales / len(sales)

    print("Total Sales:", total_sales)
    print("Average Sales:", average_sales)

Output:

    Total Sales: 7500
    Average Sales: 1500.0

---

## 38. Data Analyst Thinking

When you get a Python problem:

    1. Understand the requirement
    2. Identify the data
    3. Choose the data type
    4. Apply the logic
    5. Check the output

---

## 39. Interview Quick Notes

### What is Python?

Python is a high-level, interpreted and easy-to-use programming language widely used for data analysis, automation and machine learning.

### List vs Tuple

    List   → Mutable
    Tuple  → Immutable

### List vs Set

    List → Allows duplicates
    Set  → Stores unique values

### == vs =

    =  → Assignment
    == → Comparison

### / vs //

    /  → Normal division
    // → Floor division

### break vs continue

    break    → Stops loop
    continue → Skips current iteration

---

## 40. Day 1 Practice

### Practice 1

Create variables for:

    Name
    Age
    City
    Salary
    Role

Print all values.

### Practice 2

Create two numbers and perform:

    Addition
    Subtraction
    Multiplication
    Division
    Modulus

### Practice 3

Create a list of 5 Data Analyst skills and print each skill using a loop.

### Practice 4

Create a dictionary containing:

    Name
    Age
    Role
    Skills
    City

Print each value.

### Practice 5

Check whether a number is:

    Positive
    Negative
    Zero

### Practice 6

Create a list of sales values and calculate:

    Total Sales
    Average Sales
    Maximum Sales
    Minimum Sales

### Practice 7

Write a function that accepts salary and returns:

    High Salary
    Medium Salary
    Low Salary

---

## Day 1 Checklist

- [x] Python Introduction
- [x] Syntax
- [x] Variables
- [x] Data Types
- [x] Type Conversion
- [x] Input / Output
- [x] Operators
- [x] Strings
- [x] Lists
- [x] Tuples
- [x] Sets
- [x] Dictionaries
- [x] if / elif / else
- [x] for Loop
- [x] while Loop
- [x] break / continue
- [x] Functions
- [x] Exception Handling
- [x] Data Analyst Example
- [x] Practice Questions

---

## Day 1 Summary

    Python Basics
         ↓
    Variables & Data Types
         ↓
    Operators
         ↓
    Strings & Collections
         ↓
    Conditions
         ↓
    Loops
         ↓
    Functions
         ↓
    Basic Data Analysis

**Day 1 completed — Python Fundamentals**
