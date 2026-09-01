# 📅 Day 03 — Input & Type Conversion

Welcome to **Day 03 of my Python Learning Journey** 🐍🚀

Day 03 lo nenu Python program lo **user nundi information teesukovadam** and aa information ni required data type ki **convert cheyadam** nerchukunnanu.

Day 01 lo Python basics and variables nerchukunnanu.  
Day 02 lo different data types like `str`, `int`, `float`, and `bool` nerchukunnanu.

Day 03 lo ee concepts ni next level ki teesukelli, **user input → type conversion → calculation → output** process ni practice chesanu.

---

# 🎯 Day 03 Learning Goal

The main goal of Day 03 was to understand:

- ⌨️ `input()`
- 🔢 `int()`
- 🔢 `float()`
- 👤 User input
- 🔄 Type conversion
- 📦 Storing user input in variables
- 🧮 Using converted values in calculations
- 🖨️ Displaying results

---

# 📚 Topics Learned

- `input()`
- User input
- Variables with user input
- `int()`
- `float()`
- Type conversion
- String input
- Integer input
- Float input
- Calculations using user input
- Displaying calculated results

---

# 1. ⌨️ `input()` Function

Python lo user nundi information teesukovadaniki `input()` function use chestam.

Example:

```python
name = input("Enter your name: ")

print(name)
```

User input:

```text
Durga Vamsi
```

Output:

```text
Durga Vamsi
```

### 🧠 Key Concept

```text
input()
   ↓
Ask User for Information
   ↓
User Enters Value
   ↓
Value Stored in Variable
```

`input()` function program ni interactive ga chestundi.

---

# 2. 👤 Taking User Input

Example:

```python
product = input("Enter Product: ")

print(product)
```

User:

```text
Dog Food
```

Output:

```text
Dog Food
```

Ikkada user enter chesina `"Dog Food"` value `product` variable lo store avtundi.

```text
User
 ↓
Dog Food
 ↓
product variable
```

---

# 3. 📝 `input()` Always Returns Text

Day 03 lo important concept:

`input()` function user enter chesina value ni normally **string (`str`)** ga return chestundi.

Example:

```python
quantity = input("Enter Quantity: ")
```

User:

```text
2
```

Even though user `2` enter chesadu, `input()` danini text laga receive chestundi.

```text
"2"
 ↓
String
```

Idi calculations chestappudu important.

---

# 4. 🔄 Type Conversion

Oka data type value ni vere data type ki convert cheyadam ni **Type Conversion** antam.

Example:

```python
quantity = "2"
```

Ikkada `quantity` string.

Danni integer ga convert cheyadaniki:

```python
quantity = int("2")
```

Now:

```text
"2"
 ↓
int()
 ↓
2
```

### 🧠 Key Concept

```text
Type Conversion
      ↓
Change Data Type
```

---

# 5. 🔢 `int()` Function

`int()` function value ni integer ga convert cheyadaniki use chestam.

Example:

```python
quantity = int("2")

print(quantity)
```

Output:

```text
2
```

User input tho:

```python
quantity = int(input("Enter Quantity: "))

print(quantity)
```

User:

```text
5
```

Output:

```text
5
```

Ikkada:

```text
input()
   ↓
User enters "5"
   ↓
int()
   ↓
5
   ↓
Integer
```

---

# 6. 🔢 `float()` Function

`float()` function value ni decimal number ga convert cheyadaniki use chestam.

Example:

```python
price = float("1200.50")

print(price)
```

Output:

```text
1200.5
```

User input tho:

```python
price = float(input("Enter Price: "))

print(price)
```

User:

```text
1200.50
```

Output:

```text
1200.5
```

Flow:

```text
input()
   ↓
"1200.50"
   ↓
float()
   ↓
1200.50
   ↓
Float
```

---

# 7. 🧩 String Input

Text information kosam direct ga `input()` use cheyachu.

Example:

```python
product = input("Enter Product: ")
```

User:

```text
Dog Food
```

Then:

```text
product
   ↓
"Dog Food"
   ↓
str
```

No `int()` or `float()` conversion required because product name is text.

---

# 8. 🔢 Integer Input

Whole number input kosam `int()` use chestam.

Example:

```python
quantity = int(input("Enter Quantity: "))
```

User:

```text
2
```

Then:

```text
quantity
   ↓
2
   ↓
int
```

---

# 9. 💰 Float Input

Decimal number input kosam `float()` use chestam.

Example:

```python
price = float(input("Enter Price: "))
```

User:

```text
1200.50
```

Then:

```text
price
   ↓
1200.50
   ↓
float
```

---

# 10. 💻 Basic User Input Example

```python
product = input("Enter Product: ")
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
```

Example user input:

```text
Enter Product: Dog Food
Enter Quantity: 2
Enter Price: 1200.50
```

Output:

```text
Product: Dog Food
Quantity: 2
Price: 1200.5
```

---

# 11. 🧮 User Input + Calculation

Day 03 lo user input values ni calculations lo use cheyadam practice chesanu.

Example:

```python
product = input("Enter Product: ")
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

total = quantity * price

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
print("Total Price:", total)
```

### 📊 Example Input

```text
Enter Product: Dog Food
Enter Quantity: 2
Enter Price: 1200.50
```

### 📊 Output

```text
Product: Dog Food
Quantity: 2
Price: 1200.5
Total Price: 2401.0
```

---

# 🧠 Understanding the Calculation

Given:

```text
Quantity = 2
Price = 1200.50
```

Formula:

```text
Total = Quantity × Price
```

Calculation:

```text
2 × 1200.50
     ↓
2401.00
```

Python:

```python
total = quantity * price
```

---

# 12. 🐾 Real-World Pet Shop Example

Pet Shop lo customer product konnappudu:

```text
Product
   ↓
Quantity
   ↓
Price
   ↓
Total
```

Python lo:

```python
product = input("Enter Product: ")
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

total = quantity * price

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
print("Total Price:", total)
```

This is a simple **billing calculation**.

---

# 💻 Life Care Pet Zone Example

```python
product = input("Enter Product: ")
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

total = quantity * price

print("-------------------------")
print("Life Care Pet Zone")
print("-------------------------")

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
print("Total Price:", total)
```

### 📊 Example Input

```text
Enter Product: Dog Food
Enter Quantity: 2
Enter Price: 1200
```

### 📊 Output

```text
-------------------------
Life Care Pet Zone
-------------------------
Product: Dog Food
Quantity: 2
Price: 1200.0
Total Price: 2400.0
```

---

# 🔍 Python Execution Flow

Day 03 program execution flow:

```text
User
 ↓
Enter Product
 ↓
input()
 ↓
Store Product

User
 ↓
Enter Quantity
 ↓
input()
 ↓
int()
 ↓
Store Integer Quantity

User
 ↓
Enter Price
 ↓
input()
 ↓
float()
 ↓
Store Float Price

Quantity × Price
 ↓
Total
 ↓
print()
 ↓
Output
```

---

# 🔄 Type Conversion Flow

## String to Integer

```python
quantity = int(input("Enter Quantity: "))
```

Flow:

```text
User enters:
"2"

    ↓

input()

    ↓

"2"

    ↓

int()

    ↓

2

    ↓

Integer
```

---

## String to Float

```python
price = float(input("Enter Price: "))
```

Flow:

```text
User enters:
"1200.50"

      ↓

input()

      ↓

"1200.50"

      ↓

float()

      ↓

1200.50

      ↓

Float
```

---

# 🧠 Important Difference

Without conversion:

```python
quantity = input("Enter Quantity: ")
```

`quantity` is normally a string.

With conversion:

```python
quantity = int(input("Enter Quantity: "))
```

`quantity` becomes an integer.

Similarly:

```python
price = input("Enter Price: ")
```

returns text.

But:

