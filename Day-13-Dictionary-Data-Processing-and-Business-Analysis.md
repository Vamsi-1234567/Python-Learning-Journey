# 🐍 Python Learning Journey — Day 13

# 📅 Day 13 — Dictionary Data Processing & Business Analysis

Welcome to **Day 13** of my Python Learning Journey! 🚀

Day 12 lo I learned **Dictionaries and List of Dictionaries**.

Today, I will take that concept one step further by using dictionaries to perform **real-world data processing and business analysis**.

My examples continue with **Pet Shop / Life Care Pet Zone** data.

---

# 🎯 Day 13 Learning Goals

Today I will practice:

- Working with a list of dictionaries
- Accessing dictionary values
- Using `for` loops with dictionaries
- Applying conditions to dictionary data
- Calculating revenue
- Calculating total revenue
- Finding total stock
- Finding low-stock products
- Finding expensive products
- Counting products based on conditions
- Finding highest values
- Finding lowest values
- Combining dictionaries + functions + loops + conditions

---

# 🧠 1. Review — List of Dictionaries

A single product can be represented using a dictionary:

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}
```

Multiple products can be stored inside a list:

```python
products = [
    {
        "name": "Dog Food",
        "price": 1200,
        "quantity": 2
    },
    {
        "name": "Cat Food",
        "price": 900,
        "quantity": 3
    },
    {
        "name": "Treats",
        "price": 300,
        "quantity": 5
    }
]
```

This structure is called:

**List of Dictionaries**

---

# 🔄 2. Loop Through Products

To process every product:

```python
for product in products:
    print(product)
```

Each loop lo `product` variable contains one dictionary.

Flow:

```text
products
   ↓
Product 1
   ↓
Product 2
   ↓
Product 3
```

---

# 🔍 3. Access Dictionary Values

We can access individual values using keys.

```python
for product in products:

    print(product["name"])
    print(product["price"])
    print(product["quantity"])
```

### Output

```text
Dog Food
1200
2

Cat Food
900
3

Treats
300
5
```

---

# 💰 4. Calculate Product Revenue

Business rule:

```text
Revenue = Price × Quantity
```

Code:

```python
for product in products:

    revenue = product["price"] * product["quantity"]

    print(product["name"], "Revenue:", revenue)
```

### Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
```

---

# 🧮 5. Calculate Total Revenue

Now let's calculate the total revenue.

```python
total_revenue = 0

for product in products:

    revenue = product["price"] * product["quantity"]

    total_revenue = total_revenue + revenue

print("Total Revenue:", total_revenue)
```

### Output

```text
Total Revenue: 6600
```

### 🧠 Important Concept

Here:

```python
total_revenue = 0
```

is the starting value.

Then:

```python
total_revenue = total_revenue + revenue
```

keeps adding each product's revenue.

This is called an **Accumulator**.

---

# 📦 6. Calculate Total Stock

We can also calculate total quantity of all products.

```python
total_stock = 0

for product in products:

    total_stock = total_stock + product["quantity"]

print("Total Stock:", total_stock)
```

### Output

```text
Total Stock: 10
```

---

# ⚠️ 7. Find Low-Stock Products

Business rule:

```text
Quantity < 5 → Low Stock
```

Code:

```python
for product in products:

    if product["quantity"] < 5:
        print(product["name"], "→ Low Stock")
```

### Output

```text
Dog Food → Low Stock
Cat Food → Low Stock
```

---

# 💎 8. Find Expensive Products

Business rule:

```text
Price >= 1000 → Expensive Product
```

Code:

```python
for product in products:

    if product["price"] >= 1000:
        print(product["name"], "→ Expensive Product")
```

### Output

```text
Dog Food → Expensive Product
```

---

# 🔢 9. Count Low-Stock Products

Instead of only displaying low-stock products, we can count them.

```python
low_stock_count = 0

for product in products:

    if product["quantity"] < 5:
        low_stock_count = low_stock_count + 1

print("Low Stock Products:", low_stock_count)
```

### Output

```text
Low Stock Products: 2
```

---

# 💰 10. Count Expensive Products

```python
expensive_count = 0

for product in products:

    if product["price"] >= 1000:
        expensive_count = expensive_count + 1

print("Expensive Products:", expensive_count)
```

### Output

```text
Expensive Products: 1
```

---

# 🏆 11. Find Highest Price

We can find the most expensive product.

```python
highest_price = products[0]["price"]

for product in products:

    if product["price"] > highest_price:
        highest_price = product["price"]

print("Highest Price:", highest_price)
```

### Output

```text
Highest Price: 1200
```

---

# 📉 12. Find Lowest Price

