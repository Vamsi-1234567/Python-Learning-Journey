# 🐍 DAY 20 — JSON Data Processing

## 📌 Day 20 Goal

Today we will learn **JSON Data Processing in Python**.

After learning:

```text
Day 18 → File Handling
Day 19 → CSV Data Processing
```

today we move to another very important data format:

```text
JSON
```

JSON is widely used for:

- APIs
- Web applications
- Data exchange
- Configuration files
- Data Engineering
- Cloud applications

Today we will learn:

- What is JSON?
- JSON structure
- JSON objects
- JSON arrays
- Python dictionary ↔ JSON
- `json` module
- `json.loads()`
- `json.dumps()`
- `json.load()`
- `json.dump()`
- Reading JSON files
- Writing JSON files
- Processing JSON data
- Filtering JSON data
- Calculating revenue
- Exception handling
- Business analysis

---

# 1️⃣ What is JSON?

JSON stands for:

```text
JavaScript Object Notation
```

JSON is a common format used to store and exchange structured data.

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

This looks very similar to a Python dictionary.

Python:

```python
product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

JSON:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

The structure is similar, but JSON is a **data format**, while a Python dictionary is a Python data structure.

---

# 2️⃣ Why JSON is Important?

JSON is extremely common when working with APIs.

For example, an API might return:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

Python can read this data and process it.

A common workflow is:

```text
API
 ↓
JSON
 ↓
Python
 ↓
Data Processing
 ↓
Database
```

This is very important for Data Engineering.

---

# 3️⃣ Basic JSON Structure

A JSON object uses:

```text
key : value
```

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

Here:

```text
Name     → Key
Dog Food → Value

Price    → Key
1200     → Value

Quantity → Key
2        → Value
```

This is similar to a Python dictionary.

---

# 4️⃣ JSON Data Types

JSON supports common data types:

```text
String
Number
Boolean
Object
Array
Null
```

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2,
    "Available": true
}
```

Here:

```text
"Dog Food" → String
1200       → Number
2          → Number
true       → Boolean
```

---

# 5️⃣ JSON Object

A JSON object uses:

```text
{ }
```

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

Python equivalent:

```python
product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

---

# 6️⃣ JSON Array

A JSON array uses:

```text
[ ]
```

Example:

```json
[
    "Dog Food",
    "Cat Food",
    "Treats",
    "Bones"
]
```

This is similar to a Python list.

Python:

```python
products = [
    "Dog Food",
    "Cat Food",
    "Treats",
    "Bones"
]
```

JSON:

```json
[
    "Dog Food",
    "Cat Food",
    "Treats",
    "Bones"
]
```

---

# 7️⃣ JSON List of Objects

This is very important for Data Engineering.

Example:

```json
[
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
    },
    {
        "Name": "Bones",
        "Price": 500,
        "Quantity": 4
    }
]
```

This is equivalent to a Python:

```text
List of Dictionaries
```

So the concepts from Day 12–16 are directly useful here.

---

# 8️⃣ Python `json` Module

Python provides a built-in module:

```python
json
```

Import it:

```python
import json
```

The module provides functions for converting between Python data and JSON.

Important functions:

```text
json.loads()
json.dumps()
json.load()
json.dump()
```

---

# 9️⃣ `json.loads()`

`loads()` means:

```text
Load String
```

It converts a JSON string into a Python object.

Example:

```python
import json

json_data = '{"Name": "Dog Food", "Price": 1200}'

product = json.loads(json_data)

print(product)
```

Output:

```text
{'Name': 'Dog Food', 'Price': 1200}
```

Now the JSON string has become a Python dictionary.

---

# 🔟 JSON String → Python Dictionary

```python
import json

json_data = '{"Name": "Dog Food", "Price": 1200, "Quantity": 2}'

product = json.loads(json_data)

print(product["Name"])
print(product["Price"])
print(product["Quantity"])
```

Output:

```text
Dog Food
1200
2
```

Flow:

```text
JSON String
     ↓
json.loads()
     ↓
Python Dictionary
```

---

# 1️⃣1️⃣ `json.dumps()`

`dumps()` converts Python data into a JSON string.

Example:

```python
import json

product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}

json_data = json.dumps(product)

print(json_data)
```

Output:

```text
{"Name": "Dog Food", "Price": 1200, "Quantity": 2}
```

Flow:

```text
Python Dictionary
       ↓
json.dumps()
       ↓
JSON String
```

---

# 1️⃣2️⃣ Pretty JSON

We can make JSON easier to read using:

```python
indent=4
```

Example:

```python
import json

