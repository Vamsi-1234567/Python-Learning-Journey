# 🐍 Python Learning Journey — Day 14

# 📅 Day 14 — Dictionary Data Processing & Advanced Business Analysis

Welcome to **Day 14** of my Python Learning Journey! 🚀

Day 13 lo I practiced **Dictionary Data Processing & Business Analysis**.

Today I will go one step further by processing a list of product dictionaries and performing more detailed business calculations.

My examples continue with **Pet Shop / Life Care Pet Zone** business data.

---

# 🎯 Day 14 Learning Goals

Today I will practice:

- Working with list of dictionaries
- Accessing dictionary values
- Using `for` loops
- Using `if` conditions
- Creating reusable functions
- Calculating product revenue
- Calculating total revenue
- Finding highest and lowest values
- Counting products based on conditions
- Calculating total stock
- Finding low-stock products
- Finding expensive products
- Building a complete business analysis program

---

# 🧠 1. Product Data

Let's start with a list of dictionaries.

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]
```

Each dictionary represents one product.

For example:

```python
{"Name": "Dog Food", "Price": 1200, "Quantity": 2}
```

contains:

```text
Name     → Dog Food
Price    → 1200
Quantity → 2
```

---

# 🔄 2. Loop Through Products

```python
for product in products:
    print(product)
```

### Output

```text
{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
{'Name': 'Cat Food', 'Price': 900, 'Quantity': 3}
{'Name': 'Treats', 'Price': 300, 'Quantity': 5}
{'Name': 'Bones', 'Price': 500, 'Quantity': 4}
```

---

# 🔍 3. Access Product Values

```python
for product in products:

    print("Product:", product["Name"])
    print("Price:", product["Price"])
    print("Quantity:", product["Quantity"])
```

### Output

```text
Product: Dog Food
Price: 1200
Quantity: 2

Product: Cat Food
Price: 900
Quantity: 3

Product: Treats
Price: 300
Quantity: 5

Product: Bones
Price: 500
Quantity: 4
```

---

# 💰 4. Calculate Product Revenue

Business rule:

```text
Revenue = Price × Quantity
```

Example:

```python
for product in products:

    revenue = product["Price"] * product["Quantity"]

    print(product["Name"], "Revenue:", revenue)
```

### Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
Bones Revenue: 2000
```

---

# 🧩 5. Revenue Function

Instead of writing the same calculation repeatedly, create a function.

```python
def calculate_revenue(product):
    return product["Price"] * product["Quantity"]
```

Use the function:

```python
for product in products:

    revenue = calculate_revenue(product)

    print(product["Name"], "Revenue:", revenue)
```

### Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
Bones Revenue: 2000
```

---

# 🧮 6. Total Revenue

Now calculate the total revenue of all products.

```python
total_revenue = 0

for product in products:

    revenue = calculate_revenue(product)

    total_revenue = total_revenue + revenue

print("Total Revenue:", total_revenue)
```

### Output

```text
Total Revenue: 8600
```

### 🧠 Important Concept

```python
total_revenue = 0
```

is the starting value.

Then every product revenue is added:

```python
total_revenue = total_revenue + revenue
```

This is called an **Accumulator**.

---

# 📦 7. Total Stock

Now calculate total quantity available.

```python
total_stock = 0

for product in products:

    total_stock = total_stock + product["Quantity"]

print("Total Stock:", total_stock)
```

### Output

```text
Total Stock: 14
```

---

# ⚠️ 8. Low Stock Products

Business rule:

```text
Quantity < 5 → Low Stock
```

```python
for product in products:

    if product["Quantity"] < 5:
        print(product["Name"], "→ Low Stock")
```

### Output

```text
Dog Food → Low Stock
Cat Food → Low Stock
Bones → Low Stock
```

---

# 🔢 9. Low Stock Count

Instead of only displaying the products, we can count them.

```python
low_stock_count = 0

for product in products:

    if product["Quantity"] < 5:
        low_stock_count = low_stock_count + 1

print("Low Stock Products:", low_stock_count)
```

### Output

```text
Low Stock Products: 3
```

---

# 💎 10. Expensive Products

Business rule:

```text
Price >= 1000 → Expensive Product
```

```python
for product in products:

    if product["Price"] >= 1000:
        print(product["Name"], "→ Expensive Product")
```

### Output

```text
Dog Food → Expensive Product
```

---

# 🔢 11. Expensive Product Count

```python
expensive_count = 0

for product in products:

    if product["Price"] >= 1000:
        expensive_count = expensive_count + 1

print("Expensive Products:", expensive_count)
```

### Output

```text
Expensive Products: 1
```

---

# 🏆 12. Highest Price

Let's find the highest product price.

```python
highest_price = products[0]["Price"]

for product in products:

    if product["Price"] > highest_price:
        highest_price = product["Price"]

print("Highest Price:", highest_price)
```

### Output

```text
Highest Price: 1200
```

---

# 📉 13. Lowest Price

```python
lowest_price = products[0]["Price"]

for product in products:

    if product["Price"] < lowest_price:
        lowest_price = product["Price"]

print("Lowest Price:", lowest_price)
```

### Output

```text
Lowest Price: 300
```

---

# 🥇 14. Highest Price Product

Now let's find the product name also.

```python
highest_product = products[0]

for product in products:

    if product["Price"] > highest_product["Price"]:
        highest_product = product

print("Highest Price Product:", highest_product["Name"])
print("Price:", highest_product["Price"])
```

### Output

```text
Highest Price Product: Dog Food
Price: 1200
```

---

# 📉 15. Lowest Price Product

```python
lowest_product = products[0]

for product in products:

    if product["Price"] < lowest_product["Price"]:
        lowest_product = product

print("Lowest Price Product:", lowest_product["Name"])
print("Price:", lowest_product["Price"])
```

### Output

```text
Lowest Price Product: Treats
Price: 300
```

---

# 🏆 16. Highest Revenue Product

Price highest undadam and revenue highest undadam same kaadu.

So revenue calculate chesi highest revenue product find cheddam.

```python
highest_revenue = 0
highest_revenue_product = ""

for product in products:

    revenue = calculate_revenue(product)

    if revenue > highest_revenue:
        highest_revenue = revenue
        highest_revenue_product = product["Name"]

print("Highest Revenue Product:", highest_revenue_product)
print("Revenue:", highest_revenue)
```

### Output

```text
Highest Revenue Product: Cat Food
Revenue: 2700
```

---

# 📊 17. Revenue Comparison

Our products:

```text
Dog Food  → 1200 × 2 = 2400
Cat Food  → 900 × 3  = 2700
Treats    → 300 × 5  = 1500
Bones     → 500 × 4  = 2000
```

Therefore:

```text
Highest Revenue → Cat Food
Revenue → 2700
```

This type of calculation is useful for understanding which products generate more sales value.

---

# 🔗 18. Stock Status Function

Let's create a reusable function.

```python
def check_stock(quantity):

    if quantity < 5:
        return "Low Stock"
    else:
        return "Normal Stock"
```

Use it:

```python
for product in products:

    status = check_stock(product["Quantity"])

    print(product["Name"], ":", status)
```

### Output

```text
Dog Food : Low Stock
Cat Food : Low Stock
Treats : Normal Stock
Bones : Low Stock
```

---

# 💎 19. Price Status Function

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

    status = check_price(product["Price"])

    print(product["Name"], ":", status)
```

### Output

```text
Dog Food : Expensive
Cat Food : Normal
Treats : Normal
Bones : Normal
```

---

# 🔥 20. Complete Business Analysis

Now combine all the concepts.

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]


