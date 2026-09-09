# 🐍 DAY 16 — List and Dictionary Comprehensions

## 📌 Day 16 Goal

Today we will learn **List Comprehension** and **Dictionary Comprehension**.

These are powerful Python techniques used to create new data from existing data in a shorter and cleaner way.

We will learn:

- List Comprehension
- `for` loop with List Comprehension
- Conditions with List Comprehension
- Filtering data
- Transforming data
- Dictionary Comprehension
- Conditions with Dictionary Comprehension
- Business-data processing
- Pet Shop / Life Care Pet Zone examples

---

# 1️⃣ What is Comprehension?

Comprehension means creating a new collection from existing data using a compact Python syntax.

For example, normally we might write:

```python
numbers = [1, 2, 3, 4, 5]

squares = []

for number in numbers:
    squares.append(number * number)

print(squares)
```

### Output

```text
[1, 4, 9, 16, 25]
```

Using List Comprehension:

```python
numbers = [1, 2, 3, 4, 5]

squares = [number * number for number in numbers]

print(squares)
```

### Output

```text
[1, 4, 9, 16, 25]
```

Same result, but more compact.

---

# 2️⃣ Basic List Comprehension Syntax

The basic structure is:

```python
[new_value for item in collection]
```

Example:

```python
numbers = [1, 2, 3, 4, 5]

double_numbers = [number * 2 for number in numbers]

print(double_numbers)
```

### Output

```text
[2, 4, 6, 8, 10]
```

The meaning is:

```text
Take every number
      ↓
Multiply by 2
      ↓
Create a new list
```

---

# 3️⃣ List Comprehension with Strings

```python
products = ["Dog Food", "Cat Food", "Treats"]

product_names = [product.upper() for product in products]

print(product_names)
```

### Output

```text
['DOG FOOD', 'CAT FOOD', 'TREATS']
```

Here we transformed every product name.

---

# 4️⃣ List Comprehension with Conditions

We can also filter data.

Syntax:

```python
[new_value for item in collection if condition]
```

Example:

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = [
    number
    for number in numbers
    if number % 2 == 0
]

print(even_numbers)
```

### Output

```text
[2, 4, 6]
```

---

# 5️⃣ Filtering Products

Let's use our Pet Shop data.

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]
```

Find expensive products.

Business Rule:

```text
Price >= 1000
```

Using a normal loop:

```python
expensive_products = []

for product in products:
    if product["Price"] >= 1000:
        expensive_products.append(product)

print(expensive_products)
```

Using List Comprehension:

```python
expensive_products = [
    product
    for product in products
    if product["Price"] >= 1000
]

print(expensive_products)
```

### Output

```text
[{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}]
```

---

# 6️⃣ Low Stock Products

Business Rule:

```text
Quantity < 3
```

Using List Comprehension:

```python
low_stock_products = [
    product
    for product in products
    if product["Quantity"] < 3
]

print(low_stock_products)
```

### Output

```text
[{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}]
```

---

# 7️⃣ Get Only Product Names

Sometimes we don't need the complete dictionary.

We only need the product names.

```python
product_names = [
    product["Name"]
    for product in products
]

print(product_names)
```

### Output

```text
['Dog Food', 'Cat Food', 'Treats', 'Bones']
```

This is useful when transforming data.

---

# 8️⃣ Get Only Prices

```python
prices = [
    product["Price"]
    for product in products
]

print(prices)
```

### Output

```text
[1200, 900, 300, 500]
```

---

# 9️⃣ Get Only Quantities

```python
quantities = [
    product["Quantity"]
    for product in products
]

print(quantities)
```

### Output

```text
[2, 3, 5, 4]
```

---

# 🔟 Calculate Revenue Using List Comprehension

Business Rule:

```text
Revenue = Price × Quantity
```

Code:

```python
revenues = [
    product["Price"] * product["Quantity"]
    for product in products
]

print(revenues)
```

### Output

```text
[2400, 2700, 1500, 2000]
```