product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}

json_data = json.dumps(
    product,
    indent=4
)

print(json_data)
```

Output:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

This is called **pretty printing**.

---

# 1️⃣3️⃣ `json.load()`

There is an important difference:

```text
loads() → JSON string
load()  → JSON file
```

If we have:

```text
products.json
```

we can read it using:

```python
import json

with open("products.json", "r") as file:

    products = json.load(file)

print(products)
```

---

# 1️⃣4️⃣ `json.dump()`

Similarly:

```text
dumps() → JSON string
dump()  → JSON file
```

Example:

```python
import json

product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}

with open("product.json", "w") as file:

    json.dump(
        product,
        file,
        indent=4
    )
```

This creates:

```text
product.json
```

---

# 1️⃣5️⃣ Creating a JSON File

Let's create product data.

```python
import json

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
    },
    {
        "Name": "Bones",
        "Price": 500,
        "Quantity": 4
    }
]

with open("products.json", "w") as file:

    json.dump(
        products,
        file,
        indent=4
    )
```

Now the JSON file contains:

```json
[
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
    },
    {
        "Name": "Bones",
        "Price": 500,
        "Quantity": 4
    }
]
```

---

# 1️⃣6️⃣ Reading JSON File

```python
import json

with open("products.json", "r") as file:

    products = json.load(file)

print(products)
```

Now:

```python
products
```

is a Python list containing dictionaries.

---

# 1️⃣7️⃣ Loop Through JSON Data

```python
import json

with open("products.json", "r") as file:

    products = json.load(file)


for product in products:

    print(product["Name"])
```

Output:

```text
Dog Food
Cat Food
Treats
Bones
```

---

# 1️⃣8️⃣ Access Price

```python
for product in products:

    print(
        product["Name"],
        product["Price"]
    )
```

Output:

```text
Dog Food 1200
Cat Food 900
Treats 300
Bones 500
```

---

# 1️⃣9️⃣ Calculate Revenue

Business Rule:

```text
Revenue = Price × Quantity
```

```python
for product in products:

    revenue = (
        product["Price"]
        * product["Quantity"]
    )

    print(
        product["Name"],
        revenue
    )
```

Output:

```text
Dog Food 2400
Cat Food 2700
Treats 1500
Bones 2000
```

---

# 2️⃣0️⃣ Total Revenue

```python
total_revenue = 0

for product in products:

    revenue = (
        product["Price"]
        * product["Quantity"]
    )

    total_revenue += revenue


print("Total Revenue:", total_revenue)
```

Output:

```text
Total Revenue: 8600
```

---

# 2️⃣1️⃣ Total Stock

```python
total_stock = 0

for product in products:

    total_stock += product["Quantity"]


print("Total Stock:", total_stock)
```

Output:

```text
Total Stock: 14
```

---

# 2️⃣2️⃣ Expensive Products

Business Rule:

```text
Price >= 1000
```

```python
for product in products:

    if product["Price"] >= 1000:

        print(
            "Expensive:",
            product["Name"]
        )
```

Output:

```text
Expensive: Dog Food
```

---

# 2️⃣3️⃣ Low Stock Products

Business Rule:

```text
Quantity < 3
```

```python
for product in products:

    if product["Quantity"] < 3:

        print(
            "Low Stock:",
            product["Name"]
        )
```

Output:

```text
Low Stock: Dog Food
```

---

# 2️⃣4️⃣ JSON + List Comprehension

Day 16 taught us List Comprehension.

We can combine it with JSON.

```python
product_names = [
    product["Name"]
    for product in products
]

print(product_names)
```

Output:

```text
['Dog Food', 'Cat Food', 'Treats', 'Bones']
```

---

# 2️⃣5️⃣ JSON + Filtering

Find expensive products.

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
    {
        'Name': 'Dog Food',
        'Price': 1200,
        'Quantity': 2
    }
]
```

---

# 2️⃣6️⃣ JSON + Sorting

Day 15 taught us sorting.

We can sort JSON data after loading it into Python.

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

---

# 2️⃣7️⃣ Highest Revenue Product

```python
highest_revenue_product = max(
    products,
    key=lambda product:
        product["Price"] * product["Quantity"]
)

print(highest_revenue_product)
```

Output:

```text
{'Name': 'Cat Food', 'Price': 900, 'Quantity': 3}
```

---

# 2️⃣8️⃣ JSON + Functions

We can use functions to process JSON data.

