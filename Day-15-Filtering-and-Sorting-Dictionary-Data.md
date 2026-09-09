# 🐍 DAY 15 — Dictionary Data Processing: Sorting & Filtering

## 📌 Day 15 Goal

Today we will take the **List of Dictionaries** concepts from Day 12–14 and learn how to perform more useful **data processing**.

We will focus on:

- Filtering dictionary data
- Sorting dictionary data
- Finding highest and lowest values
- Using `sorted()`
- Using `key`
- Using `lambda`
- Combining `sorted()` with dictionaries
- Business analysis using product data

These concepts are very useful in **Data Engineering**, because real-world data often needs to be **filtered, sorted, and analyzed** before further processing.

---

# 1️⃣ What is Data Processing?

Data processing means taking raw data and converting it into useful information.

For example:

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]
```

This is raw business data.

We can process this data to answer questions like:

- Which products are expensive?
- Which products have low stock?
- Which product has the highest price?
- Which product has the lowest price?
- Which product has the highest revenue?
- How can we sort products by price?
- How can we show only products with quantity below 4?

---

# 2️⃣ Filtering Data

Filtering means selecting only the records that satisfy a condition.

Example:

```python
for product in products:
    if product["Price"] >= 1000:
        print(product)
```

### Output:

```text
{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
```

Here we filtered products where:

```text
Price >= 1000
```

---

# 3️⃣ Filtering Low Stock Products

Business Rule:

```text
Low Stock = Quantity < 3
```

Code:

```python
for product in products:
    if product["Quantity"] < 3:
        print(product["Name"])
```

### Output:

```text
Dog Food
```

This is useful for inventory management.

---

# 4️⃣ Filtering Normal Stock Products

We can also find products that have enough stock.

```python
for product in products:
    if product["Quantity"] >= 3:
        print(product["Name"])
```

### Output:

```text
Cat Food
Treats
Bones
```

---

# 5️⃣ Sorting Data

Sorting means arranging data in a specific order.

For example:

```text
100
200
300
400
```

is ascending order.

And:

```text
400
300
200
100
```

is descending order.

Python provides:

```python
sorted()
```

for sorting data.

---

# 6️⃣ Basic `sorted()`

Example:

```python
prices = [1200, 900, 300, 500]

sorted_prices = sorted(prices)

print(sorted_prices)
```

### Output:

```text
[300, 500, 900, 1200]
```

This is ascending order.

---

# 7️⃣ Descending Order

Use:

```python
reverse=True
```

Example:

```python
prices = [1200, 900, 300, 500]

sorted_prices = sorted(prices, reverse=True)

print(sorted_prices)
```

### Output:

```text
[1200, 900, 500, 300]
```

---

# 8️⃣ Sorting a List of Dictionaries

Our data is not a simple list.

It contains dictionaries:

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]
```

We want to sort products based on:

```text
Price
```

We can use:

```python
key=lambda
```

---

# 9️⃣ Understanding `lambda`

A `lambda` is a small anonymous function.

Example:

```python
square = lambda x: x * x

print(square(5))
```

### Output:

```text
25
```

Instead of writing:

```python
def square(x):
    return x * x
```

we can write:

```python
lambda x: x * x
```

---

# 🔟 Sorting Dictionaries by Price

```python
sorted_products = sorted(
    products,
    key=lambda product: product["Price"]
)

for product in sorted_products:
    print(product)
```

### Output:

```text
{'Name': 'Treats', 'Price': 300, 'Quantity': 5}
{'Name': 'Bones', 'Price': 500, 'Quantity': 4}
{'Name': 'Cat Food', 'Price': 900, 'Quantity': 3}
{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
```

Now products are sorted by **Price from lowest to highest**.

---

# 1️⃣1️⃣ Sort Products by Highest Price

Use:

```python
reverse=True
```

Example:

```python
sorted_products = sorted(
    products,
    key=lambda product: product["Price"],
    reverse=True
)

for product in sorted_products:
    print(product["Name"], product["Price"])
```

### Output:

```text
Dog Food 1200
Cat Food 900
Bones 500
Treats 300
```

---

# 1️⃣2️⃣ Sort Products by Quantity

We can sort using:

```python
product["Quantity"]
```

Example:

```python
sorted_products = sorted(
    products,
    key=lambda product: product["Quantity"]
)

for product in sorted_products:
    print(product["Name"], product["Quantity"])
```

### Output:

```text
Dog Food 2
Cat Food 3
Bones 4
Treats 5
```

---

# 1️⃣3️⃣ Sort Products by Highest Quantity

```python
sorted_products = sorted(
    products,
    key=lambda product: product["Quantity"],
    reverse=True
)

for product in sorted_products:
    print(product["Name"], product["Quantity"])
```

### Output:

```text
Treats 5
Bones 4
Cat Food 3
Dog Food 2
```

---

# 1️⃣4️⃣ Find Highest Price Product

We can use:

```python
max()
```

Example:

```python
highest_price_product = max(
    products,
    key=lambda product: product["Price"]
)

print(highest_price_product)
```

### Output:

```text
{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
```

---

# 1️⃣5️⃣ Find Lowest Price Product

Use:

```python
min()
```

Example:

```python
lowest_price_product = min(
    products,
    key=lambda product: product["Price"]
)

print(lowest_price_product)
```

### Output:

```text
{'Name': 'Treats', 'Price': 300, 'Quantity': 5}
```

---

# 1️⃣6️⃣ Calculate Product Revenue

Business Rule:

```text
Revenue = Price × Quantity
```

Function:

```python
def calculate_revenue(product):
    return product["Price"] * product["Quantity"]
```

Example:

```python
for product in products:
    revenue = calculate_revenue(product)

    print(product["Name"], revenue)
```

### Output:

```text
Dog Food 2400
Cat Food 2700
Treats 1500
Bones 2000
```

---

# 1️⃣7️⃣ Find Highest Revenue Product

Now we can combine:

- Dictionaries
- Functions
- `max()`
- `lambda`
- Business logic

```python
highest_revenue_product = max(
    products,
    key=lambda product: product["Price"] * product["Quantity"]
)

print(highest_revenue_product)
```

### Output:

```text
{'Name': 'Cat Food', 'Price': 900, 'Quantity': 3}
```

Because:

```text
Dog Food  = 1200 × 2 = 2400
Cat Food  = 900 × 3  = 2700
Treats   = 300 × 5  = 1500
Bones    = 500 × 4  = 2000
```

So:

```text
Highest Revenue = Cat Food
Revenue = 2700
```

---

# 1️⃣8️⃣ Sort Products by Revenue

We can also sort products based on revenue.

```python
sorted_products = sorted(
    products,
    key=lambda product: product["Price"] * product["Quantity"],
    reverse=True
)

for product in sorted_products:
    revenue = product["Price"] * product["Quantity"]

    print(product["Name"], revenue)
```

### Output:

```text
Cat Food 2700
Dog Food 2400
Bones 2000
Treats 1500
```

---

# 1️⃣9️⃣ Filter Expensive Products

Business Rule:

```text
Expensive Product = Price >= 1000
```

```python
expensive_products = []

for product in products:
    if product["Price"] >= 1000:
        expensive_products.append(product)

for product in expensive_products:
    print(product["Name"])
```

### Output:

```text
Dog Food
```

---

# 2️⃣0️⃣ Filter Low Stock Products

Business Rule:

```text
Low Stock = Quantity < 3
```

```python
low_stock_products = []

for product in products:
    if product["Quantity"] < 3:
        low_stock_products.append(product)

for product in low_stock_products:
    print(product["Name"])
```

### Output:

```text
Dog Food
```

---

# 2️⃣1️⃣ Filtering + Sorting Together

We can first filter products and then sort them.

Example:

Find products with price greater than or equal to 500 and sort them by price.

```python
filtered_products = []

for product in products:
    if product["Price"] >= 500:
        filtered_products.append(product)

sorted_products = sorted(
    filtered_products,
    key=lambda product: product["Price"]
)

for product in sorted_products:
    print(product["Name"], product["Price"])
```

### Output:

```text
Bones 500
Cat Food 900
Dog Food 1200
```

This is an important data-processing pattern:

```text
Raw Data
   ↓
Filter
   ↓
Sort
   ↓
Analysis
```

---

# 2️⃣2️⃣ Complete Business Analysis

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]


