# 🐍 DAY 24 — Python Mini Project: Pet Shop Data Management System

## 📚 Python Learning Journey

**Goal:** Python → Data Engineering

Day 24 is an important milestone in my Python learning journey.

Ippativaraku manam individual Python concepts nerchukunnam. Ippudu aa concepts anni **one practical project** lo combine chestam.

Today we will build a:

> 🐾 **Life Care Pet Zone — Pet Shop Data Management System**

Ee project lo real-world business data ni Python tho process chestam.

---

# 🎯 Day 24 Learning Objectives

Day 24 complete ayyaka nenu:

- Lists use cheyyadam
- Dictionaries use cheyyadam
- Functions create cheyyadam
- Loops use cheyyadam
- Conditions use cheyyadam
- Exception handling use cheyyadam
- CSV data process cheyyadam
- JSON data process cheyyadam
- Modules use cheyyadam
- OOP use cheyyadam
- Data filtering
- Data sorting
- Revenue calculation
- Inventory analysis
- Business reports

anni oka project lo combine cheyyagalanu.

---

# 🏪 Project Overview

## Life Care Pet Zone

Mana pet shop lo products unnayi.

Example:

```text
Dog Food
Cat Food
Treats
Bones
Shampoo
```

Prathi product ki:

```text
Name
Price
Quantity
Category
```

untayi.

Mana program calculate cheyyali:

```text
1. Product Details
2. Total Revenue
3. Total Stock
4. Low Stock Products
5. Expensive Products
6. Highest Price Product
7. Lowest Price Product
8. Highest Revenue Product
9. Product Search
10. Sorted Products
```

---

# 🧠 Concepts Used

Day 24 project lo previous days concepts ni combine chestam.

```text
Variables
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
Exception Handling
    ↓
File Handling
    ↓
CSV
    ↓
JSON
    ↓
Modules
    ↓
OOP
    ↓
Data Processing
```

---

# 1️⃣ Project Data

First product data create cheddam.

```python
products = [
    {
        "name": "Dog Food",
        "price": 1200,
        "quantity": 2,
        "category": "Food"
    },
    {
        "name": "Cat Food",
        "price": 900,
        "quantity": 3,
        "category": "Food"
    },
    {
        "name": "Treats",
        "price": 300,
        "quantity": 5,
        "category": "Treats"
    },
    {
        "name": "Bones",
        "price": 500,
        "quantity": 4,
        "category": "Treats"
    },
    {
        "name": "Pet Shampoo",
        "price": 1100,
        "quantity": 6,
        "category": "Grooming"
    }
]
```

---

# 2️⃣ Business Rules

Mana project lo business rules:

### Revenue

```text
Revenue = Price × Quantity
```

### Low Stock

```text
Quantity < 5
```

### Expensive Product

```text
Price >= 1000
```

---

# 3️⃣ Display Products

First products ni display cheddam.

```python
for product in products:

    print("Product:", product["name"])
    print("Price:", product["price"])
    print("Quantity:", product["quantity"])
    print("Category:", product["category"])
    print()
```

---

# 4️⃣ Calculate Product Revenue

Function create cheddam.

```python
def calculate_revenue(product):

    return product["price"] * product["quantity"]
```

Use:

```python
for product in products:

    revenue = calculate_revenue(product)

    print(product["name"], revenue)
```

### Output

```text
Dog Food 2400
Cat Food 2700
Treats 1500
Bones 2000
Pet Shampoo 6600
```

---

# 5️⃣ Calculate Total Revenue

```python
def calculate_total_revenue(products):

    total = 0

    for product in products:

        total += calculate_revenue(product)

    return total
```

Call:

```python
total_revenue = calculate_total_revenue(products)

print("Total Revenue:", total_revenue)
```

### Output

```text
Total Revenue: 15200
```

---

# 6️⃣ Calculate Total Stock

```python
def calculate_total_stock(products):

    total_stock = 0

    for product in products:

        total_stock += product["quantity"]

    return total_stock
```

Use:

```python
total_stock = calculate_total_stock(products)

print("Total Stock:", total_stock)
```

### Output

```text
Total Stock: 20
```

Calculation:

```text
2 + 3 + 5 + 4 + 6 = 20
```

---

# 7️⃣ Find Low Stock Products

Business rule:

```text
Quantity < 5
```

Function:

```python
def get_low_stock_products(products):

    low_stock = []

    for product in products:

        if product["quantity"] < 5:
            low_stock.append(product)

    return low_stock
```

Use:

```python
low_stock_products = get_low_stock_products(products)

for product in low_stock_products:

    print(product["name"])
```

### Output