```python
def calculate_revenue(product):

    return (
        product["Price"]
        * product["Quantity"]
    )


for product in products:

    revenue = calculate_revenue(product)

    print(
        product["Name"],
        revenue
    )
```

Output:

```text
Dog Food 2400
Cat Food 2700
Treats 1500
Bones 2000
```

---

# 2️⃣9️⃣ JSON + Exception Handling

Day 17 taught us Exception Handling.

Now we can combine it with JSON.

```python
import json

try:

    with open("products.json", "r") as file:

        products = json.load(file)

        print(products)

except FileNotFoundError:

    print("JSON file not found")

except json.JSONDecodeError:

    print("Invalid JSON data")
```

This makes our JSON processing safer.

---

# 3️⃣0️⃣ What is `JSONDecodeError`?

If a JSON file contains invalid JSON:

```text
{
    "Name": "Dog Food",
    "Price": 1200,
```

the JSON structure is incomplete.

Python may raise:

```text
JSONDecodeError
```

We can handle it:

```python
try:

    with open("products.json", "r") as file:

        products = json.load(file)

except json.JSONDecodeError:

    print("Invalid JSON format")
```

---

# 3️⃣1️⃣ Complete JSON Business Analysis

```python
import json


try:

    with open("products.json", "r") as file:

        products = json.load(file)


except FileNotFoundError:

    print("JSON file not found")

    products = []


except json.JSONDecodeError:

    print("Invalid JSON data")

    products = []


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


if products:

    highest_price_product = max(
        products,
        key=lambda product:
            product["Price"]
    )

    highest_revenue_product = max(
        products,
        key=lambda product:
            product["Price"]
            * product["Quantity"]
    )

    print(
        "Highest Price Product:",
        highest_price_product["Name"]
    )

    print(
        "Highest Revenue Product:",
        highest_revenue_product["Name"]
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
```

---

# 3️⃣2️⃣ Expected Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
Bones Revenue: 2000

Highest Price Product: Dog Food
Highest Revenue Product: Cat Food

Total Products: 4
Total Revenue: 8600
Total Stock: 14

Expensive Products: ['Dog Food']

Low Stock Products: ['Dog Food']
```

---

# 3️⃣3️⃣ Python ↔ JSON Conversion

Remember these four functions carefully.

```text
Python → JSON String

json.dumps()
```

```text
JSON String → Python

json.loads()
```

```text
Python → JSON File

json.dump()
```

```text
JSON File → Python

json.load()
```

Quick memory trick:

```text
s = string
no s = file
```

So:

```text
loads  → string → Python
dumps  → Python → string

load   → file → Python
dump   → Python → file
```

---

# 3️⃣4️⃣ JSON vs CSV

| Feature | CSV | JSON |
|---|---|---|
| Structure | Rows & Columns | Objects & Arrays |
| Best for | Tabular data | Structured / nested data |
| Python module | `csv` | `json` |
| Dictionary support | `DictReader` | Native objects |
| Nested data | Limited | Supported |
| APIs | Less common | Very common |

Example CSV:

```text
Name,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
```

Example JSON:

```json
[
    {
        "Name": "Dog Food",
        "Price": 1200,
        "Quantity": 2
    },
    {
        "Name": "Cat Food",
        "Price": 900,
        "Quantity": 3
    }
]
```

---

# 3️⃣5️⃣ JSON Nested Data

JSON can contain nested objects.

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Category": {
        "Type": "Food",
        "Animal": "Dog"
    }
}
```

Python:

```python
product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Category": {
        "Type": "Food",
        "Animal": "Dog"
    }
}
```

Access nested data:

```python
print(product["Category"]["Type"])
```

Output:

```text
Food
```

This is one reason JSON is powerful for APIs and real-world data.

---

# 3️⃣6️⃣ Common Mistakes

### ❌ Mistake 1 — Confusing `load()` and `loads()`

Remember:

```text
load  → file
loads → string
```

---

### ❌ Mistake 2 — Confusing `dump()` and `dumps()`

Remember:

```text
dump  → file
dumps → string
```

---

### ❌ Mistake 3 — Forgetting `import json`

Correct:

```python
import json
```

---

### ❌ Mistake 4 — Invalid JSON

JSON uses:

```json
{
    "Name": "Dog Food"
}
```

Make sure the JSON structure is valid.

---

### ❌ Mistake 5 — Wrong Key

If JSON contains:

```json
{
    "Price": 1200
}
```

use:

```python
product["Price"]
```

not:

```python
product["price"]
```

Python dictionary keys are case-sensitive.

---