def calculate_revenue(product):
    return product["Price"] * product["Quantity"]


total_revenue = 0
total_stock = 0

for product in products:

    revenue = calculate_revenue(product)

    total_revenue += revenue
    total_stock += product["Quantity"]

    print(
        product["Name"],
        "Revenue:",
        revenue
    )


print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)


highest_price = max(
    products,
    key=lambda product: product["Price"]
)

lowest_price = min(
    products,
    key=lambda product: product["Price"]
)

highest_revenue = max(
    products,
    key=lambda product: product["Price"] * product["Quantity"]
)


print("Highest Price Product:", highest_price["Name"])
print("Lowest Price Product:", lowest_price["Name"])
print("Highest Revenue Product:", highest_revenue["Name"])
```

---

# 2️⃣3️⃣ Important Functions Learned

| Function | Purpose |
|---|---|
| `len()` | Count items |
| `sorted()` | Sort data |
| `max()` | Find maximum |
| `min()` | Find minimum |
| `lambda` | Small function |
| `append()` | Add item to list |

---

# 2️⃣4️⃣ Important Sorting Syntax

### Ascending

```python
sorted(data, key=lambda x: x["Price"])
```

### Descending

```python
sorted(data, key=lambda x: x["Price"], reverse=True)
```

### Highest value

```python
max(data, key=lambda x: x["Price"])
```

### Lowest value

```python
min(data, key=lambda x: x["Price"])
```

---

# 2️⃣5️⃣ Day 15 Practice Tasks

## 🟢 Task 1 — Sort by Price

Sort products from lowest price to highest price.

---

## 🟢 Task 2 — Sort by Price Descending

Sort products from highest price to lowest price.

---

## 🟢 Task 3 — Sort by Quantity

Sort products based on quantity.

---

## 🟡 Task 4 — Highest Price

Find the product with the highest price.

---

## 🟡 Task 5 — Lowest Price

Find the product with the lowest price.

---

## 🟡 Task 6 — Highest Revenue

Find the product with the highest revenue.

Use:

```text
Revenue = Price × Quantity
```

---

## 🟠 Task 7 — Expensive Products

Find products where:

```text
Price >= 1000
```

---

## 🟠 Task 8 — Low Stock

Find products where:

```text
Quantity < 3
```

---

## 🔴 Task 9 — Sort by Revenue

Sort all products from highest revenue to lowest revenue.

---

## 🔴 Task 10 — Mini Product Report

Create a report containing:

```text
Total Products
Total Revenue
Total Stock
Highest Price Product
Lowest Price Product
Highest Revenue Product
Expensive Products Count
Low Stock Products Count
```

---

# 2️⃣6️⃣ Day 15 Mini Project 🚀

## 🐾 Life Care Pet Zone — Product Analysis

Use:

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]
```

