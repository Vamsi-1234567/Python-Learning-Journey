# 🐍 DAY 21 — Modules and Packages

## 📚 Python Learning Journey

**Goal:** Python → Data Engineering

Day 21 lo manam **Modules and Packages** nerchukuntam.

Ippativaraku manam Python code ni mostly single notebook/file lo rasam.

But real-world projects lo code chala large ga untundi. Anni functions, calculations, validations, data processing logic ni oka single file lo pedithe manage cheyyadam difficult avutundi.

Anduke Python lo code ni **reusable and organized** ga maintain cheyyadaniki:

- Modules
- Packages
- `import`
- `from ... import`
- `as`
- Built-in modules
- User-defined modules

laanti concepts use chestam.

---

# 🎯 Day 21 Learning Objectives

Day 21 complete ayyaka nenu:

- Module ante enti?
- Package ante enti?
- `import` ela use cheyyali?
- `from ... import` ela use cheyyali?
- `as` alias enduku use chestam?
- Built-in Python modules ela use cheyyali?
- Own/custom module ela create cheyyali?
- Module lo functions ela reuse cheyyali?
- Multiple files madhya code ela organize cheyyali?
- Data Engineering projects lo modules enduku important?

ani explain cheyyagalanu.

---

# 1️⃣ Module Ante Enti?

Simple ga cheppali ante:

> **A Python file containing reusable Python code is called a module.**

Python lo `.py` file oka module ga work cheyyagaladu.

Example:

```text
sales.py
```

Indulo sales-related functions unte, vere Python file nundi aa functions ni import cheskoni reuse cheyyachu.

### Simple Structure

```text
project/
│
├── sales.py
└── main.py
```

`main.py` nundi `sales.py` ni import cheskovachu.

---

# 2️⃣ Modules Enduku Use Chestam?

Oka large Python program ni single file lo maintain cheyyadam difficult.

For example:

```text
main.py
```

lo:

- Sales calculations
- Inventory calculations
- Customer logic
- Validation
- File processing
- JSON processing
- CSV processing

anni unte file chala large avutundi.

Instead:

```text
sales.py
inventory.py
validation.py
file_processing.py
main.py
```

ila separate cheyyachu.

Idi code ni:

- Clean
- Reusable
- Maintainable
- Organized
- Easy to debug

ga chestundi.

---

# 3️⃣ Real-Life Example

Mana **Life Care Pet Zone** business ni consider cheddam.

Manaki different types of logic unnayi:

```text
Sales
Inventory
Products
Validation
Reports
```

Vatini separate modules ga maintain cheyyachu.

```text
pet_shop/
│
├── sales.py
├── inventory.py
├── products.py
├── validation.py
└── main.py
```

Idi real-world project structure ki closer ga untundi.

---

# 4️⃣ Creating a Simple Module

First `sales.py` ane file create cheddam.

### sales.py

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Ippudu `sales.py` oka module.

---

# 5️⃣ Import Module

Another file:

### main.py

```python
import sales
```

Ippudu `sales` module ni use cheyyachu.

Function call:

```python
revenue = sales.calculate_revenue(1200, 2)

print(revenue)
```

### Output

```text
2400
```

---

# 6️⃣ `import` Meaning

```python
import sales
```

Meaning:

> `sales.py` module ni mana current Python program lo use cheyyadaniki import chestunnam.

Function access cheyyadaniki:

```python
sales.calculate_revenue()
```

Format:

```python
module_name.function_name()
```

---

# 7️⃣ Module + Multiple Functions

` sales.py `:

```python
def calculate_revenue(price, quantity):
    return price * quantity


def calculate_stock(quantity):
    return quantity


def check_price(price):
    if price >= 1000:
        return "Expensive"
    else:
        return "Affordable"
```

Ippudu `main.py`:

```python
import sales

revenue = sales.calculate_revenue(1200, 2)
stock = sales.calculate_stock(2)
status = sales.check_price(1200)

print(revenue)
print(stock)
print(status)
```

### Output

```text
2400
2
Expensive
```

One module lo multiple reusable functions create cheyyachu.

---

# 8️⃣ `from ... import`

Sometimes complete module ni import cheyyakunda specific function ni directly import cheyyachu.

Example:

```python
from sales import calculate_revenue
```

Ippudu:

```python
revenue = calculate_revenue(1200, 2)

print(revenue)
```

