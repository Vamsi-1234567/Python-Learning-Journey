# 🐍 DAY 20 — JSON Data Processing

## 📌 Day 20 Goal

Today we will learn **JSON Data Processing in Python**.

Day 19 lo manam **CSV files** tho work chesam.

Ippudu manam **JSON** data ni read, parse, process, modify, and analyze cheyyadam nerchukundam.

JSON is very important in **Data Engineering** because APIs, applications, websites, and many data systems JSON format lo data exchange chestayi.

Today we will learn:

- What is JSON?
- Why JSON is important
- JSON structure
- Objects and arrays
- JSON keys and values
- Python `json` module
- `json.loads()`
- `json.dumps()`
- `json.load()`
- `json.dump()`
- JSON string → Python object
- Python object → JSON string
- JSON file → Python object
- Python object → JSON file
- List of dictionaries
- JSON + functions
- JSON + filtering
- JSON + sorting
- JSON + business analysis
- JSON + Exception Handling
- API and Data Engineering connection

---

# 1️⃣ What is JSON?

JSON stands for:

```text
JavaScript Object Notation
```

JSON is a lightweight format used to store and exchange data.

Simple JSON example:

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

JSON chusthe Python dictionary laga kanipistundi.

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

Syntax similar ga unna, JSON is a **data interchange format**, Python dictionary is a **Python data structure**.

---

# 2️⃣ Why JSON is Important?

Real-world applications madhya data exchange kosam JSON chala common.

Example:

```text
Application
    ↓
API
    ↓
JSON
    ↓
Python
    ↓
Data Processing
```

For example, oka online store product API ila data return cheyyachu:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

Python aa JSON data ni read chesi analysis cheyyagaladu.

---

# 3️⃣ JSON Basic Structure

JSON mainly two important structures ni use chestundi:

```text
Object
Array
```

Python lo roughly:

```text
JSON Object → Python Dictionary
JSON Array  → Python List
```

---

# 4️⃣ JSON Object

JSON object `{ }` brackets tho represent chestam.

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

Idi oka product information.

Structure:

```text
{
    Key : Value
}
```

Multiple key-value pairs:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

---

# 5️⃣ JSON Array

JSON array `[ ]` brackets tho represent chestam.

Example:

```json
[
    "Dog Food",
    "Cat Food",
    "Treats"
]
```

Python equivalent:

```python
[
    "Dog Food",
    "Cat Food",
    "Treats"
]
```

So:

```text
JSON Array
    ↓
Python List
```

---

# 6️⃣ List of JSON Objects

Real-world data lo multiple records untayi.

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
    }
]
```

Python lo idi:

```python
list of dictionaries
```

This is exactly the structure manam previous days lo practice chesam.

---

# 7️⃣ Python `json` Module

Python lo JSON processing kosam built-in module undi:

```python
json
```

Import cheyyali:

```python
import json
```

External package install cheyyalsina avasaram ledu.

---

# 8️⃣ JSON String

First JSON data ni Python string lo store cheddam.

```python
import json

data = '''
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
'''
```

Ikkada `data` is a Python string.

JSON structure string lopala undi.

---

# 9️⃣ `json.loads()`

`loads()` means:

```text
JSON String → Python Object
```

Example:

```python
import json

data = '''
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
'''

product = json.loads(data)

print(product)
```

Output:

```text
{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
```

JSON object Python dictionary ga convert ayyindi.

---

# 🔟 Understanding `loads()`

Remember:

```text
loads
  ↓
Load String
```

Syntax:

```python
json.loads(json_string)
```

Use when JSON data already Python string form lo unte.

---

# 1️⃣1️⃣ Access JSON Data

`json.loads()` taruvata manaki Python dictionary vastundi.

```python
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

Now normal Python dictionary laga process cheyyachu.

---

# 1️⃣2️⃣ JSON List Example

```python
import json

data = '''
[
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5}
]
'''

products = json.loads(data)

print(products)
```

Output:

```text
[
    {'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2},
    {'Name': 'Cat Food', 'Price': 900, 'Quantity': 3},
    {'Name': 'Treats', 'Price': 300, 'Quantity': 5}
]
```

Now:

```text
JSON String
     ↓
json.loads()
     ↓
Python List
     ↓
Dictionaries
```

---

# 1️⃣3️⃣ Loop Through JSON Data

```python
import json

data = '''
[
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5}
]
'''

products = json.loads(data)

for product in products:

    print(product["Name"])
```

Output:

```text
Dog Food
Cat Food
Treats
```

JSON data convert ayyaka normal Python loops use cheyyachu.

---

# 1️⃣4️⃣ Calculate Revenue from JSON

Business Rule:

```text
Revenue = Price × Quantity
```

Example:

```python
import json

data = '''
[
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5}
]
'''

products = json.loads(data)

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
```

---

# 1️⃣5️⃣ Calculate Total Revenue

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
Total Revenue: 6600
```

Calculation:

```text
Dog Food = 1200 × 2 = 2400
Cat Food = 900 × 3 = 2700
Treats   = 300 × 5 = 1500

Total = 6600
```

---

# 1️⃣6️⃣ `json.dumps()`

Now reverse operation chuddam.

`dumps()` means:

```text
Python Object → JSON String
```

Example:

```python
import json

product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}