def calculate_revenue(product):
    return product["Price"] * product["Quantity"]


def check_stock(quantity):

    if quantity < 5:
        return "Low Stock"
    else:
        return "Normal Stock"


def check_price(price):

    if price >= 1000:
        return "Expensive"
    else:
        return "Normal"


total_revenue = 0
total_stock = 0
low_stock_count = 0
expensive_count = 0


for product in products:

    revenue = calculate_revenue(product)

    stock_status = check_stock(product["Quantity"])

    price_status = check_price(product["Price"])

    total_revenue = total_revenue + revenue

    total_stock = total_stock + product["Quantity"]

    if product["Quantity"] < 5:
        low_stock_count = low_stock_count + 1

    if product["Price"] >= 1000:
        expensive_count = expensive_count + 1

    print("Product:", product["Name"])
    print("Price:", product["Price"])
    print("Quantity:", product["Quantity"])
    print("Revenue:", revenue)
    print("Stock Status:", stock_status)
    print("Price Status:", price_status)
    print("--------------------")


print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)
print("Low Stock Count:", low_stock_count)
print("Expensive Product Count:", expensive_count)
```

---

# 🧠 21. What Happened Inside the Program?

The program follows this flow:

```text
Product List
     ↓
For Loop
     ↓
One Dictionary
     ↓
Access Name / Price / Quantity
     ↓
Calculate Revenue
     ↓
Check Stock
     ↓
Check Price
     ↓
Update Counters
     ↓
Calculate Totals
     ↓