### Output

```text
2400
```

Ikkada:

```python
sales.calculate_revenue()
```

instead of:

```python
calculate_revenue()
```

direct ga function call cheyyachu.

---

# 9️⃣ Import Multiple Functions

Example:

```python
from sales import calculate_revenue, check_price
```

Ippudu:

```python
revenue = calculate_revenue(1200, 2)

status = check_price(1200)

print(revenue)
print(status)
```

### Output

```text
2400
Expensive
```

---

# 🔟 Import Everything

Python lo:

```python
from sales import *
```

ani use cheyyachu.

Idi module lo available unna names/functions ni import chestundi.

Example:

```python
from sales import *

print(calculate_revenue(1200, 2))
print(check_price(1200))
```

But real projects lo `import *` avoid cheyyadam better.

Reason:

- Which function came from which module unclear
- Name conflicts ravachu
- Code readability decrease avutundi

Better:

```python
import sales
```

or:

```python
from sales import calculate_revenue
```

---

# 1️⃣1️⃣ Using `as`

Long module name unte alias create cheyyachu.

Example:

```python
import sales as s
```

Ippudu:

```python
revenue = s.calculate_revenue(1200, 2)

print(revenue)
```

### Output

```text
2400
```

Here:

```text
sales → original module name
s → alias
```

---

# 1️⃣2️⃣ Built-in Modules

Python already many useful modules provide chestundi.

Examples:

```text
math
random
datetime
os
json
csv
```

Manam already `json` and `csv` concepts nerchukunnam.

---

# 1️⃣3️⃣ `math` Module

`math` module mathematical operations kosam use cheyyachu.

```python
import math

print(math.sqrt(25))
```

### Output

```text
5.0
```

Another example:

```python
import math

print(math.ceil(10.2))
print(math.floor(10.8))
```

### Output

```text
11
10
```

---

# 1️⃣4️⃣ `datetime` Module

Date and time operations kosam:

```python
import datetime

today = datetime.date.today()

print(today)
```

Output current date batti change avutundi.

Example output:

```text
2026-09-14
```

---

# 1️⃣5️⃣ `random` Module

Random values generate cheyyadaniki:

```python
import random

number = random.randint(1, 10)

print(number)
```

Output:

```text
7
```

Output every time different ga undachu.

---

# 1️⃣6️⃣ JSON Module Revision

Day 20 lo JSON nerchukunnam.

JSON module ni import chesi:

```python
import json
```

JSON string ni Python object ga convert cheyyachu.

```python
data = '''
[
    {"Name": "Dog Food", "Price": 1200},
    {"Name": "Cat Food", "Price": 900}
]
'''

products = json.loads(data)

print(products)
```

`json` itself Python standard library module.

---

# 1️⃣7️⃣ CSV Module Revision

CSV processing kosam:

```python
import csv
```

Example:

```python
with open("products.csv", "r") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row)
```

Ikkada:

```text
csv
```

is a Python module.

---

# 1️⃣8️⃣ User-Defined Module

Python built-in modules tho paatu manam own modules kuda create cheyyachu.

Example:

```text
project/
│
├── calculations.py
└── main.py
```

### calculations.py

```python
def add(a, b):
    return a + b


def multiply(a, b):
    return a * b
```

### main.py

```python
import calculations

print(calculations.add(10, 20))
print(calculations.multiply(10, 20))
```

### Output

```text
30
200
```

Idi **User-Defined Module**.

---

# 1️⃣9️⃣ Pet Shop Custom Module

Mana learning journey example tho practice cheddam.

Project:

```text
pet_shop/
│
├── sales.py
└── main.py
```

### sales.py

```python
def calculate_revenue(price, quantity):
    return price * quantity


def check_price(price):
    if price >= 1000:
        return "Expensive"
    else:
        return "Affordable"
```

### main.py

```python
import sales

revenue = sales.calculate_revenue(1200, 2)

status = sales.check_price(1200)

print("Revenue:", revenue)
print("Status:", status)
```

### Output

```text
Revenue: 2400
Status: Expensive
```

---

# 2️⃣0️⃣ Inventory Module

Another module create cheddam.

```text
pet_shop/
│
├── sales.py
├── inventory.py
└── main.py
```

### inventory.py

```python
def check_stock(quantity):
    if quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"
```

### main.py