data = json.dumps(product)

print(data)
```

Output:

```text
{"Name": "Dog Food", "Price": 1200, "Quantity": 2}
```

Remember:

```text
loads() → JSON → Python
dumps() → Python → JSON
```

---

# 1️⃣7️⃣ `loads()` vs `dumps()`

Very important:

| Function | Conversion |
|---|---|
| `json.loads()` | JSON String → Python |
| `json.dumps()` | Python → JSON String |
| `json.load()` | JSON File → Python |
| `json.dump()` | Python → JSON File |

Easy way to remember:

```text
s = String
```

So:

```text
loads()  → String input
dumps()  → String output
```

---

# 1️⃣8️⃣ Pretty JSON Using `indent`

By default:

```python
data = json.dumps(product)
```

output single line lo untundi.

Readable format kosam:

```python
data = json.dumps(
    product,
    indent=4
)

print(data)
```

Output:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

`indent=4` JSON ni readable format lo display chestundi.

---

# 1️⃣9️⃣ JSON File

JSON data ni file lo store cheyyachu.

Example file:

```text
products.json
```

Contents:

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
    }
]
```

---

# 2️⃣0️⃣ Reading JSON File Using `json.load()`

JSON file ni read cheyyadaniki:

```python
json.load()
```

Example:

```python
import json

with open("products.json", "r") as file:

    products = json.load(file)

print(products)
```

Output:

```text
[
    {'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2},
    {'Name': 'Cat Food', 'Price': 900, 'Quantity': 3},
    {'Name': 'Treats', 'Price': 300, 'Quantity': 5}
]
```

---

# 2️⃣1️⃣ `json.load()` Meaning

Remember:

```text
load()
 ↓
File → Python
```

Example:

```python
products = json.load(file)
```

JSON file data Python object ga convert avutundi.

---

# 2️⃣2️⃣ Loop Through JSON File

```python
import json

with open("products.json", "r") as file:

    products = json.load(file)


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
```

---

# 2️⃣3️⃣ Writing JSON File Using `json.dump()`

Python data:

```python
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
    }
]
```

Write to JSON file:

```python
import json

with open("products.json", "w") as file:

    json.dump(
        products,
        file,
        indent=4
    )
```

Now `products.json` contains formatted JSON.

---

# 2️⃣4️⃣ `json.dump()` Meaning

Remember:

```text
Python Object
      ↓
json.dump()
      ↓
JSON File
```

Example:

```python
json.dump(products, file, indent=4)
```

---

# 2️⃣5️⃣ Complete JSON File Write

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

---

# 2️⃣6️⃣ Read JSON and Calculate Total Stock

```python
import json

with open("products.json", "r") as file:

    products = json.load(file)


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

# 2️⃣7️⃣ JSON + Functions

Day 10–11 lo manam functions nerchukunnam.

Now JSON data tho function use cheddam.

```python
def calculate_revenue(product):

    return (
        product["Price"]
        * product["Quantity"]
    )
```

Use:

```python
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

# 2️⃣8️⃣ JSON + Filtering

Day 15–16 concepts ni JSON tho combine cheddam.

Expensive products:

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

# 2️⃣9️⃣ JSON + Low Stock

Business Rule:

```text
Quantity < 3
```

Code:

```python
low_stock_products = [
    product
    for product in products
    if product["Quantity"] < 3
]

print(low_stock_products)
```

Output:

```text
[
    {'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
]
```

---

# 3️⃣0️⃣ JSON + Sorting

Day 15 lo sorting nerchukunnam.

JSON data Python list ga convert ayyaka sorting easy.

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

# 3️⃣1️⃣ Sort by Revenue

```python
sorted_products = sorted(
    products,
    key=lambda product:
        product["Price"] * product["Quantity"],
    reverse=True
)

for product in sorted_products:

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
Cat Food 2700
Dog Food 2400
Bones 2000
Treats 1500
```

---

# 3️⃣2️⃣ Find Highest Revenue Product

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

# 3️⃣3️⃣ JSON + Exception Handling

Day 17 lo manam Exception Handling nerchukunnam.

JSON file missing ayithe:

```text
FileNotFoundError
```

JSON format wrong ayithe:

```text
JSONDecodeError
```

Handle cheyyachu.

```python
import json

try:

    with open("products.json", "r") as file:

        products = json.load(file)

except FileNotFoundError:

    print("JSON file not found")

except json.JSONDecodeError:

    print("Invalid JSON data")
```

This is very important for reliable data processing.

---

# 3️⃣4️⃣ Invalid JSON Example

Suppose JSON file lo:

```text
{
    "Name": "Dog Food",
    "Price": 1200,
}
```

This is invalid JSON because trailing comma issue undi.

When we try:

```python
json.load(file)
```

Python can raise:

```text
JSONDecodeError
```

Handle:

```python
try:

    with open("products.json", "r") as file:
        data = json.load(file)

except json.JSONDecodeError:

    print("Invalid JSON format")
```

---

# 3️⃣5️⃣ JSON Data Validation

JSON data lo required fields unnayo check cheyyachu.

```python
for product in products:

    if "Name" not in product:
        print("Name is missing")

    if "Price" not in product:
        print("Price is missing")

    if "Quantity" not in product:
        print("Quantity is missing")
```

This is useful when processing external data.

---

# 3️⃣6️⃣ JSON + Type Conversion

JSON generally numeric values ni number ga preserve cheyyagaladu.

Example:

```json
{
    "Price": 1200,
    "Quantity": 2
}
```

After:

```python
product = json.loads(data)
```

Python lo:

```python
product["Price"]
```

is an integer.

Unlike CSV, every value automatically string ga read avvalsina avasaram ledu.

Still, external JSON data ni process chesetappudu validation important.

---

# 3️⃣7️⃣ JSON vs CSV

| Feature | CSV | JSON |
|---|---|---|
| Structure | Rows & Columns | Objects & Arrays |
| Nested Data | Difficult | Easy |
| Python Mapping | Rows | Dictionaries |
| Common Use | Tables | APIs / Applications |
| Python Module | `csv` | `json` |
| Read | `csv.reader()` | `json.load()` |
| Dictionary Read | `csv.DictReader()` | `json.load()` |

Simple understanding:

```text
CSV → Tabular Data
JSON → Structured / Nested Data
```

---

# 3️⃣8️⃣ JSON Nested Data

JSON lo nested data store cheyyachu.

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2,
    "Supplier": {
        "Name": "Pet Supplies Ltd",
        "City": "Hyderabad"
    }
}
```

Python lo:

```python
product["Supplier"]["Name"]
```

Output:

```text
Pet Supplies Ltd
```

And:

```python
product["Supplier"]["City"]
```

Output:

```text
Hyderabad
```

This is one major difference between simple CSV and JSON.

---

# 3️⃣9️⃣ JSON Nested List

JSON can also contain lists inside objects.

Example:

```json
{
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2,
    "Categories": [
        "Dog",
        "Food",
        "Pet"
    ]
}
```

Python:

```python
print(product["Categories"])
```

Output:

```text
['Dog', 'Food', 'Pet']
```

Access individual value:

```python
print(product["Categories"][0])
```

Output:

```text
Dog
```

---

# 4️⃣0️⃣ Complete JSON Business Analysis

```python
import json


def calculate_revenue(product):

    return (
        product["Price"]
        * product["Quantity"]
    )


try:

    with open("products.json", "r") as file:

        products = json.load(file)


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
        key=lambda product:
            product["Price"]
    )


    highest_revenue_product = max(
        products,
        key=lambda product:
            product["Price"]
            * product["Quantity"]
    )


    print()
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


except FileNotFoundError:

    print("JSON file not found")


except json.JSONDecodeError:

    print("Invalid JSON format")
```

---

# 4️⃣1️⃣ Expected Output

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

# 4️⃣2️⃣ JSON Processing Flow

Today we learned:

```text
JSON Data
    ↓
Read / Parse
    ↓
Python Object
    ↓
Dictionary / List
    ↓
Validate
    ↓
Transform
    ↓
Filter
    ↓
Sort
    ↓
Calculate
    ↓
Business Analysis
```

This is a very important Data Engineering pattern.

---

# 4️⃣3️⃣ API Connection

Later manam APIs nerchukuntam.

API usually JSON response ivvachu.

Example:

```text
Python
   ↓
API Request
   ↓
JSON Response
   ↓
json.loads()
   ↓
Python Data
   ↓
Process
   ↓
Store
```

For example:

```python
data = response.text

products = json.loads(data)
```

Then:

```python
for product in products:
    print(product["Name"])