```text
Dog Food
Cat Food
Bones
```

---

# 8️⃣ Find Expensive Products

Business rule:

```text
Price >= 1000
```

Function:

```python
def get_expensive_products(products):

    expensive = []

    for product in products:

        if product["price"] >= 1000:
            expensive.append(product)

    return expensive
```

Use:

```python
expensive_products = get_expensive_products(products)

for product in expensive_products:

    print(product["name"])
```

### Output

```text
Dog Food
Pet Shampoo
```

---

# 9️⃣ Find Highest Price Product

```python
def get_highest_price_product(products):

    return max(
        products,
        key=lambda product: product["price"]
    )
```

Use:

```python
highest = get_highest_price_product(products)

print("Product:", highest["name"])
print("Price:", highest["price"])
```

### Output

```text
Product: Dog Food
Price: 1200
```

---

# 🔟 Find Lowest Price Product

```python
def get_lowest_price_product(products):

    return min(
        products,
        key=lambda product: product["price"]
    )
```

Use:

```python
lowest = get_lowest_price_product(products)

print("Product:", lowest["name"])
print("Price:", lowest["price"])
```

### Output

```text
Product: Treats
Price: 300
```

---

# 1️⃣1️⃣ Find Highest Revenue Product

```python
def get_highest_revenue_product(products):

    return max(
        products,
        key=lambda product: calculate_revenue(product)
    )
```

Use:

```python
highest_revenue = get_highest_revenue_product(products)

print("Product:", highest_revenue["name"])
print("Revenue:", calculate_revenue(highest_revenue))
```

### Output

```text
Product: Pet Shampoo
Revenue: 6600
```

---

# 1️⃣2️⃣ Search Product

Real applications lo product search important.

Function:

```python
def search_product(products, name):

    for product in products:

        if product["name"].lower() == name.lower():
            return product

    return None
```

Use:

```python
result = search_product(products, "Dog Food")

if result:
    print("Product Found:", result)
else:
    print("Product Not Found")
```

### Output

```text
Product Found: {'name': 'Dog Food', 'price': 1200, 'quantity': 2, 'category': 'Food'}
```

---

# 1️⃣3️⃣ Category Filtering

Food products only kavali ante:

```python
def get_products_by_category(products, category):

    result = []

    for product in products:

        if product["category"].lower() == category.lower():
            result.append(product)

    return result
```

Use:

```python
food_products = get_products_by_category(
    products,
    "Food"
)

for product in food_products:

    print(product["name"])
```

### Output

```text
Dog Food
Cat Food
```

---

# 1️⃣4️⃣ Sort Products by Price

```python
def sort_by_price(products):

    return sorted(
        products,
        key=lambda product: product["price"]
    )
```

Use:

```python
sorted_products = sort_by_price(products)

for product in sorted_products:

    print(product["name"], product["price"])
```

### Output

```text
Treats 300
Bones 500
Cat Food 900
Dog Food 1200
Pet Shampoo 1100
```

---

# 1️⃣5️⃣ Sort by Revenue

```python
def sort_by_revenue(products):

    return sorted(
        products,
        key=lambda product: calculate_revenue(product),
        reverse=True
    )
```

Use:

```python
sorted_products = sort_by_revenue(products)

for product in sorted_products:

    print(
        product["name"],
        calculate_revenue(product)
    )
```

### Output

```text
Pet Shampoo 6600
Cat Food 2700
Dog Food 2400
Bones 2000
Treats 1500
```

---

# 1️⃣6️⃣ Exception Handling

User wrong input enter chesthe program crash avvakudadhu.

Example:

```python
try:

    price = float(input("Enter product price: "))

    print("Price:", price)

except ValueError:

    print("Invalid price. Please enter a number.")
```

If user enters:

```text
abc
```

Output:

```text
Invalid price. Please enter a number.
```

---

# 1️⃣7️⃣ Validate Product Price

```python
def validate_price(price):

    if price <= 0:
        raise ValueError("Price must be greater than zero.")

    return True
```

Use:

```python
try:

    price = 1200

    validate_price(price)

    print("Valid Price")

except ValueError as error:

    print("Error:", error)
```

---

# 1️⃣8️⃣ JSON Export

Mana processed product data ni JSON file lo save cheyyachu.

```python
import json
```

Save:

```python
with open("products.json", "w") as file:

    json.dump(products, file, indent=4)
```

Ippudu:

```text
products.json
```

create avutundi.

---

# 1️⃣9️⃣ JSON Read

```python
import json

with open("products.json", "r") as file:

    products = json.load(file)

print(products)
```

This is useful because real-world applications often exchange/store structured data as JSON.