Display Analysis
```

This is a basic example of **data processing**.

---

# 🧪 22. Practice Task 1 — Total Products

Using the same `products` list, find:

```text
Total Products
```

Hint:

```python
len(products)
```

---

# 🧪 23. Practice Task 2 — Total Revenue

Find:

```text
Total Revenue
```

Use:

```text
Function
+
For Loop
+
Accumulator
```

---

# 🧪 24. Practice Task 3 — Expensive Products Count

Rule:

```text
Price >= 1000
```

Find:

```text
Expensive Products Count
```

---

# 🧪 25. Practice Task 4 — Normal Products Count

Rule:

```text
Price < 1000
```

Find:

```text
Normal Products Count
```

---

# 🧪 26. Practice Task 5 — Highest Price Product

Find:

```text
Highest Price Product
Highest Price
```

---

# 🧪 27. Practice Task 6 — Lowest Price Product

Find:

```text
Lowest Price Product
Lowest Price
```

---

# 🧪 28. Practice Task 7 — Low Stock Products

Rule:

```text
Quantity < 3
```

Find all products that have low stock.

---

# 🏆 29. Day 14 Mini Project — Product Report

Use the same products list.

Create a complete report containing:

```text
Total Products
Total Revenue
Expensive Products Count
Normal Products Count
Highest Price Product
Highest Price
Lowest Price Product
Lowest Price
Low Stock Products
Total Stock
Highest Revenue Product
Highest Revenue
```

This mini project combines almost everything I have learned so far.

---

# 🧠 30. Important Business Rules

```text
Revenue = Price × Quantity

Total Revenue = Sum of all product revenues

Low Stock = Quantity < 5

Expensive Product = Price >= 1000

Normal Product = Price < 1000

Total Stock = Sum of all quantities
```

---

# 📊 31. Skills Used Today

Today I combined:

```text
Dictionary
     +
List
     +
For Loop
     +
If Condition
     +
Function
     +
Accumulator
     +
Counter
     +
Business Logic
```

This is an important step in my Python data-processing journey.

---

# 🏢 32. Data Engineering Connection

Data Engineering lo raw data ni process chesi useful information ga transform cheyyali.

Today I practiced a simple version of that process:

```text
Raw Product Data
       ↓
Read Dictionary
       ↓
Process Records
       ↓
Apply Business Rules
       ↓
Calculate Metrics
       ↓
Generate Report
```

Later, similar logic can be applied to data coming from:

```text
CSV Files
JSON Files
APIs
Databases
SQL
DataFrames
ETL Pipelines
```

---

# ⚠️ 33. Common Mistakes

### Mistake 1 — Wrong Key

Incorrect:

```python
product["product_name"]
```

If the actual key is:

```python
"Name"
```

Correct:

```python
product["Name"]
```

---

### Mistake 2 — Forgetting the Loop

Incorrect:

```python
print(products["Name"])
```

`products` is a list.

Correct:

```python
for product in products:
    print(product["Name"])
```

---

### Mistake 3 — Resetting the Total Inside the Loop

Incorrect:

```python
for product in products:

    total = 0
    total = total + product["Price"]
```

Correct:

```python
total = 0

for product in products:

    total = total + product["Price"]
```

The accumulator should normally be initialized **before** the loop.

---

### Mistake 4 — Confusing Count and Total

Count means:

```text
How many products?
```

Total means:

```text
How much value?
```

Example:

```python
count = count + 1
```

counts products.

```python
total = total + revenue
```

adds money values.

---

# 📝 34. Day 14 Summary

Today I improved my ability to process structured product data.

I practiced:

- List of dictionaries
- Dictionary access
- Loops
- Conditions
- Functions
- Revenue calculation
- Total revenue
- Total stock
- Product counting
- Expensive products
- Normal products
- Low-stock products
- Highest price
- Lowest price
- Highest revenue
- Business analysis
- Mini reporting

The main pattern I learned is:

```text
Data
 ↓
Process
 ↓
Apply Rules
 ↓
Calculate
 ↓
Analyze
 ↓
Report
```

---

# 📈 My Python Learning Progress

```text
Day 01  → Python Basics                         ✅
Day 02  → Variables & Data Types                ✅
Day 03  → Input & Type Conversion               ✅
Day 04  → Operators & Calculations              ✅
Day 05  → Conditional Statements                ✅
Day 06  → For Loops & Iteration                 ✅
Day 07  → Lists                                 ✅
Day 08  → Multiple Lists & Data Handling        ✅
Day 09  → Sales & Inventory Analysis            ✅
Day 10  → Functions                             ✅
Day 11  → Functions + Business Logic            ✅
Day 12  → Dictionaries & List of Dictionaries   ✅
Day 13  → Dictionary Data Processing            ✅
Day 14  → Dictionary Business Analysis          ✅
```

---

# 🚀 Next Step — Day 15

My next goal is to continue improving Python data processing and move toward more practical data-handling concepts.

Learning path:

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

Every day I am improving my Python programming and problem-solving skills step by step toward my **Data Engineering** goal.

---

# 👨‍💻 Developed By

**Durga Vamsi**

📌 **Project:** Python Learning Journey  
📅 **Progress:** Day 01 → Day 14  
🎯 **Goal:** Python → Data Engineering

---

⭐ **Thanks for visiting my Python Learning Journey!**