Now we have the revenue for every product.

---

# 1️⃣1️⃣ Calculate Total Revenue

We can combine List Comprehension with `sum()`.

```python
total_revenue = sum(
    product["Price"] * product["Quantity"]
    for product in products
)

print(total_revenue)
```

### Output

```text
8600
```

Business calculation:

```text
Dog Food = 1200 × 2 = 2400
Cat Food = 900 × 3 = 2700
Treats   = 300 × 5 = 1500
Bones    = 500 × 4 = 2000

Total Revenue = 8600
```

---

# 1️⃣2️⃣ Total Stock

We can calculate total stock using `sum()`.

```python
total_stock = sum(
    product["Quantity"]
    for product in products
)

print(total_stock)
```

### Output

```text
14
```

---

# 1️⃣3️⃣ Dictionary Comprehension

List Comprehension creates a:

```python
list
```

Dictionary Comprehension creates a:

```python
dictionary
```

Syntax:

```python
{key: value for item in collection}
```

Example:

```python
numbers = [1, 2, 3, 4, 5]

squares = {
    number: number * number
    for number in numbers
}

print(squares)
```

### Output

```text
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

# 1️⃣4️⃣ Product Price Dictionary

Create a dictionary containing:

```text
Product Name → Price
```

```python
product_prices = {
    product["Name"]: product["Price"]
    for product in products
}

print(product_prices)
```

### Output

```text
{
    'Dog Food': 1200,
    'Cat Food': 900,
    'Treats': 300,
    'Bones': 500
}
```

This is useful for creating simplified data structures.

---

# 1️⃣5️⃣ Product Quantity Dictionary

```python
product_stock = {
    product["Name"]: product["Quantity"]
    for product in products
}

print(product_stock)
```

### Output

```text
{
    'Dog Food': 2,
    'Cat Food': 3,
    'Treats': 5,
    'Bones': 4
}
```

---

# 1️⃣6️⃣ Dictionary Comprehension with Condition

We can filter dictionary data.

Find products with price >= 500.

```python
expensive_products = {
    product["Name"]: product["Price"]
    for product in products
    if product["Price"] >= 500
}

print(expensive_products)
```

### Output

```text
{
    'Dog Food': 1200,
    'Cat Food': 900,
    'Bones': 500
}
```

---

# 1️⃣7️⃣ Low Stock Dictionary

```python
low_stock = {
    product["Name"]: product["Quantity"]
    for product in products
    if product["Quantity"] < 3
}

print(low_stock)
```

### Output

```text
{
    'Dog Food': 2
}
```

---

# 1️⃣8️⃣ Revenue Dictionary

We can create:

```text
Product Name → Revenue
```

```python
product_revenue = {
    product["Name"]: product["Price"] * product["Quantity"]
    for product in products
}

print(product_revenue)
```

### Output

```text
{
    'Dog Food': 2400,
    'Cat Food': 2700,
    'Treats': 1500,
    'Bones': 2000
}
```

This is very useful for business analysis.

---

# 1️⃣9️⃣ Find High Revenue Products

Suppose we want products with revenue >= 2000.

```python
high_revenue_products = {
    product["Name"]: product["Price"] * product["Quantity"]
    for product in products
    if product["Price"] * product["Quantity"] >= 2000
}

print(high_revenue_products)
```

### Output

```text
{
    'Dog Food': 2400,
    'Cat Food': 2700,
    'Bones': 2000
}
```

---

# 2️⃣0️⃣ List Comprehension + Function

We can use a function inside List Comprehension.

```python
def calculate_revenue(product):
    return product["Price"] * product["Quantity"]


revenues = [
    calculate_revenue(product)
    for product in products
]

print(revenues)
```

### Output

```text
[2400, 2700, 1500, 2000]
```

This makes our code reusable.

---

# 2️⃣1️⃣ List Comprehension + Condition + Function

```python
def calculate_revenue(product):
    return product["Price"] * product["Quantity"]