```python
lowest_price = products[0]["price"]

for product in products:

    if product["price"] < lowest_price:
        lowest_price = product["price"]

print("Lowest Price:", lowest_price)
```

### Output

```text
Lowest Price: 300
```

---

# 🥇 13. Find Highest-Priced Product

Instead of finding only the price, we can find the complete product.

```python
highest_product = products[0]

for product in products:

    if product["price"] > highest_product["price"]:
        highest_product = product

print("Highest Priced Product:", highest_product["name"])
print("Price:", highest_product["price"])
```

### Output

```text
Highest Priced Product: Dog Food
Price: 1200
```

---

# 📊 14. Find Product with Highest Revenue

Revenue can be different from price.

So let's calculate revenue for every product and find the highest one.

```python
highest_revenue = 0
highest_product = ""

for product in products:

    revenue = product["price"] * product["quantity"]

    if revenue > highest_revenue:
        highest_revenue = revenue
        highest_product = product["name"]

print("Highest Revenue Product:", highest_product)
print("Revenue:", highest_revenue)
```

### Output

```text
Highest Revenue Product: Cat Food
Revenue: 2700
```

---

# 🔗 15. Use a Function for Revenue

Instead of writing the same calculation repeatedly, create a function.

```python
def calculate_revenue(product):
    return product["price"] * product["quantity"]
```

Now:

```python
for product in products:

    revenue = calculate_revenue(product)

    print(product["name"], "Revenue:", revenue)
```

### Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
```

---

# 🧩 16. Function for Stock Status

```python
def check_stock(quantity):

    if quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"
```

Use:

```python
for product in products:

    status = check_stock(product["quantity"])

    print(product["name"], ":", status)
```

### Output

```text
Dog Food : Low Stock
Cat Food : Low Stock
Treats : Stock Available
```

---

# 💎 17. Function for Price Status

```python
def check_price(price):

    if price >= 1000:
        return "Expensive"
    else:
        return "Normal"
```

Use:

```python
for product in products:

    status = check_price(product["price"])

    print(product["name"], ":", status)
```

### Output

```text
Dog Food : Expensive
Cat Food : Normal
Treats : Normal
```

---

# 🔥 18. Complete Product Analysis

Now let's combine everything.

```python
products = [
    {
        "name": "Dog Food",
        "price": 1200,
        "quantity": 2
    },
    {
        "name": "Cat Food",
        "price": 900,
        "quantity": 3
    },
    {
        "name": "Treats",
        "price": 300,
        "quantity": 5
    },
    {
        "name": "Toy",
        "price": 500,
        "quantity": 4
    }
]


def calculate_revenue(product):
    return product["price"] * product["quantity"]


def check_stock(quantity):

    if quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"


def check_price(price):

    if price >= 1000:
        return "Expensive"
    else:
        return "Normal"


total_revenue = 0
total_stock = 0

for product in products:

    revenue = calculate_revenue(product)
    stock_status = check_stock(product["quantity"])
    price_status = check_price(product["price"])

    total_revenue = total_revenue + revenue
    total_stock = total_stock + product["quantity"]

    print("Product:", product["name"])
    print("Price:", product["price"])
    print("Quantity:", product["quantity"])
    print("Revenue:", revenue)
    print("Stock:", stock_status)
    print("Price Status:", price_status)
    print("--------------------")


print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)
```

---

# 🧠 19. Program Flow

The complete program works like this:

```text
List of Dictionaries
        ↓
      for loop
        ↓
   Get one product
        ↓
Calculate Revenue
        ↓
 Check Stock
        ↓
 Check Price
        ↓
 Update Total Revenue
        ↓
 Update Total Stock
        ↓
 Display Result
```

This is becoming closer to real-world data processing.

---

# 🏪 20. Life Care Pet Zone Business Logic

For my practice project, I use these business rules:

```text
Revenue = Price × Quantity

Low Stock = Quantity < 5

Expensive Product = Price >= 1000

Total Revenue = Sum of all revenues

Total Stock = Sum of all quantities
```

These rules can be implemented using reusable functions.

---

# 🧪 21. Practice Task 1

Create the following products:

```python
products = [
    {
        "name": "Dog Food",
        "price": 1500,
        "quantity": 3
    },
    {
        "name": "Cat Food",
        "price": 800,
        "quantity": 6
    },
    {
        "name": "Toy",
        "price": 400,
        "quantity": 8
    }
]
```

Calculate:

```text
Product Revenue
Total Revenue
Total Stock
```

---

# 🧪 22. Practice Task 2

Using the same data, find:

```text
Low Stock Products
```

Rule:

```text
Quantity < 5
```

---

# 🧪 23. Practice Task 3

Find:

```text
Expensive Products
```

Rule:

```text
Price >= 1000
```

---

# 🧪 24. Practice Task 4

Create a function:

```python
def calculate_revenue(product):
    return product["price"] * product["quantity"]