---

# 2️⃣0️⃣ CSV Export

CSV file kuda create cheyyachu.

```python
import csv
```

Example:

```python
with open("products.csv", "w", newline="") as file:

    fieldnames = [
        "name",
        "price",
        "quantity",
        "category"
    ]

    writer = csv.DictWriter(
        file,
        fieldnames=fieldnames
    )

    writer.writeheader()
    writer.writerows(products)
```

Now:

```text
products.csv
```

create avutundi.

---

# 2️⃣1️⃣ OOP Version

Ippudu same project ni OOP tho represent cheddam.

```python
class Product:

    def __init__(
        self,
        name,
        price,
        quantity,
        category
    ):
        self.name = name
        self.price = price
        self.quantity = quantity
        self.category = category

    def calculate_revenue(self):

        return self.price * self.quantity

    def check_stock(self):

        if self.quantity < 5:
            return "Low Stock"

        return "Stock Available"

    def check_price(self):

        if self.price >= 1000:
            return "Expensive"

        return "Affordable"
```

---

# 2️⃣2️⃣ Create Product Objects

```python
products = [

    Product(
        "Dog Food",
        1200,
        2,
        "Food"
    ),

    Product(
        "Cat Food",
        900,
        3,
        "Food"
    ),

    Product(
        "Treats",
        300,
        5,
        "Treats"
    ),

    Product(
        "Bones",
        500,
        4,
        "Treats"
    ),

    Product(
        "Pet Shampoo",
        1100,
        6,
        "Grooming"
    )
]
```

---

# 2️⃣3️⃣ Process OOP Objects

```python
for product in products:

    print("Product:", product.name)
    print("Price:", product.price)
    print("Quantity:", product.quantity)
    print("Category:", product.category)
    print("Revenue:", product.calculate_revenue())
    print("Stock:", product.check_stock())
    print("Price Status:", product.check_price())

    print()
```

---

# 2️⃣4️⃣ Complete OOP Analysis

```python
total_revenue = 0
total_stock = 0

for product in products:

    total_revenue += product.calculate_revenue()

    total_stock += product.quantity

print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)
```

### Output

```text
Total Revenue: 15200
Total Stock: 20
```

---

# 2️⃣5️⃣ Project Report

Create a simple report:

```python
print("=" * 40)
print(" LIFE CARE PET ZONE")
print(" PET SHOP BUSINESS REPORT")
print("=" * 40)

print("Total Products:", len(products))
print("Total Stock:", total_stock)
print("Total Revenue:", total_revenue)

print("=" * 40)
```

### Output

```text
========================================
 LIFE CARE PET ZONE
 PET SHOP BUSINESS REPORT
========================================
Total Products: 5
Total Stock: 20
Total Revenue: 15200
========================================
```

---

# 2️⃣6️⃣ Low Stock Report

```python
print("LOW STOCK PRODUCTS")

for product in products:

    if product.quantity < 5:

        print(
            product.name,
            "- Quantity:",
            product.quantity
        )
```

### Output

```text
LOW STOCK PRODUCTS

Dog Food - Quantity: 2
Cat Food - Quantity: 3
Bones - Quantity: 4
```

---

# 2️⃣7️⃣ Expensive Product Report

```python
print("EXPENSIVE PRODUCTS")

for product in products:

    if product.price >= 1000:

        print(
            product.name,
            "- Price:",
            product.price
        )
```

### Output

```text
EXPENSIVE PRODUCTS

Dog Food - Price: 1200
Pet Shampoo - Price: 1100
```

---

# 2️⃣8️⃣ Final Business Analysis

Our project gives:

```text
Total Products = 5

Total Stock = 20

Total Revenue = ₹15,200
```

Low Stock:

```text
Dog Food
Cat Food
Bones
```

Expensive Products:

```text
Dog Food
Pet Shampoo
```

Highest Revenue:

```text
Pet Shampoo
₹6,600
```

Lowest Price:

```text
Treats
₹300
```

---

# 2️⃣9️⃣ Project Structure

Day 24 project ni professional ga organize cheyyachu.

```text
Day-24-Python-Mini-Project/
│
├── main.py
├── products.py
├── sales.py
├── inventory.py
├── validation.py
├── products.csv
├── products.json
└── README.md
```

---

# 3️⃣0️⃣ Module Responsibilities

### `products.py`

Product class:

```text
Product
```

### `sales.py`

Sales calculations:

```text
Revenue
Total Revenue
Highest Revenue
```

### `inventory.py`

Inventory logic:

```text
Total Stock
Low Stock
```

### `validation.py`

Validation:

```text
Price Validation
Quantity Validation
```