```python
price = float(input("Enter Price: "))
```

converts it to a float.

---

# ❌ Why Type Conversion Is Important

Suppose:

```python
quantity = input("Enter Quantity: ")
price = input("Enter Price: ")
```

Both values are normally strings.

If we want to perform numerical calculations, we should convert them.

Correct:

```python
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

total = quantity * price
```

This allows Python to perform numerical calculations correctly.

---

# 🎯 Day 03 Practice Tasks

## Practice Task 1 — Ask Name

```python
name = input("Enter your name: ")

print("Hello", name)
```

Example:

```text
Enter your name: Durga
```

Output:

```text
Hello Durga
```

---

## Practice Task 2 — Ask Product

```python
product = input("Enter Product: ")

print("Product:", product)
```

Example:

```text
Enter Product: Dog Food
```

Output:

```text
Product: Dog Food
```

---

## Practice Task 3 — Ask Quantity

```python
quantity = int(input("Enter Quantity: "))

print("Quantity:", quantity)
```

Example:

```text
Enter Quantity: 5
```

Output:

```text
Quantity: 5
```

---

## Practice Task 4 — Ask Price

```python
price = float(input("Enter Price: "))

print("Price:", price)
```

Example:

```text
Enter Price: 500.50
```

Output:

```text
Price: 500.5
```

---

## Practice Task 5 — Calculate Total

```python
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

total = quantity * price

print("Total:", total)
```

Example:

```text
Enter Quantity: 3
Enter Price: 500
```

Output:

```text
Total: 1500.0
```

---

# 🧪 Day 03 Practice Program

```python
# Life Care Pet Zone
# Product Billing Program

product = input("Enter Product: ")
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

total = quantity * price

print("-------------------------")
print("Life Care Pet Zone")
print("-------------------------")

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
print("Total Price:", total)
```

### 📊 Example Input

```text
Enter Product: Cat Food
Enter Quantity: 3
Enter Price: 900
```

### 📊 Output

```text
-------------------------
Life Care Pet Zone
-------------------------
Product: Cat Food
Quantity: 3
Price: 900.0
Total Price: 2700.0
```

---

# 💡 Business Logic

Day 03 lo simple business calculation practice chesanu.

```text
Product
   ↓
Quantity
   ↓
Price
   ↓
Calculation
   ↓
Total Revenue
```

Formula:

```text
Total = Quantity × Price
```

Python:

```python
total = quantity * price
```

This type of calculation is useful in:

- 🛒 Shopping
- 🧾 Billing
- 💰 Sales
- 📦 Inventory
- 📊 Business Analysis

---

# 🧠 Day 03 Key Concepts

## `input()`

```python
input()
```

User nundi information teesukovadaniki use chestam.

---

## `int()`

```python
int()
```

Value ni integer ga convert chestundi.

Example:

```python
int("5")
```

Result:

```text
5
```

---

## `float()`

```python
float()
```

Value ni decimal number ga convert chestundi.

Example:

```python
float("1200.50")
```

Result:

```text
1200.5
```

---

## Type Conversion

```text
String
  ↓
int()
  ↓
Integer
```

or

```text
String
  ↓
float()
  ↓
Float
```

---

# 📚 Day 03 Quick Reference

| Function | Purpose | Example |
|---|---|---|
| `input()` | User input | `input("Enter Name: ")` |
| `int()` | Convert to integer | `int("10")` |
| `float()` | Convert to float | `float("10.5")` |
| `print()` | Display output | `print(price)` |

---

# 🔑 Important Syntax

## User Input

```python
name = input("Enter Name: ")
```

---

## Integer Input

```python
quantity = int(input("Enter Quantity: "))
```

---

## Float Input

```python
price = float(input("Enter Price: "))
```

---

## Calculation

```python
total = quantity * price
```

---

## Display Result

```python
print("Total:", total)
```

---

# ❌ Common Beginner Mistakes

## Mistake 1 — Forgetting Type Conversion

Incorrect:

```python
quantity = input("Enter Quantity: ")
price = input("Enter Price: ")

total = quantity * price
```

For numerical calculations, input values should be converted to appropriate numeric types.

Correct:

```python
quantity = int(input("Enter Quantity: "))
price = float(input("Enter Price: "))

total = quantity * price
```

---

## Mistake 2 — Using `int()` for Decimal Values

Incorrect:

```python
price = int(input("Enter Price: "))
```

If the user enters:

```text
1200.50
```

`int()` cannot directly convert that decimal text.

Better:

```python
price = float(input("Enter Price: "))
```

---

## Mistake 3 — Forgetting `int()`

Incorrect:

```python
quantity = input("Enter Quantity: ")
```

For numerical quantity calculations, use:

```python
quantity = int(input("Enter Quantity: "))
```

---

## Mistake 4 — Forgetting `float()`

For decimal prices:

```python
price = float(input("Enter Price: "))
```

---

# 🧠 What I Understood in Day 03

Day 03 lo nenu Python program ki user nundi data teesukovadam nerchukunnanu.

`input()` function user nundi information teesukuntundi.

`input()` normally text/string value ni return chestundi.

Numerical calculations kosam:

```text
int()
 ↓
Whole Numbers
```

and

```text
float()
 ↓
Decimal Numbers
```

use chestam.

I also learned how user input ni variables lo store chesi, aa values tho calculations chesi, final result ni `print()` tho display cheyali.

---

# 💭 My Day 03 Learning

Day 03 na Python learning journey lo important step.

Day 01 lo variables nerchukunnanu.

Day 02 lo data types nerchukunnanu.

Day 03 lo user nundi data teesukoni, required data type ki convert chesi, aa data tho calculations cheyadam practice chesanu.

Simple ga:

```text
User Input
   ↓
Store in Variable
   ↓
Convert Data Type
   ↓
Perform Calculation
   ↓
Display Output
```

Real-world example ga **Life Care Pet Zone** product billing ni practice chesanu.

Product name kosam `str`, quantity kosam `int`, price kosam `float` use chesi total amount calculate chesanu.

---

# 📝 What I Learned — Day 03

I learned how to make Python programs interactive using `input()`.

I learned how to take product, quantity, and price information from a user.

I learned that `input()` normally returns a string and that numerical values need to be converted using `int()` or `float()` before performing numerical calculations.

I also learned how to combine:

```text
input()
+
Variables
+
Type Conversion
+
Operators
+
print()
```

to create a simple real-world billing program.

---

# 🏆 Day 03 Achievement

By completing Day 03, I learned:

- ✅ `input()`
- ✅ User input
- ✅ Storing user input in variables
- ✅ `int()`
- ✅ `float()`
- ✅ Type conversion
- ✅ String input
- ✅ Integer input
- ✅ Float input
- ✅ Calculations using user input
- ✅ Displaying calculated results
- ✅ Simple billing logic
- ✅ Real-world Pet Shop example

---

# 🎯 Day 03 Summary

```text
Day 03
   ↓
User Input
   ↓
input()
   ↓
Store Data
   ↓
Type Conversion
   ↓
int()
   ↓
float()
   ↓
Calculations
   ↓
print()
   ↓
Output
```

---

# 📈 Learning Progress

```text
Day 01
Python Basics
   ↓
Day 02
Variables & Data Types
   ↓
Day 03
Input & Type Conversion
   ↓
Day 04
Operators & Calculations
```

---

# 🚀 Next Step

## 📅 Day 04 — Operators & Calculations

In Day 04, I will learn more about Python operators and how to perform different mathematical calculations.

Topics will include:

- Addition `+`
- Subtraction `-`
- Multiplication `*`
- Division `/`
- Modulus `%`

I will also apply these operators to practical business calculations.

---

# 🐍 Python Learning Journey

**Day 03 → Completed ✅**

> **Learn → Practice → Make Mistakes → Understand → Improve.** 🚀