```

So today's JSON knowledge future lo **API data processing** ki direct ga useful avutundi.

---

# 4️⃣4️⃣ Data Engineering Connection 🔥

Data Engineer ga manam different sources nundi data receive cheyyali.

Sources:

```text
CSV
JSON
API
Database
Logs
Applications
```

JSON especially important for:

```text
REST APIs
Web Applications
Cloud Services
Microservices
Data Exchange
Configuration Files
```

Typical pipeline:

```text
API
 ↓
JSON
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

This is an actual Data Engineering workflow.

---

# 4️⃣5️⃣ Day 18 → Day 19 → Day 20

```text
Day 18
File Handling
      ↓
Day 19
CSV Data Processing
      ↓
Day 20
JSON Data Processing
```

We are now moving from basic Python file operations into **structured data processing**.

---

# 4️⃣6️⃣ Important JSON Functions

| Function | Purpose |
|---|---|
| `json.loads()` | JSON String → Python |
| `json.dumps()` | Python → JSON String |
| `json.load()` | JSON File → Python |
| `json.dump()` | Python → JSON File |

### Easy Memory Trick

```text
s = String
```

Therefore:

```text
loads()  → String → Python
dumps()  → Python → String
```

Without `s`:

```text
load()   → File → Python
dump()   → Python → File
```

---

# 4️⃣7️⃣ Common Mistakes

### ❌ Mistake 1 — Forgetting `import json`

Wrong:

```python
data = json.loads(text)
```

Correct:

```python
import json
```

---

### ❌ Mistake 2 — Confusing `load()` and `loads()`

Remember:

```text
load()  → File
loads() → String
```

---

### ❌ Mistake 3 — Confusing `dump()` and `dumps()`

Remember:

```text
dump()  → File
dumps() → String
```

---

### ❌ Mistake 4 — Invalid JSON

JSON requires proper syntax.

Correct:

```json
{
    "Name": "Dog Food",
    "Price": 1200
}
```

---

### ❌ Mistake 5 — Using Single Quotes in JSON

Python dictionary:

```python
{
    "Name": "Dog Food"
}
```

JSON standard syntax uses double quotes:

```json
{
    "Name": "Dog Food"
}
```

---

### ❌ Mistake 6 — Forgetting Type/Structure Validation

External JSON data always trusted ani assume cheyyakudadhu.

Check required fields:

```python
if "Price" in product:
    print(product["Price"])
```

---

# 4️⃣8️⃣ Day 20 Practice Tasks

## 🟢 Task 1 — JSON String

Create a JSON string containing:

```text
Name
Price
Quantity
```

Use:

```python
json.loads()
```

to convert it into a Python dictionary.

---

## 🟢 Task 2 — Access Values

Print:

```text
Name
Price
Quantity
```

from the converted dictionary.

---

## 🟢 Task 3 — JSON List

Create a JSON list containing 4 products.

Convert it using:

```python
json.loads()
```

---

## 🟡 Task 4 — Product Revenue

Calculate:

```text
Revenue = Price × Quantity
```

for every product.

---

## 🟡 Task 5 — Total Revenue

Calculate total revenue.

---

## 🟡 Task 6 — Total Stock

Calculate total stock.

---

## 🟡 Task 7 — Expensive Products

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

## 🟠 Task 10 — JSON File

Create:

```text
products.json
```

Write product data using:

```python
json.dump()
```

Then read it using:

```python
json.load()
```

---

# 4️⃣9️⃣ 🔴 Day 20 Mini Project

# 🐾 Life Care Pet Zone — JSON Product Analysis

Create:

```text
products.json
```

with:

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

Your Python program should:

```text
Read JSON File
      ↓
Convert JSON
      ↓
Validate Data
      ↓
Calculate Product Revenue
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

# 5️⃣0️⃣ Day 20 Challenge 🚀

Create a function:

```python
def analyze_products(products):
```

The function should return:

```text
Total Products
Total Revenue
Total Stock
Highest Price Product
Lowest Price Product
Highest Revenue Product
Expensive Products
Low Stock Products
```

Then call:

```python
analyze_products(products)
```

This challenge combines almost everything you have learned so far.

---

# 📌 Day 20 Summary

Today I learned:

- ✅ What is JSON
- ✅ JSON objects
- ✅ JSON arrays
- ✅ JSON keys and values
- ✅ Python `json` module
- ✅ `json.loads()`
- ✅ `json.dumps()`
- ✅ `json.load()`
- ✅ `json.dump()`
- ✅ JSON string processing
- ✅ JSON file processing
- ✅ List of dictionaries
- ✅ JSON nested data
- ✅ JSON + functions
- ✅ JSON + filtering
- ✅ JSON + sorting
- ✅ JSON + `max()`
- ✅ JSON + business logic
- ✅ JSON + exception handling
- ✅ JSON data validation
- ✅ API data concept
- ✅ Data Engineering workflow

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

We will learn how to organize Python code into reusable files and use modules.

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