```

Use it with a list of dictionaries.

---

# 🏆 25. Day 13 Challenge

Create a **Life Care Pet Zone Product Analysis Program**.

Use at least 5 products.

Each dictionary should contain:

```text
name
price
quantity
```

Create these functions:

```python
calculate_revenue()
check_stock()
check_price()
```

Your program should display:

```text
Product Name
Price
Quantity
Revenue
Stock Status
Price Status
```

At the end calculate:

```text
Total Revenue
Total Stock
Low Stock Count
Expensive Product Count
Highest Revenue Product
Highest Revenue
```

---

# ⚠️ 26. Common Mistakes

### Mistake 1 — Wrong Dictionary Key

Incorrect:

```python
print(product["Product"])
```

If the actual key is:

```python
"name"
```

Correct:

```python
print(product["name"])
```

---

### Mistake 2 — Confusing List and Dictionary

List:

```python
products[0]
```

Dictionary:

```python
product["name"]
```

List uses **index**.

Dictionary uses **key**.

---

### Mistake 3 — Wrong Accumulator

Incorrect:

```python
total_revenue = revenue
```

This replaces the previous value.

Correct:

```python
total_revenue = total_revenue + revenue
```

---

### Mistake 4 — Forgetting Dictionary Access

Incorrect:

```python
revenue = product * quantity
```

Correct:

```python
revenue = product["price"] * product["quantity"]
```

---

# 🧠 27. Key Learning

Today I learned that dictionaries make structured data easier to manage.

Instead of:

```text
products[]
prices[]
quantities[]
```

I can keep one product's related information together:

```python
{
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}
```

Then multiple records can be stored as:

```python
[
    {...},
    {...},
    {...}
]
```

This is a powerful data-handling pattern.

---

# 📊 28. Data Engineering Connection

This concept is important for my future **Data Engineering** journey.

Real-world data can come from:

```text
APIs
 ↓
JSON
 ↓
Python
 ↓
Data Processing
 ↓
CSV
 ↓
SQL
 ↓
Pandas
 ↓
ETL Pipeline
```

A JSON object often looks similar to a Python dictionary.

So learning dictionaries helps me understand how structured data is represented and processed.

---

# 📝 29. Day 13 Summary

Today I practiced:

- List of dictionaries
- Dictionary value access
- Dictionary + loops
- Dictionary + conditions
- Dictionary + functions
- Revenue calculation
- Total revenue
- Total stock
- Low-stock detection
- Expensive-product detection
- Product counting
- Highest price
- Lowest price
- Highest revenue
- Business data processing

The important pattern I practiced today is:

```text
Data
 ↓
Loop
 ↓
Function
 ↓
Condition
 ↓
Calculation
 ↓
Result
```

---

# 📈 My Python Learning Progress

```text
Day 01  → Python Basics                    ✅
Day 02  → Variables & Data Types           ✅
Day 03  → Input & Type Conversion          ✅
Day 04  → Operators & Calculations         ✅
Day 05  → Conditional Statements           ✅
Day 06  → For Loops & Iteration            ✅
Day 07  → Lists                            ✅
Day 08  → Multiple Lists & Data Handling   ✅
Day 09  → Sales & Inventory Analysis       ✅
Day 10  → Functions                        ✅
Day 11  → Functions + Business Logic       ✅
Day 12  → Dictionaries & List of Dictionaries ✅
Day 13  → Dictionary Data Processing       ✅
```

---

# 🚀 Next Step — Day 14

My next goal is to continue improving Python data-handling and problem-solving skills.

Learning path:

```text
Python Basics
      ↓
Data Types
      ↓
Conditions
      ↓
Loops
      ↓
Lists
      ↓
Dictionaries
      ↓
Functions
      ↓
Data Processing
      ↓
File Handling
      ↓
CSV / JSON
      ↓
SQL
      ↓
Pandas
      ↓
ETL
      ↓
Data Engineering
```

---

# 🏆 Learning Philosophy

> **Learn → Practice → Make Mistakes → Understand → Improve.** 🐍🚀

Every day I am building my Python skills step by step toward my Data Engineering goal.

---

# 👨‍💻 Developed By

**Durga Vamsi**

📌 **Project:** Python Learning Journey  
📅 **Progress:** Day 01 → Day 13  
🎯 **Goal:** Python → Data Engineering

---

⭐ **Thanks for visiting my Python Learning Journey!**