```python
import sales
import inventory

revenue = sales.calculate_revenue(1200, 2)

stock_status = inventory.check_stock(2)

print("Revenue:", revenue)
print("Stock:", stock_status)
```

### Output

```text
Revenue: 2400
Stock: Low Stock
```

Now sales logic and inventory logic separate modules lo unnayi.

---

# 2️⃣1️⃣ Multiple Modules

Real project lo multiple modules use cheyyachu.

```text
pet_shop/
│
├── sales.py
├── inventory.py
├── validation.py
├── products.py
└── main.py
```

### sales.py

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

### inventory.py

```python
def check_stock(quantity):
    if quantity < 5:
        return "Low Stock"
    return "Available"
```

### validation.py

```python
def validate_price(price):
    if price > 0:
        return True
    return False
```

### main.py

```python
import sales
import inventory
import validation

price = 1200
quantity = 2

if validation.validate_price(price):

    revenue = sales.calculate_revenue(price, quantity)

    stock = inventory.check_stock(quantity)

    print("Revenue:", revenue)
    print("Stock:", stock)
```

### Output

```text
Revenue: 2400
Stock: Low Stock
```

---

# 2️⃣2️⃣ Module Organization

Large project lo functions ni purpose batti separate cheyyadam good practice.

Example:

```text
pet_shop/
│
├── sales.py
├── inventory.py
├── validation.py
├── reports.py
└── main.py
```

### sales.py

Sales-related logic.

### inventory.py

Stock-related logic.

### validation.py

Input/data validation logic.

### reports.py

Reporting logic.

### main.py

Main program flow.

---

# 2️⃣3️⃣ Why This Is Important for Data Engineering?

Data Engineering projects lo code single file lo undadu.

Example:

```text
data_pipeline/
│
├── extract.py
├── transform.py
├── load.py
├── validation.py
├── config.py
└── main.py
```

Possible responsibilities:

```text
extract.py
    ↓
Read data

transform.py
    ↓
Clean and transform data

validation.py
    ↓
Validate data

load.py
    ↓
Load data

main.py
    ↓
Run pipeline
```

Idi real-world Data Engineering workflow ki important foundation.

---

# 2️⃣4️⃣ Module vs Function

Important difference:

### Function

Reusable block of code.

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

### Module

Python code ni contain chese `.py` file.

Example:

```text
sales.py
```

Indulo multiple functions undachu:

```python
def calculate_revenue(price, quantity):
    return price * quantity


def calculate_discount(price):
    return price * 0.10
```

So:

```text
Function → reusable logic

Module → reusable Python file/code collection
```

---

# 2️⃣5️⃣ Module vs Package

### Module

Usually one `.py` file.

```text
sales.py
```

### Package

Multiple related Python modules ni organize chese directory.

Example:

```text
pet_shop/
│
├── sales.py
├── inventory.py
├── products.py
└── reports.py
```

Conceptually:

```text
Module
   ↓
sales.py

Package
   ↓
pet_shop/
    ├── sales.py
    ├── inventory.py
    ├── products.py
    └── reports.py
```

---

# 2️⃣6️⃣ Package Structure

A simple package structure:

```text
project/
│
├── main.py
│
└── pet_shop/
    ├── __init__.py
    ├── sales.py
    └── inventory.py
```

`pet_shop` is the package.

Inside it:

```text
sales.py
inventory.py
```

are modules.

---

# 2️⃣7️⃣ Importing From a Package

Example:

```python
from pet_shop import sales
```

Then:

```python
revenue = sales.calculate_revenue(1200, 2)

print(revenue)
```

### Output

```text
2400
```

---

# 2️⃣8️⃣ Import Function From Package Module

```python
from pet_shop.sales import calculate_revenue
```

Then:

```python
print(calculate_revenue(1200, 2))
```

### Output

```text
2400
```

---

# 2️⃣9️⃣ `__name__` Concept

Modules lo frequently kanipinche important concept:

```python
__name__
```

Example:

```python
print(__name__)
```

If file direct ga run chesthe:

```text
__main__
```

ani output ravachu.

---

# 3️⃣0️⃣ `if __name__ == "__main__"`

Common Python pattern:

```python
def calculate_revenue(price, quantity):
    return price * quantity


if __name__ == "__main__":
    print(calculate_revenue(1200, 2))
```

Meaning:

> Ee file direct ga run chesthe ee code execute cheyyi.

