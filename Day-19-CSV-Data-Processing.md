# 🐍 DAY 19 — CSV Data Processing

## 📌 Day 19 Goal

Today we will learn how to work with **CSV (Comma-Separated Values) files** using Python.

CSV files are very common in real-world business and Data Engineering because they store data in a simple **rows and columns** format.

Today we will learn:

- What is CSV?
- CSV structure
- Creating CSV files
- Reading CSV files
- Python `csv` module
- `csv.reader()`
- `csv.DictReader()`
- `csv.writer()`
- `csv.DictWriter()`
- Writing rows
- Reading rows
- Converting CSV data
- Filtering CSV data
- Calculating revenue from CSV
- Exception handling with CSV
- Business analysis
- Data Engineering connection

---

# 1️⃣ What is CSV?

CSV stands for:

```text
Comma-Separated Values
```

A CSV file stores data in rows and columns.

Example:

```text
Name,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
Bones,500,4
```

Here:

```text
Name     → Column
Price    → Column
Quantity → Column
```

And:

```text
Dog Food,1200,2
```

is one row.

---

# 2️⃣ CSV Structure

A CSV file usually has a header row.

Example:

```text
Name,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
Bones,500,4
```

Structure:

```text
Header
  ↓
Name | Price | Quantity
  ↓
Data Rows
  ↓
Dog Food | 1200 | 2
Cat Food | 900 | 3
Treats   | 300  | 5
Bones    | 500  | 4
```

CSV is very useful because business data naturally fits into rows and columns.

---

# 3️⃣ Why CSV is Important for Data Engineering

Many organizations exchange data using CSV files.

Examples:

```text
Sales Data
Customer Data
Product Data
Employee Data
Inventory Data
Transaction Data
```

A simple pipeline can be:

```text
CSV File
   ↓
Python
   ↓
Read Data
   ↓
Clean Data
   ↓
Transform Data
   ↓
Business Analysis
   ↓
Database
```

---

# 4️⃣ Python CSV Module

Python provides a built-in module called:

```python
csv
```

Import it:

```python
import csv
```

We can use it to:

```text
Read CSV
Write CSV
Process CSV
```

---

# 5️⃣ Creating a CSV File

Let's create product data.

```python
import csv

products = [
    ["Dog Food", 1200, 2],
    ["Cat Food", 900, 3],
    ["Treats", 300, 5],
    ["Bones", 500, 4]
]

with open("products.csv", "w", newline="") as file:

    writer = csv.writer(file)

    writer.writerow(["Name", "Price", "Quantity"])

    writer.writerows(products)
```

This creates:

```text
products.csv
```

with:

```text
Name,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
Bones,500,4
```

---

# 6️⃣ Understanding `csv.writer()`

We use:

```python
csv.writer(file)
```

to create a CSV writer.

Example:

```python
writer = csv.writer(file)
```

Then:

```python
writer.writerow(...)
```

writes one row.

And:

```python
writer.writerows(...)
```

writes multiple rows.

---

# 7️⃣ `writerow()`

Example:

```python
import csv

with open("products.csv", "w", newline="") as file:

    writer = csv.writer(file)

    writer.writerow(["Name", "Price", "Quantity"])
    writer.writerow(["Dog Food", 1200, 2])
    writer.writerow(["Cat Food", 900, 3])
```

The CSV becomes:

```text
Name,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
```

---

# 8️⃣ `writerows()`

Instead of writing each row separately:

```python
products = [
    ["Dog Food", 1200, 2],
    ["Cat Food", 900, 3],
    ["Treats", 300, 5]
]
```

We can use:

```python
writer.writerows(products)
```

Complete example:

```python
import csv

products = [
    ["Dog Food", 1200, 2],
    ["Cat Food", 900, 3],
    ["Treats", 300, 5]
]

with open("products.csv", "w", newline="") as file:

    writer = csv.writer(file)

    writer.writerow(["Name", "Price", "Quantity"])

    writer.writerows(products)
```

---