### `main.py`

Complete program execution.

---

# 3️⃣1️⃣ Data Flow

Our mini project data flow:

```text
Product Data
     ↓
Python Objects
     ↓
Validation
     ↓
Data Processing
     ↓
Business Rules
     ↓
Analysis
     ↓
Report
     ↓
CSV / JSON
```

This is a very useful way to think about data-processing applications.

---

# 3️⃣2️⃣ Practice Task 1

Add 5 more products.

Example:

```text
Product Name
Price
Quantity
Category
```

Then run the complete analysis.

---

# 3️⃣3️⃣ Practice Task 2

Create a function:

```python
get_total_products(products)
```

Return:

```text
Total number of products
```

---

# 3️⃣4️⃣ Practice Task 3

Create:

```python
get_category_products(products, category)
```

Test:

```text
Food
Treats
Grooming
```

---

# 3️⃣5️⃣ Practice Task 4

Create:

```python
get_low_stock_count(products)
```

Return the number of low-stock products.

Expected:

```text
3
```

---

# 3️⃣6️⃣ Practice Task 5

Create:

```python
get_total_revenue(products)
```

Return:

```text
15200
```

---

# 3️⃣7️⃣ Practice Task 6

Export the final product data to:

```text
products.json
```

Then read the JSON file again.

---

# 3️⃣8️⃣ Practice Task 7

Export the same data to:

```text
products.csv
```

Read the CSV file and print all products.

---

# 3️⃣9️⃣ Practice Task 8 — Final Challenge

Create a menu-driven program:

```text
===== LIFE CARE PET ZONE =====

1. Show Products
2. Total Revenue
3. Total Stock
4. Low Stock Products
5. Expensive Products
6. Search Product
7. Sort by Price
8. Sort by Revenue
9. Exit
```

User choice based on corresponding function execute cheyyali.

---

# 4️⃣0️⃣ Final Mini Project Challenge

Try to build the complete system without looking at the previous code.

Requirements:

```text
✓ Product class
✓ Product objects
✓ List of products
✓ Functions
✓ Loops
✓ Conditions
✓ Exception handling
✓ Search
✓ Filtering
✓ Sorting
✓ Revenue calculation
✓ Inventory analysis
✓ JSON
✓ CSV
✓ Modular structure
```

---

# 🧠 Day 24 Key Concepts

Today I combined:

```text
Lists
Dictionaries
Functions
Loops
Conditions
Exception Handling
File Handling
CSV
JSON
Modules
OOP
Filtering
Sorting
Data Processing
Business Logic
```

---

# 📝 Day 24 Practice Checklist

- [ ] Create product dataset
- [ ] Create Product class
- [ ] Create product objects
- [ ] Display products
- [ ] Calculate product revenue
- [ ] Calculate total revenue
- [ ] Calculate total stock
- [ ] Find low-stock products
- [ ] Find expensive products
- [ ] Find highest price
- [ ] Find lowest price
- [ ] Find highest revenue
- [ ] Search product
- [ ] Filter by category
- [ ] Sort by price
- [ ] Sort by revenue
- [ ] Handle invalid input
- [ ] Export JSON
- [ ] Read JSON
- [ ] Export CSV
- [ ] Read CSV
- [ ] Organize modules
- [ ] Complete menu-driven project

---

# 📌 Day 24 Summary

Today I built a practical:

## 🐾 Life Care Pet Zone — Pet Shop Data Management System

I combined the Python concepts I learned during the previous days.

The project can perform:

```text
Product Management
Sales Analysis
Inventory Analysis
Product Search
Filtering
Sorting
Revenue Calculation
CSV Processing
JSON Processing
Exception Handling
OOP
```

This project helped me understand how individual Python concepts can work together in a real-world business application.

---

# 🚀 My Python Learning Progress

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
Day 17 → Exception Handling
Day 18 → File Handling
Day 19 → CSV Data Processing
Day 20 → JSON Data Processing
Day 21 → Modules & Packages
Day 22 → OOP Basics
Day 23 → OOP + Data Processing
Day 24 → Python Mini Project
```

---

# 🎯 Next Day

## DAY 25 — NumPy Basics

Next Python → Data Engineering journey lo manam **NumPy** start chestam.

Topics:

```text
NumPy
Arrays
Array Creation
Indexing
Slicing
Array Operations
Mathematical Operations
Statistics
```

NumPy is an important foundation before moving deeper into:

```text
Pandas
Data Cleaning
Data Analysis
SQL
Data Engineering
```

---

# 👨‍💻 Developed By

## Durga Vamsi

**Python → Data Engineering Learning Journey** 🐍🚀