But another file nundi import chesthe, main block automatically execute avvakunda reusable functions ni import cheskovachu.

Idi Python projects lo very common pattern.

---

# 3️⃣1️⃣ Complete Example

### sales.py

```python
def calculate_revenue(price, quantity):
    return price * quantity


def check_price(price):
    if price >= 1000:
        return "Expensive"
    else:
        return "Affordable"


if __name__ == "__main__":
    print(calculate_revenue(1200, 2))
```

### main.py

```python
import sales

price = 1200
quantity = 2

revenue = sales.calculate_revenue(price, quantity)

status = sales.check_price(price)

print("Product Price:", price)
print("Quantity:", quantity)
print("Revenue:", revenue)
print("Price Status:", status)
```

### Output

```text
Product Price: 1200
Quantity: 2
Revenue: 2400
Price Status: Expensive
```

---

# 3️⃣2️⃣ Complete Pet Shop Modular Program

Let's combine previous concepts.

### Project Structure

```text
pet_shop/
│
├── sales.py
├── inventory.py
├── validation.py
└── main.py
```

### sales.py

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

### inventory.py

```python
def check_stock(quantity):
    if quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"
```

### validation.py

```python
def validate_price(price):
    if price > 0:
        return True
    else:
        return False
```

### main.py

```python
import sales
import inventory
import validation

products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5}
]

total_revenue = 0

for product in products:

    price = product["Price"]
    quantity = product["Quantity"]

    if validation.validate_price(price):

        revenue = sales.calculate_revenue(price, quantity)

        stock_status = inventory.check_stock(quantity)

        total_revenue += revenue

        print("Product:", product["Name"])
        print("Revenue:", revenue)
        print("Stock:", stock_status)
        print()

print("Total Revenue:", total_revenue)
```

### Output

```text
Product: Dog Food
Revenue: 2400
Stock: Low Stock

Product: Cat Food
Revenue: 2700
Stock: Low Stock

Product: Treats
Revenue: 1500
Stock: Stock Available

Total Revenue: 6600
```

---

# 3️⃣3️⃣ Important Keywords

Day 21 lo important syntax:

```python
import module
```

```python
from module import function
```

```python
from module import function1, function2
```

```python
import module as alias
```

```python
from package import module
```

```python
from package.module import function
```

---

# 3️⃣4️⃣ Common Mistakes

## ❌ Mistake 1 — Wrong Module Name

If file:

```text
sales.py
```

untee:

```python
import sale
```

wrong.

Correct:

```python
import sales
```

---

## ❌ Mistake 2 — Forgetting Module Name

If:

```python
import sales
```

then:

```python
calculate_revenue(1200, 2)
```

may not work as expected because function was imported through the module.

Use:

```python
sales.calculate_revenue(1200, 2)
```

Or explicitly:

```python
from sales import calculate_revenue
```

---

## ❌ Mistake 3 — Circular Imports

Example:

```text
sales.py → imports inventory.py
inventory.py → imports sales.py
```

This can create circular dependency problems.

Beginner projects lo modules ni simple and clearly separated ga maintain cheyyadam better.

---

## ❌ Mistake 4 — Using `import *`

Avoid:

```python
from sales import *
```

Prefer:

```python
import sales
```

or:

```python
from sales import calculate_revenue
```

---

# 3️⃣5️⃣ Practice Task 1 — Create Calculator Module

Create:

```text
calculator.py
```

Functions:

```python
add()
subtract()
multiply()
divide()
```

Then `main.py` nundi import chesi use cheyyandi.

---

# 3️⃣6️⃣ Practice Task 2 — Sales Module

Create:

```text
sales.py
```

Function:

```python
calculate_revenue(price, quantity)
```

Then `main.py` lo import chesi:

```text
Dog Food
Price = 1200
Quantity = 2
```

revenue calculate cheyyandi.

Expected:

```text
Revenue: 2400
```

---

# 3️⃣7️⃣ Practice Task 3 — Inventory Module

Create:

```text
inventory.py
```

Function:

```python
check_stock(quantity)
```

Business rule:

```text
Quantity < 5 → Low Stock
Quantity >= 5 → Stock Available
```

Test:

```python
print(check_stock(2))
print(check_stock(10))
```

Expected:

```text
Low Stock
Stock Available
```

---

# 3️⃣8️⃣ Practice Task 4 — Product Analysis Modules

Create:

```text
pet_shop/
│
├── sales.py
├── inventory.py
├── pricing.py
└── main.py
```

### sales.py

Create:

```python
calculate_revenue()
```

### inventory.py

Create:

```python
check_stock()
```

### pricing.py

Create:

```python
check_price()
```

Then all modules ni `main.py` lo import cheyyandi.

---

# 3️⃣9️⃣ Day 21 Mini Project

## 🐾 Pet Shop Modular Business Analysis

Create:

```text
pet_shop/
│
├── sales.py
├── inventory.py
├── pricing.py
└── main.py
```

Use:

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]
```

Implement:

### Sales

```text
Product Revenue
Total Revenue
```

### Inventory

```text
Total Stock
Low Stock Products
```

### Pricing

```text
Expensive Products
Affordable Products
```

### Main Program

`main.py` should import the modules and run the complete analysis.

---

# 4️⃣0️⃣ Business Rules

For this project:

```text
Revenue = Price × Quantity
```

```text
Low Stock = Quantity < 5
```

```text
Expensive Product = Price >= 1000
```

---

# 4️⃣1️⃣ Expected Analysis

For:

```text
Dog Food → 1200 × 2 = 2400
Cat Food → 900 × 3 = 2700
Treats → 300 × 5 = 1500
Bones → 500 × 4 = 2000
```

Total Revenue:

```text
2400 + 2700 + 1500 + 2000
= 8600
```

Total Stock:

```text
2 + 3 + 5 + 4
= 14
```

Low Stock:

```text
Dog Food
Cat Food
Bones
```

Expensive:

```text
Dog Food
```

---

# 4️⃣2️⃣ Day 20 vs Day 21

| Day | Topic |
|---|---|
| Day 20 | JSON Data Processing |
| Day 21 | Modules and Packages |

### Day 20

JSON data ni read/process cheyyadam nerchukunnam.

### Day 21

Code ni reusable and organized modules ga divide cheyyadam nerchukuntunnam.

So:

```text
Day 20
JSON Data
   ↓
Process Data

Day 21
Python Code
   ↓
Organize + Reuse
```

---

# 4️⃣3️⃣ Data Engineering Connection

Data Engineer ki modular coding chala important.

Real-world pipeline example:

```text
Raw Data
   ↓
Extract
   ↓
Transform
   ↓
Validate
   ↓
Load
   ↓
Report
```

Code ni ila divide cheyyachu:

```text
extract.py
transform.py
validate.py
load.py
report.py
main.py
```

Each module ki specific responsibility untundi.

This is the foundation for writing maintainable Data Engineering code.

---

# 🧠 Day 21 Key Concepts

Remember these:

```text
Module
   ↓
Python file containing reusable code
```

```text
Package
   ↓
Collection of related modules
```

```python
import sales
```

```python
from sales import calculate_revenue
```

```python
import sales as s
```

```python
from pet_shop.sales import calculate_revenue
```

And:

```python
if __name__ == "__main__":
```

is a common Python pattern for code that should run when a file is executed directly.

---

# 📝 Day 21 Practice Checklist

- [ ] Understand Module
- [ ] Understand Package
- [ ] Use `import`
- [ ] Use `from ... import`
- [ ] Use `as`
- [ ] Practice built-in modules
- [ ] Create a custom module
- [ ] Import custom functions
- [ ] Create multiple modules
- [ ] Understand `__name__`
- [ ] Practice `if __name__ == "__main__"`
- [ ] Complete Pet Shop modular project

---

# 📌 Day 21 Summary

Today I learned how to organize Python code using **Modules and Packages**.

Important concepts:

```text
Modules
Packages
import
from ... import
as
Built-in Modules
User-Defined Modules
Multiple Modules
__name__
__main__
```

I also learned how to divide Pet Shop business logic into separate modules such as:

```text
Sales
Inventory
Pricing
Validation
```

This makes Python programs:

```text
Reusable
Organized
Maintainable
Scalable
```

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
```

---

# 🎯 Next Day

## DAY 22 — Object-Oriented Programming (OOP) Basics

Next I will start learning:

```text
Classes
Objects
Attributes
Methods
__init__()
self
Constructors
```

OOP is another important Python foundation before moving deeper into Data Engineering projects.

---

# 👨‍💻 Developed By

## Durga Vamsi

**Python → Data Engineering Learning Journey** 🐍🚀