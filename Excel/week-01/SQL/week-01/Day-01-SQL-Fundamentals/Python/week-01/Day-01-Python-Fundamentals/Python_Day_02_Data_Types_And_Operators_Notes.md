# Python Day 02 – Data Types & Operators

## 1. Python Data Types

A data type defines what kind of value a variable contains.

Common Python data types:

- int
- float
- str
- bool
- list
- tuple
- set
- dict

---

# 2. Integer (`int`)

Integers are whole numbers without decimal points.

```python
age = 22
salary = 50000
quantity = 10
3. Float (float)
Float represents numbers containing decimal values.
price = 99.50
percentage = 85.5
Example:
type(price)
Output:
<class 'float'>
4. String (str)
A string is a sequence of characters enclosed in quotes.
name = "Ravi"
city = "Hyderabad"
Example:
print(name)
5. Boolean (bool)
Boolean values represent either True or False.
is_employee = True
is_active = False
Example:
print(is_employee)
6. Checking Data Type
The type() function is used to identify the data type of a value.
x = 100
print(type(x))
Output:
<class 'int'>
Example:
name = "Ravi"
salary = 50000.50
is_active = True

print(type(name))
print(type(salary))
print(type(is_active))
7. Type Casting
Type casting means converting one data type into another.
Integer to Float
x = 10
y = float(x)

print(y)
Output:
10.0
Float to Integer
x = 10.8
y = int(x)

print(y)
Output:
10
The decimal portion is removed.
8. String to Integer
x = "100"
y = int(x)

print(y)
Output:
100
Now y is an integer.
9. Integer to String
x = 100
y = str(x)

print(y)
Output:
100
Now y is a string.
10. Arithmetic Operators
Arithmetic operators are used for mathematical calculations.
Operator	Meaning	Example
+	Addition	10 + 5
-	Subtraction	10 - 5
*	Multiplication	10 * 5
/	Division	10 / 5
//	Floor Division	10 // 3
%	Modulus	10 % 3
**	Exponent	10 ** 2


11. Addition
a = 10
b = 20

result = a + b

print(result)
Output:
30
12. Subtraction
a = 20
b = 10

result = a - b

print(result)
Output:
10
13. Multiplication
price = 500
quantity = 4

total = price * quantity

print(total)
Output:
2000
14. Division
a = 10
b = 2

result = a / b

print(result)
Output:
5.0
The / operator normally returns a float.
15. Floor Division
// returns the floor value of a division.
result = 10 // 3

print(result)
Output:
3
16. Modulus
% returns the remainder.
result = 10 % 3

print(result)
Output:
1
Practical example:
number = 10

if number % 2 == 0:
    print("Even")
17. Exponent
** is used for powers.
result = 5 ** 2

print(result)
Output:
25
18. Comparison Operators
Comparison operators compare two values.
Operator	Meaning
==	Equal to
!=	Not equal to
>	Greater than
<	Less than
>=	Greater than or equal to
<=	Less than or equal to


Example:
salary = 60000

print(salary > 50000)
Output:
True
19. Logical Operators
Logical operators combine conditions.
AND
and returns True when both conditions are true.
age = 25
salary = 60000

print(age > 18 and salary > 50000)
Output:
True
OR
or returns True when at least one condition is true.
age = 17
salary = 60000

print(age > 18 or salary > 50000)
Output:
True
NOT
not reverses the result.
is_active = True

print(not is_active)
Output:
False
20. Assignment Operators
Assignment operators are used to assign or update values.
Operator	Example	Equivalent
=	x = 10	x = 10
+=	x += 5	x = x + 5
-=	x -= 5	x = x - 5
*=	x *= 5	x = x * 5
/=	x /= 5	x = x / 5


Example:
sales = 10000

sales += 2000

print(sales)
Output:
12000
21. Operator Precedence
Python follows an order when evaluating expressions.
Example:
result = 10 + 5 * 2

print(result)
Output:
20
Multiplication is performed before addition.
Parentheses can be used to control the order:
result = (10 + 5) * 2

print(result)
Output:
30
22. Practical Data Analyst Examples
Calculate Revenue
quantity = 10
unit_price = 500

revenue = quantity * unit_price

print(revenue)
Output:
5000
Calculate Profit
sales = 50000
cost = 30000

profit = sales - cost

print(profit)
Output:
20000
Calculate Profit Margin
sales = 50000
profit = 20000

profit_margin = (profit / sales) * 100

print(profit_margin)
Output:
40.0
23. Important Interview Points
- int represents whole numbers.
- float represents decimal numbers.
- str represents text.
- bool represents True or False.
- type() is used to check the data type.
- Type casting converts one data type into another.
- / returns normal division.
- // performs floor division.
- % returns the remainder.
- ** is used for exponentiation.
- == checks equality.
- = assigns a value.
- and, or, and not are logical operators.
- Parentheses can change the order of operations.
Day 02 Summary
Today I learned:
Data Types
int
float
str
bool

type()
Type Casting

Arithmetic Operators
+
-
*
/
//
%
**

Comparison Operators
==
!=
>
<
>=
<=

Logical Operators
and
or
not

Assignment Operators
=
+=
-=
*=
/=

Operator Precedence
Practical Data Analyst Calculations