### ❌ Mistake 6 — Processing Empty Data

Before using:

```python
max(products)
```

make sure the list is not empty.

Example:

```python
if products:

    highest = max(
        products,
        key=lambda product:
            product["Price"]
    )
```

---

# 3️⃣7️⃣ Day 19 vs Day 20

| Day | Main Concept |
|---|---|
| Day 19 | CSV Data Processing |
| Day 20 | JSON Data Processing |

### Day 19

```text
CSV
 ↓
Rows
 ↓
Columns
 ↓
DictReader
 ↓
Data Processing
```

### Day 20

```text
JSON
 ↓
Objects
 ↓
Arrays
 ↓
json.load()
 ↓
Data Processing
```

Both are important data formats.

---

# 3️⃣8️⃣ Data Engineering Connection 🔥

JSON is extremely important in modern Data Engineering.

A typical API workflow may look like:

```text
API
 ↓
JSON Response
 ↓
Python
 ↓
Validate
 ↓
Transform
 ↓
Clean
 ↓
Load
 ↓
Database
```

For example:

```text
Customer API
      ↓
   JSON Data
      ↓
Python Processing
      ↓
Data Validation
      ↓
Transformation
      ↓
Database
```

You are now learning the basic skills needed to work with:

```text
CSV
JSON
APIs
Pandas
SQL
ETL
Data Pipelines
Cloud Data
```

---

# 3️⃣9️⃣ Day 20 Practice Tasks

## 🟢 Task 1 — Create JSON

Create:

```text
product.json
```

with:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

---

## 🟢 Task 2 — Read JSON

Use:

```python
json.load()
```

and print the data.

---

## 🟢 Task 3 — Access Values

Print:

```text
Name
Price
Quantity
```

---

## 🟢 Task 4 — Create Product List

Create a JSON file containing:

```text
Dog Food
Cat Food
Treats
Bones
```

with price and quantity.

---

## 🟡 Task 5 — Calculate Revenue

Calculate:

```text
Revenue = Price × Quantity
```

for every product.

---

## 🟡 Task 6 — Total Revenue

Calculate:

```text
Total Revenue
```

---

## 🟡 Task 7 — Total Stock

Calculate:

```text
Total Stock
```

---

## 🟠 Task 8 — Expensive Products

Find:

```text
Price >= 1000
```

---

## 🟠 Task 9 — Low Stock Products

Find:

```text
Quantity < 3
```

---

## 🟠 Task 10 — Highest Revenue

Find the product with the highest revenue.

---

## 🔴 Task 11 — Sort Products

Sort JSON products by:

```text
Price
```

from highest to lowest.

---

## 🔴 Task 12 — Mini Project

Build a:

# 🐾 Life Care Pet Zone JSON Analysis System

Program flow:

```text
Read products.json
      ↓
Load JSON
      ↓
Validate Data
      ↓
Convert / Process Data
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
Sort Products
      ↓
Display Business Report
```

---

# 📌 Day 20 Quick Reference

```python
import json
```

### JSON String → Python

```python
json.loads(data)
```

### Python → JSON String

```python
json.dumps(data)
```

### JSON File → Python

```python
json.load(file)
```

### Python → JSON File

```python
json.dump(data, file)
```

### Pretty JSON

```python
json.dumps(data, indent=4)
```

or:

```python
json.dump(data, file, indent=4)
```

---

# 📌 Day 20 Summary

Today I learned:

- ✅ What is JSON
- ✅ JSON objects
- ✅ JSON arrays
- ✅ JSON data types
- ✅ JSON list of objects
- ✅ Python `json` module
- ✅ `json.loads()`
- ✅ `json.dumps()`
- ✅ `json.load()`
- ✅ `json.dump()`
- ✅ Creating JSON files
- ✅ Reading JSON files
- ✅ Writing JSON files
- ✅ Processing JSON data
- ✅ JSON + dictionaries
- ✅ JSON + lists
- ✅ JSON + functions
- ✅ JSON + comprehensions
- ✅ JSON + filtering
- ✅ JSON + sorting
- ✅ JSON + exception handling
- ✅ Revenue calculation
- ✅ Business analysis

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
Day 20 → JSON Data Processing
```

---

# 🚀 Next Step — Day 21

The next topic is:

## 📦 Python Modules & Packages

We will learn how to organize Python code into reusable files and modules.

```text
Python Basics
      ↓
Functions
      ↓
File Handling
      ↓
CSV
      ↓
JSON
      ↓
Modules & Packages
      ↓
Reusable Python Code
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