Build a program that can:

1. Calculate revenue for every product
2. Calculate total revenue
3. Calculate total stock
4. Find expensive products
5. Find low-stock products
6. Find highest price product
7. Find lowest price product
8. Find highest revenue product
9. Sort products by price
10. Sort products by revenue

---

# 2️⃣7️⃣ Common Mistakes

### ❌ Mistake 1 — Wrong Dictionary Key

```python
product["price"]
```

But dictionary contains:

```python
"Price"
```

Python is case-sensitive.

Correct:

```python
product["Price"]
```

---

### ❌ Mistake 2 — Forgetting `reverse=True`

For highest-to-lowest sorting:

```python
sorted(
    products,
    key=lambda product: product["Price"],
    reverse=True
)
```

---

### ❌ Mistake 3 — Sorting Without `key`

This will not correctly sort dictionaries by price:

```python
sorted(products)
```

Use:

```python
sorted(
    products,
    key=lambda product: product["Price"]
)
```

---

### ❌ Mistake 4 — Confusing Price and Revenue

Price:

```text
Price
```

Revenue:

```text
Price × Quantity
```

Example:

```text
900 × 3 = 2700
```

---

# 2️⃣8️⃣ Day 14 vs Day 15

| Day | Main Focus |
|---|---|
| Day 14 | Dictionary Business Analysis |
| Day 15 | Filtering & Sorting Dictionary Data |

Day 14 focused mainly on **calculating and analyzing** data.

Day 15 adds more powerful **data processing** techniques:

```text
Filter
Sort
Maximum
Minimum
Lambda
Business Analysis
```

---

# 2️⃣9️⃣ Data Engineering Connection 🔥

In Data Engineering, raw data usually needs processing before it can be used.

A simple workflow is:

```text
Raw Data
   ↓
Read Data
   ↓
Filter Data
   ↓
Transform Data
   ↓
Sort / Aggregate
   ↓
Store Data
   ↓
Analytics
```

Today you practiced important building blocks:

```text
List of Dictionaries
        ↓
Filtering
        ↓
Sorting
        ↓
Business Logic
        ↓
Analysis
```

Later, these concepts will help when working with:

- CSV files
- JSON data
- APIs
- Pandas
- SQL
- ETL pipelines
- Data transformation

---

# 📌 Day 15 Summary

Today I learned:

- ✅ Dictionary data processing
- ✅ Filtering data
- ✅ Sorting data
- ✅ `sorted()`
- ✅ `reverse=True`
- ✅ `key`
- ✅ `lambda`
- ✅ `max()`
- ✅ `min()`
- ✅ Sorting dictionaries
- ✅ Finding highest price
- ✅ Finding lowest price
- ✅ Finding highest revenue
- ✅ Filtering expensive products
- ✅ Filtering low-stock products
- ✅ Combining filtering and sorting
- ✅ Business analysis using dictionaries

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
```

---

# 🚀 Next Step — Day 16

Next, we can move toward **advanced data processing with Lists & Dictionaries**, including more realistic business-data problems and reusable logic.

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
Filtering & Sorting
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