# 9️⃣ Reading a CSV File

Use:

```python
csv.reader()
```

Example:

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.reader(file)

    for row in reader:

        print(row)
```

Output:

```text
['Name', 'Price', 'Quantity']
['Dog Food', '1200', '2']
['Cat Food', '900', '3']
['Treats', '300', '5']
['Bones', '500', '4']
```

---

# 🔟 Important — CSV Data is Read as Text

Notice:

```text
'1200'
```

and:

```text
'2'
```

are strings.

So we need type conversion.

Example:

```python
price = int(row[1])
quantity = int(row[2])
```

Then:

```text
"1200" → 1200
"2"    → 2
```

---

# 1️⃣1️⃣ Reading CSV with Indexes

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.reader(file)

    next(reader)

    for row in reader:

        name = row[0]
        price = int(row[1])
        quantity = int(row[2])

        print(name, price, quantity)
```

Output:

```text
Dog Food 1200 2
Cat Food 900 3
Treats 300 5
Bones 500 4
```

---

# 1️⃣2️⃣ What is `next()`?

Our first row is:

```text
Name,Price,Quantity
```

This is the header.

We don't want to process it as product data.

So:

```python
next(reader)
```

moves past the header.

Then the loop starts from:

```text
Dog Food
```

---

# 1️⃣3️⃣ Using `DictReader()`

A better way to work with CSV data is:

```python
csv.DictReader()
```

It converts each row into a dictionary.

Example:

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        print(row)
```

Output:

```text
{'Name': 'Dog Food', 'Price': '1200', 'Quantity': '2'}
{'Name': 'Cat Food', 'Price': '900', 'Quantity': '3'}
{'Name': 'Treats', 'Price': '300', 'Quantity': '5'}
{'Name': 'Bones', 'Price': '500', 'Quantity': '4'}
```

This is very useful because we can access values using column names.

---

# 1️⃣4️⃣ Access CSV Data Using Column Names

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        print(row["Name"])
        print(row["Price"])
        print(row["Quantity"])
```

Output:

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

Bones
500
4
```

This is easier to understand than:

```python
row[0]
row[1]
row[2]
```

---

# 1️⃣5️⃣ Convert CSV Data to Dictionaries

We can create a list of dictionaries.

```python
import csv

products = []

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        product = {
            "Name": row["Name"],
            "Price": int(row["Price"]),
            "Quantity": int(row["Quantity"])
        }

        products.append(product)