high_revenue = [
    product["Name"]
    for product in products
    if calculate_revenue(product) >= 2000
]

print(high_revenue)
```

### Output

```text
['Dog Food', 'Cat Food', 'Bones']
```

This combines multiple concepts:

```text
Function
   +
List
   +
Dictionary
   +
Condition
   +
Comprehension
```

---

# 2️⃣2️⃣ Normal Loop vs List Comprehension

### Normal Loop

```python
prices = []

for product in products:
    prices.append(product["Price"])
```

### List Comprehension

```python
prices = [
    product["Price"]
    for product in products
]
```

Both produce the same result.

The comprehension version is shorter.

---

# 2️⃣3️⃣ Important Rule

Don't use comprehension just because it is shorter.

If the logic becomes difficult to understand, a normal `for` loop may be better.

### Simple logic

```python
prices = [
    product["Price"]
    for product in products
]
```

Good.

### Complex business logic

A normal function + loop may be easier to maintain.

Readable code is more important than writing the shortest possible code.

---

# 2️⃣4️⃣ Complete Day 16 Program

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]


def calculate_revenue(product):
    return product["Price"] * product["Quantity"]


# Product Names
product_names = [
    product["Name"]
    for product in products
]


# Product Prices
prices = [
    product["Price"]
    for product in products
]


# Product Revenues
revenues = [
    calculate_revenue(product)
    for product in products
]


# Expensive Products
expensive_products = [
    product["Name"]
    for product in products
    if product["Price"] >= 1000
]


# Low Stock Products
low_stock_products = [
    product["Name"]
    for product in products
    if product["Quantity"] < 3
]


# Total Revenue
total_revenue = sum(revenues)


# Total Stock
total_stock = sum(
    product["Quantity"]
    for product in products
)


# Product Revenue Dictionary
product_revenue = {
    product["Name"]: calculate_revenue(product)
    for product in products
}


print("Product Names:", product_names)
print("Prices:", prices)
print("Revenues:", revenues)
print("Expensive Products:", expensive_products)
print("Low Stock Products:", low_stock_products)
print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)
print("Product Revenue:", product_revenue)
```

---

# 2️⃣5️⃣ Expected Output

```text
Product Names: ['Dog Food', 'Cat Food', 'Treats', 'Bones']

Prices: [1200, 900, 300, 500]

Revenues: [2400, 2700, 1500, 2000]

Expensive Products: ['Dog Food']

Low Stock Products: ['Dog Food']

Total Revenue: 8600

Total Stock: 14

Product Revenue:
{
    'Dog Food': 2400,
    'Cat Food': 2700,
    'Treats': 1500,
    'Bones': 2000
}
```

---

# 2️⃣6️⃣ Day 16 Practice Tasks

## 🟢 Task 1 — Product Names

Create a list containing only product names.

---

## 🟢 Task 2 — Product Prices

Create a list containing only product prices.

---

## 🟢 Task 3 — Product Quantities

Create a list containing only product quantities.

---

## 🟡 Task 4 — Revenue List

Create a list containing revenue for every product.

```text
Revenue = Price × Quantity
```

---

## 🟡 Task 5 — Expensive Products

Create a list containing products where:

```text
Price >= 1000
```

---

## 🟡 Task 6 — Low Stock Products

Create a list containing products where:

```text
Quantity < 3
```

---

## 🟠 Task 7 — Product Price Dictionary

Create:

```text
Product Name → Price
```

Expected:

```text
{
    'Dog Food': 1200,
    'Cat Food': 900,
    'Treats': 300,
    'Bones': 500
}
```

---

## 🟠 Task 8 — Product Revenue Dictionary

Create:

```text
Product Name → Revenue
```

---

## 🔴 Task 9 — High Revenue Products

Create a dictionary containing products whose revenue is:

```text
>= 2000
```

---

## 🔴 Task 10 — Mini Business Report

Using List and Dictionary Comprehension, calculate:

```text
Total Products
Total Revenue
Total Stock
Expensive Products
Low Stock Products
Product Revenue
```

---

# 2️⃣7️⃣ Common Mistakes

### ❌ Mistake 1 — Forgetting `for`

Wrong:

```python
prices = [product["Price"] products]
```

Correct:

```python
prices = [
    product["Price"]
    for product in products
]
```

---

### ❌ Mistake 2 — Wrong Dictionary Key

Wrong:

```python
product["price"]
```

Correct:

```python
product["Price"]
```

Python is case-sensitive.

---

### ❌ Mistake 3 — Confusing List and Dictionary Comprehension

List:

```python
[value for item in data]
```

Dictionary:

```python
{key: value for item in data}
```

---

### ❌ Mistake 4 — Forgetting the Condition

Filtering requires:

```python
if
```

Example:

```python
[
    product
    for product in products
    if product["Price"] >= 1000
]
```

---

# 2️⃣8️⃣ Day 15 vs Day 16

| Day | Main Concept |
|---|---|
| Day 15 | Filtering & Sorting Dictionary Data |
| Day 16 | List & Dictionary Comprehensions |

### Day 15

We learned:

```text
Filter
Sort
max()
min()
lambda
```

### Day 16

We learn:

```text
Transform
Filter
Create Lists
Create Dictionaries
Comprehensions
```

So Day 16 builds directly on the data-processing skills from Day 15.

---

# 2️⃣9️⃣ Data Engineering Connection 🔥

Comprehensions are useful when working with structured data.

For example:

```text
Raw Data
   ↓
Extract Values
   ↓
Filter Data
   ↓
Transform Data
   ↓
Create New Structure
   ↓
Analysis
```

You are now learning the foundation for:

```text
Python
   ↓
Data Processing
   ↓
Pandas
   ↓
SQL
   ↓
ETL
   ↓
Data Pipelines
   ↓
Data Engineering 🚀
```

When you later work with CSV, JSON, APIs, and Pandas DataFrames, the same thinking will continue:

```text
Read
→ Filter
→ Transform
→ Aggregate
→ Analyze
```

---

# 📌 Day 16 Summary

Today I learned:

- ✅ List Comprehension
- ✅ Dictionary Comprehension
- ✅ Filtering with comprehensions
- ✅ Transforming data
- ✅ Extracting dictionary values
- ✅ `sum()`
- ✅ Comprehension with functions
- ✅ Comprehension with conditions
- ✅ Product revenue calculation
- ✅ Business-data processing
- ✅ Creating simplified data structures
- ✅ List of dictionaries processing

---

# 📈 Python Learning Progress

```text
Day 01 → Python Basics
Day 02 → Variables & Data Types
Day 03 → Input & Type Conversion
Day 04 → Operators & Calculations
Day 05 → Conditional Statements
Day 06 → For Loops & Iteration
Day 07 → Lists
Day 08 → Multiple Lists & Data Handling
Day 09 → Sales & Inventory Analysis
Day 10 → Functions
Day 11 → Functions & Business Logic
Day 12 → Dictionaries & List of Dictionaries
Day 13 → Dictionary Data Processing & Business Analysis
Day 14 → Dictionary Business Analysis
Day 15 → Filtering & Sorting Dictionary Data
Day 16 → List & Dictionary Comprehensions
```

---

# 🚀 Next Step — Day 17

Next we can continue with **advanced Python data processing** and solve more realistic business-data problems.

```text
Python Basics
      ↓
Lists
      ↓
Dictionaries
      ↓
Functions
      ↓
Business Logic
      ↓
Filtering
      ↓
Sorting
      ↓
Comprehensions
      ↓
Advanced Data Processing
      ↓
Pandas
      ↓
SQL
      ↓
ETL
      ↓
Data Engineering 🚀
```

---

# 👨‍💻 Developed By

## **Durga Vamsi**

🐍 Python Learning Journey  
📊 Data Engineering Goal  
🚀 Learning by Building Real-World Business Examples