print(products)
```

Output:

```text
[
    {'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2},
    {'Name': 'Cat Food', 'Price': 900, 'Quantity': 3},
    {'Name': 'Treats', 'Price': 300, 'Quantity': 5},
    {'Name': 'Bones', 'Price': 500, 'Quantity': 4}
]
```

This connects directly to the concepts we learned earlier.

```text
CSV
 ↓
Dictionary
 ↓
List of Dictionaries
```

---

# 1️⃣6️⃣ Calculate Revenue from CSV

Business Rule:

```text
Revenue = Price × Quantity
```

Example:

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        price = int(row["Price"])
        quantity = int(row["Quantity"])

        revenue = price * quantity

        print(row["Name"], revenue)
```

Output:

```text
Dog Food 2400
Cat Food 2700
Treats 1500
Bones 2000
```

---

# 1️⃣7️⃣ Calculate Total Revenue

```python
import csv

total_revenue = 0

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        price = int(row["Price"])
        quantity = int(row["Quantity"])

        revenue = price * quantity

        total_revenue += revenue


print("Total Revenue:", total_revenue)
```

Output:

```text
Total Revenue: 8600
```

---

# 1️⃣8️⃣ Calculate Total Stock

```python
import csv

total_stock = 0

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        quantity = int(row["Quantity"])

        total_stock += quantity


print("Total Stock:", total_stock)
```

Output:

```text
Total Stock: 14
```

---

# 1️⃣9️⃣ Find Expensive Products

Business Rule:

```text
Price >= 1000
```

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        price = int(row["Price"])

        if price >= 1000:

            print(
                "Expensive:",
                row["Name"]
            )
```

Output:

```text
Expensive: Dog Food
```

---

# 2️⃣0️⃣ Find Low Stock Products

Business Rule:

```text
Quantity < 3
```

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        quantity = int(row["Quantity"])

        if quantity < 3:

            print(
                "Low Stock:",
                row["Name"]
            )
```

Output:

```text
Low Stock: Dog Food
```

---

# 2️⃣1️⃣ Find Highest Price Product

We can use `max()`.

```python
import csv

products = []

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:

        products.append({
            "Name": row["Name"],
            "Price": int(row["Price"]),
            "Quantity": int(row["Quantity"])
        })


highest_price = max(
    products,
    key=lambda product: product["Price"]
)

print(highest_price)
```

Output:

```text
{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
```

---

# 2️⃣2️⃣ Find Highest Revenue Product

```python
highest_revenue = max(
    products,
    key=lambda product: product["Price"] * product["Quantity"]
)

print(highest_revenue)
```

Output:

```text
{'Name': 'Cat Food', 'Price': 900, 'Quantity': 3}
```

Because:

```text
Dog Food = 1200 × 2 = 2400
Cat Food = 900 × 3 = 2700
Treats   = 300 × 5 = 1500
Bones    = 500 × 4 = 2000
```

So:

```text
Highest Revenue = Cat Food
Revenue = 2700
```

---

# 2️⃣3️⃣ CSV + Exception Handling

Day 17 taught us Exception Handling.

Now we combine it with CSV.

```python
import csv

try:

    with open("products.csv", "r") as file:

        reader = csv.DictReader(file)

        for row in reader:

            price = int(row["Price"])
            quantity = int(row["Quantity"])

            revenue = price * quantity

            print(
                row["Name"],
                revenue
            )

except FileNotFoundError:

    print("CSV file not found")

except ValueError:

    print("Invalid numeric data")

except KeyError:

    print("Required column is missing")
```

This creates a safer data-processing program.

---

# 2️⃣4️⃣ Writing CSV Using `DictWriter`

We can also write dictionaries directly to a CSV file.

```python
import csv

products = [
    {
        "Name": "Dog Food",
        "Price": 1200,
        "Quantity": 2
    },
    {
        "Name": "Cat Food",
        "Price": 900,
        "Quantity": 3
    },
    {
        "Name": "Treats",
        "Price": 300,
        "Quantity": 5
    }
]


with open("products.csv", "w", newline="") as file:

    fieldnames = [
        "Name",
        "Price",
        "Quantity"
    ]

    writer = csv.DictWriter(
        file,
        fieldnames=fieldnames
    )

    writer.writeheader()

    writer.writerows(products)
```

This creates:

```text
Name,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
```

---

# 2️⃣5️⃣ `DictWriter()` Methods

Important methods:

```python
writer.writeheader()
```

Writes the column names.

```python
writer.writerow(product)
```

Writes one dictionary.

```python
writer.writerows(products)
```

Writes multiple dictionaries.

---

# 2️⃣6️⃣ CSV + List Comprehension

We can combine Day 16 concepts with CSV.

Example:

```python
import csv

with open("products.csv", "r") as file:

    reader = csv.DictReader(file)

    products = [
        {
            "Name": row["Name"],
            "Price": int(row["Price"]),
            "Quantity": int(row["Quantity"])
        }
        for row in reader
    ]

print(products)
```

Now CSV data becomes a Python list of dictionaries.

---

# 2️⃣7️⃣ CSV + Filtering

Find expensive products using List Comprehension.

```python
expensive_products = [
    product
    for product in products
    if product["Price"] >= 1000
]

print(expensive_products)
```

Output:

```text
[
    {'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
]
```

---

# 2️⃣8️⃣ CSV + Sorting

Sort products by price.

```python
sorted_products = sorted(
    products,
    key=lambda product: product["Price"]
)

for product in sorted_products:

    print(
        product["Name"],
        product["Price"]
    )
```

Output:

```text
Treats 300
Bones 500
Cat Food 900
Dog Food 1200
```

This combines:

```text
Day 15 → Sorting
Day 19 → CSV
```

---

# 2️⃣9️⃣ Complete CSV Business Analysis

```python
import csv


products = []


try:

    with open("products.csv", "r") as file:

        reader = csv.DictReader(file)

        for row in reader:

            product = {
                "Name": row["Name"],
                "Price": int(row["Price"]),
                "Quantity": int(row["Quantity"])
            }

            products.append(product)


except FileNotFoundError:

    print("CSV file not found")

except ValueError:

    print("Invalid numeric data")

except KeyError:

    print("Required column is missing")


total_revenue = 0
total_stock = 0


for product in products:

    revenue = (
        product["Price"]
        * product["Quantity"]
    )

    total_revenue += revenue

    total_stock += product["Quantity"]

    print(
        product["Name"],
        "Revenue:",
        revenue
    )


expensive_products = [
    product["Name"]
    for product in products
    if product["Price"] >= 1000
]


low_stock_products = [
    product["Name"]
    for product in products
    if product["Quantity"] < 3
]


highest_price_product = max(
    products,
    key=lambda product: product["Price"]
)


highest_revenue_product = max(
    products,
    key=lambda product:
        product["Price"] * product["Quantity"]
)


print("Total Products:", len(products))
print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)
print(
    "Expensive Products:",
    expensive_products
)
print(
    "Low Stock Products:",
    low_stock_products
)
print(
    "Highest Price Product:",
    highest_price_product["Name"]
)
print(
    "Highest Revenue Product:",
    highest_revenue_product["Name"]
)
```

---

# 3️⃣0️⃣ Expected Business Report

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
Bones Revenue: 2000

Total Products: 4
Total Revenue: 8600
Total Stock: 14

Expensive Products: ['Dog Food']

Low Stock Products: ['Dog Food']

Highest Price Product: Dog Food
Highest Revenue Product: Cat Food
```

---

# 3️⃣1️⃣ Important CSV Functions

| Function / Method | Purpose |
|---|---|
| `csv.reader()` | Read CSV rows |
| `csv.DictReader()` | Read CSV as dictionaries |
| `csv.writer()` | Write CSV rows |
| `csv.DictWriter()` | Write dictionaries to CSV |
| `writerow()` | Write one row |
| `writerows()` | Write multiple rows |
| `writeheader()` | Write CSV headers |
| `next()` | Skip/read next row |

---

# 3️⃣2️⃣ CSV Data Processing Flow

Today we learned this complete flow:

```text
CSV File
   ↓
csv.DictReader()
   ↓
Dictionary
   ↓
List of Dictionaries
   ↓
Type Conversion
   ↓
Validation
   ↓
Filtering
   ↓
Sorting
   ↓
Business Calculations
   ↓
Business Report
```

This is an important foundation for Data Engineering.

---

# 3️⃣3️⃣ Common Mistakes

### ❌ Mistake 1 — Forgetting `import csv`

Wrong:

```python
reader = csv.reader(file)
```

Correct:

```python
import csv
```

---

### ❌ Mistake 2 — Treating CSV Numbers as Integers

CSV data is commonly read as text.

For example:

```python
row["Price"]
```

may be:

```text
"1200"
```

Convert it:

```python
price = int(row["Price"])
```

---

### ❌ Mistake 3 — Wrong Column Name

If CSV contains:

```text
Name,Price,Quantity
```

use:

```python
row["Price"]
```

not:

```python
row["price"]
```

Python is case-sensitive.

---

### ❌ Mistake 4 — Forgetting `newline=""`

When writing CSV, use:

```python
with open(
    "products.csv",
    "w",
    newline=""
) as file:
```

This helps avoid unwanted blank lines on some platforms.

---

### ❌ Mistake 5 — Missing File

Use:

```python
try:

    with open("products.csv", "r") as file:
        ...

except FileNotFoundError:

    print("CSV file not found")
```

---

# 3️⃣4️⃣ Day 18 vs Day 19

| Day | Main Concept |
|---|---|
| Day 18 | File Handling |
| Day 19 | CSV Data Processing |

### Day 18

We learned:

```text
Files
 ↓
Read
 ↓
Write
 ↓
Append
```

### Day 19

We move to structured data:

```text
CSV
 ↓
Rows
 ↓
Columns
 ↓
Dictionary
 ↓
Data Processing
```

So Day 19 is a natural continuation of File Handling.

---

# 3️⃣5️⃣ Data Engineering Connection 🔥

CSV is one of the easiest formats for understanding data pipelines.

For example, a company may provide:

```text
sales.csv
```

Your job as a Data Engineer may be to:

```text
Read CSV
   ↓
Validate Data
   ↓
Clean Data
   ↓
Transform Data
   ↓
Calculate Metrics
   ↓
Load Data
```

This is the foundation of an **ETL pipeline**.

```text
Extract
  ↓
Transform
  ↓
Load
```

Today's Python work is preparing you for:

```text
CSV
 ↓
Pandas
 ↓
SQL
 ↓
Databases
 ↓
ETL
 ↓
Data Pipelines
 ↓
Cloud Data Engineering 🚀
```

---

# 📌 Day 19 Summary

Today I learned:

- ✅ What is CSV
- ✅ CSV rows and columns
- ✅ Python `csv` module
- ✅ `csv.reader()`
- ✅ `csv.DictReader()`
- ✅ `csv.writer()`
- ✅ `csv.DictWriter()`
- ✅ `writerow()`
- ✅ `writerows()`
- ✅ `writeheader()`
- ✅ Reading CSV data
- ✅ Writing CSV data
- ✅ Type conversion
- ✅ CSV → Dictionary
- ✅ CSV → List of Dictionaries
- ✅ Filtering CSV data
- ✅ Sorting CSV data
- ✅ Revenue calculation
- ✅ Total revenue
- ✅ Total stock
- ✅ Exception handling
- ✅ Business analysis

---

# 📝 Day 19 Practice Tasks

## 🟢 Task 1 — Create CSV

Create:

```text
products.csv
```

with:

```text
Name,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
Bones,500,4
```

---

## 🟢 Task 2 — Read CSV

Use:

```python
csv.reader()
```

and print every row.

---

## 🟢 Task 3 — Use DictReader

Read the CSV using:

```python
csv.DictReader()
```

---

## 🟡 Task 4 — Product Names

Print only product names.

---

## 🟡 Task 5 — Total Revenue

Calculate:

```text
Price × Quantity
```

and find total revenue.

---

## 🟡 Task 6 — Total Stock

Calculate total quantity.

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

## 🟠 Task 9 — Highest Revenue

Find the product with the highest revenue.

---

## 🔴 Task 10 — CSV Mini Project

Build a complete:

# 🐾 Life Care Pet Zone CSV Analysis System

The program should:

```text
Read products.csv
      ↓
Convert CSV data
      ↓
Create dictionaries
      ↓
Validate data
      ↓
Calculate Revenue
      ↓
Calculate Total Revenue
      ↓
Calculate Total Stock
      ↓
Find Expensive Products
      ↓
Find Low Stock Products
      ↓
Find Highest Price
      ↓
Find Highest Revenue
      ↓
Display Business Report
```

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
Day 17 → Exception Handling
Day 18 → File Handling
Day 19 → CSV Data Processing
```

---

# 🚀 Next Step — Day 20

The next topic is:

## 🟨 JSON Data Processing

We will learn how Python works with **JSON**, another extremely important data format used in APIs and Data Engineering.

```text
File Handling
      ↓
CSV
      ↓
JSON
      ↓
APIs
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

---

# 👨‍💻 Developed By

## **Durga Vamsi**

🐍 Python Learning Journey  
📊 Data Engineering Goal  
🚀 Learning by Building Real-World Business Examples