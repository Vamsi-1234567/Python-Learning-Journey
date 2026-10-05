# 🐍 DAY 23 — OOP + Data Processing

## 📚 Python Learning Journey

**Goal:** Python → Data Engineering

Day 23 lo manam **Object-Oriented Programming (OOP) + Data Processing** nerchukuntam.

Day 22 lo manam OOP basics nerchukunnam:

- Class
- Object
- Attributes
- Methods
- `__init__()`
- `self`

Ippudu aa concepts ni actual data processing tho combine chestam.

Mana previous topics:

```text
Lists
Dictionaries
Loops
Functions
Business Logic
OOP
```

anni combine chesi real-world **Pet Shop Data Processing System** build chestam.

---

# 🎯 Day 23 Learning Objectives

Day 23 complete ayyaka nenu:

- OOP objects tho data ni represent cheyyadam
- Multiple objects ni list lo store cheyyadam
- Objects ni loop cheyyadam
- Object methods tho calculations cheyyadam
- Total revenue calculate cheyyadam
- Total stock calculate cheyyadam
- Low-stock products identify cheyyadam
- Expensive products identify cheyyadam
- Highest revenue product find cheyyadam
- OOP + business logic combine cheyyadam
- Real-world data processing structure ardham cheskovadam

nerchukunta.

---

# 1️⃣ Day 22 Revision

Day 22 lo simple Product class create chesam:

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity
```

Object:

```python
product1 = Product("Dog Food", 1200, 2)
```

Attributes:

```python
product1.name
product1.price
product1.quantity
```

---

# 2️⃣ Adding Business Logic

Product class lo method create cheyyachu:

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

    def calculate_revenue(self):
        return self.price * self.quantity
```

Object:

```python
product1 = Product("Dog Food", 1200, 2)

print(product1.calculate_revenue())
```

### Output

```text
2400
```

---

# 3️⃣ Multiple Product Objects

Real business lo one product matrame undadu.

Example:

```python
product1 = Product("Dog Food", 1200, 2)
product2 = Product("Cat Food", 900, 3)
product3 = Product("Treats", 300, 5)
product4 = Product("Bones", 500, 4)
```

Ippudu four objects unnayi.

---

# 4️⃣ Objects ni List lo Store Cheyyadam

Multiple objects ni list lo store cheyyachu.

```python
products = [
    Product("Dog Food", 1200, 2),
    Product("Cat Food", 900, 3),
    Product("Treats", 300, 5),
    Product("Bones", 500, 4)
]
```

Ippudu:

```text
products
   ↓
List
   ↓
Product Objects
```

---

# 5️⃣ Loop Through Objects

List lo unna objects ni loop cheyyachu.

```python
for product in products:
    print(product.name)
```

### Output

```text
Dog Food
Cat Food
Treats
Bones
```

---

# 6️⃣ Display Product Details

```python
for product in products:

    print("Product:", product.name)
    print("Price:", product.price)
    print("Quantity:", product.quantity)
    print()
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

# 7️⃣ Product Revenue

Revenue formula:

```text
Revenue = Price × Quantity
```

Class method:

```python
def calculate_revenue(self):
    return self.price * self.quantity
```

Loop:

```python
for product in products:
    print(product.name, product.calculate_revenue())
```

### Output

```text
Dog Food 2400
Cat Food 2700
Treats 1500
Bones 2000
```

---

# 8️⃣ Calculate Total Revenue

First:

```python
total_revenue = 0
```

Then loop:

```python
for product in products:

    revenue = product.calculate_revenue()

    total_revenue += revenue

print("Total Revenue:", total_revenue)
```

### Output

```text
Total Revenue: 8600
```

Why `total_revenue = 0`?

Because initially mana daggara revenue emi calculate avvaledu.

So:

```text
Starting Total = 0
```

Then each product revenue add chestam.

```text
0
+ 2400
+ 2700
+ 1500
+ 2000
= 8600
```

---

# 9️⃣ Total Stock

Stock formula:

```text
Total Stock = Sum of all quantities
```

Code:

```python
total_stock = 0

for product in products:
    total_stock += product.quantity

print("Total Stock:", total_stock)
```

### Output

```text
Total Stock: 14
```

Calculation:

```text
2 + 3 + 5 + 4 = 14
```

---

# 🔟 Low Stock Detection

Business rule:

```text
Quantity < 5 → Low Stock
```

Class method:

```python
def check_stock(self):

    if self.quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"
```

Loop:

```python
for product in products:

    if product.check_stock() == "Low Stock":
        print(product.name)
```

### Output

```text
Dog Food
Cat Food
Bones
```

---

# 1️⃣1️⃣ Expensive Product Detection

Business rule:

```text
Price >= 1000 → Expensive
```

Method:

```python
def check_price(self):

    if self.price >= 1000:
        return "Expensive"
    else:
        return "Affordable"
```

Loop:

```python
for product in products:

    if product.check_price() == "Expensive":
        print(product.name)
```

### Output

```text
Dog Food
```

---

# 1️⃣2️⃣ Highest Price Product

OOP objects tho `max()` use cheyyachu.

```python
highest_price_product = max(
    products,
    key=lambda product: product.price
)

print(highest_price_product.name)
print(highest_price_product.price)
```

### Output

```text
Dog Food
1200
```

---

# 1️⃣3️⃣ Lowest Price Product

```python
lowest_price_product = min(
    products,
    key=lambda product: product.price
)

print(lowest_price_product.name)
print(lowest_price_product.price)
```

### Output

```text
Treats
300
```

---

# 1️⃣4️⃣ Highest Revenue Product

Revenue based on highest product:

```python
highest_revenue_product = max(
    products,
    key=lambda product: product.calculate_revenue()
)

print(
    highest_revenue_product.name,
    highest_revenue_product.calculate_revenue()
)
```

### Output

```text
Cat Food 2700
```

Because:

```text
Dog Food = 1200 × 2 = 2400
Cat Food = 900 × 3 = 2700
Treats = 300 × 5 = 1500
Bones = 500 × 4 = 2000
```

Highest:

```text
Cat Food → ₹2700
```

---

# 1️⃣5️⃣ Complete Product Class

Now all business logic ni class lo add cheddam.

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

    def calculate_revenue(self):
        return self.price * self.quantity

    def check_stock(self):

        if self.quantity < 5:
            return "Low Stock"
        else:
            return "Stock Available"

    def check_price(self):

        if self.price >= 1000:
            return "Expensive"
        else:
            return "Affordable"

    def display_product(self):

        print("Product:", self.name)
        print("Price:", self.price)
        print("Quantity:", self.quantity)
        print("Revenue:", self.calculate_revenue())
        print("Stock:", self.check_stock())
        print("Price Status:", self.check_price())
```

---

# 1️⃣6️⃣ Create Product Objects

```python
products = [
    Product("Dog Food", 1200, 2),
    Product("Cat Food", 900, 3),
    Product("Treats", 300, 5),
    Product("Bones", 500, 4)
]
```

---

# 1️⃣7️⃣ Display All Products

```python
for product in products:

    product.display_product()

    print()
```

### Output

```text
Product: Dog Food
Price: 1200
Quantity: 2
Revenue: 2400
Stock: Low Stock
Price Status: Expensive

Product: Cat Food
Price: 900
Quantity: 3
Revenue: 2700
Stock: Low Stock
Price Status: Affordable

Product: Treats
Price: 300
Quantity: 5
Revenue: 1500
Stock: Stock Available
Price Status: Affordable

Product: Bones
Price: 500
Quantity: 4
Revenue: 2000
Stock: Low Stock
Price Status: Affordable
```

---

# 1️⃣8️⃣ Complete Data Processing

Now complete analysis create cheddam.

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

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


products = [
    Product("Dog Food", 1200, 2),
    Product("Cat Food", 900, 3),
    Product("Treats", 300, 5),
    Product("Bones", 500, 4)
]


total_revenue = 0
total_stock = 0

for product in products:

    revenue = product.calculate_revenue()

    total_revenue += revenue
    total_stock += product.quantity

    print("Product:", product.name)
    print("Revenue:", revenue)
    print("Stock:", product.check_stock())
    print("Price:", product.check_price())
    print()


print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)
```

### Output

```text
Product: Dog Food
Revenue: 2400
Stock: Low Stock
Price: Expensive

Product: Cat Food
Revenue: 2700
Stock: Low Stock
Price: Affordable

Product: Treats
Revenue: 1500
Stock: Stock Available
Price: Affordable

Product: Bones
Revenue: 2000
Stock: Low Stock
Price: Affordable

Total Revenue: 8600
Total Stock: 14
```

---

# 1️⃣9️⃣ OOP + Filtering

Objects ni condition based on filter cheyyachu.

Example:

```python
expensive_products = []

for product in products:

    if product.price >= 1000:
        expensive_products.append(product)
```

Print:

```python
for product in expensive_products:
    print(product.name)
```

### Output

```text
Dog Food
```

---

# 2️⃣0️⃣ OOP + List Comprehension

Day 16 lo comprehensions nerchukunnam.

Ippudu objects tho use cheddam.

```python
expensive_products = [
    product
    for product in products
    if product.price >= 1000
]
```

Print:

```python
for product in expensive_products:
    print(product.name)
```

### Output

```text
Dog Food
```

---

# 2️⃣1️⃣ Revenue List

Every product revenue ni separate list lo create cheyyachu.

```python
revenues = [
    product.calculate_revenue()
    for product in products
]

print(revenues)
```

### Output

```text
[2400, 2700, 1500, 2000]
```

Total:

```python
print(sum(revenues))
```

### Output

```text
8600
```

---

# 2️⃣2️⃣ Product Names List

```python
product_names = [
    product.name
    for product in products
]

print(product_names)
```

### Output

```text
['Dog Food', 'Cat Food', 'Treats', 'Bones']
```

---

# 2️⃣3️⃣ Sort Products by Price

Day 15 lo sorting nerchukunnam.

Now objects tho:

```python
sorted_products = sorted(
    products,
    key=lambda product: product.price
)

for product in sorted_products:
    print(product.name, product.price)
```

### Output

```text
Treats 300
Bones 500
Cat Food 900
Dog Food 1200
```

---

# 2️⃣4️⃣ Sort Products by Revenue

```python
sorted_products = sorted(
    products,
    key=lambda product: product.calculate_revenue(),
    reverse=True
)

for product in sorted_products:

    print(
        product.name,
        product.calculate_revenue()
    )
```

### Output

```text
Cat Food 2700
Dog Food 2400
Bones 2000
Treats 1500
```

---

# 2️⃣5️⃣ Why OOP + Data Processing?

OOP valla data and business logic organized ga untayi.

Without OOP:

```text
Lists
Dictionaries
Functions
Separate Variables
```

With OOP:

```text
Object
 ├── Data
 └── Behavior
```

Example:

```text
Product Object
│
├── name
├── price
├── quantity
│
├── calculate_revenue()
├── check_stock()
└── check_price()
```

Idi large applications ki useful.

---

# 2️⃣6️⃣ Real-World Business Example

Life Care Pet Zone lo product:

```text
Dog Food
Price = ₹1200
Quantity = 2
```

Object:

```python
dog_food = Product("Dog Food", 1200, 2)
```

Business calculations:

```python
dog_food.calculate_revenue()
```

```python
dog_food.check_stock()
```

```python
dog_food.check_price()
```

So one object contains:

```text
Product Data
+
Product Business Logic
```

---

# 2️⃣7️⃣ Customer Class

OOP data processing only products ki kaadu.

Customer data kuda represent cheyyachu.

```python
class Customer:

    def __init__(self, name, city):
        self.name = name
        self.city = city

    def display_customer(self):
        print("Name:", self.name)
        print("City:", self.city)
```

Create:

```python
customer1 = Customer("Ravi", "Anantapur")

customer1.display_customer()
```

### Output

```text
Name: Ravi
City: Anantapur
```

---

# 2️⃣8️⃣ Order Class

Orders ni kuda object laga represent cheyyachu.

```python
class Order:

    def __init__(self, product_name, quantity, price):
        self.product_name = product_name
        self.quantity = quantity
        self.price = price

    def calculate_total(self):
        return self.quantity * self.price
```

Object:

```python
order1 = Order("Dog Food", 2, 1200)

print(order1.calculate_total())
```

### Output

```text
2400
```

---

# 2️⃣9️⃣ OOP Data Model

Real business system:

```text
Customer
    ↓
Order
    ↓
Product
    ↓
Revenue
```

Example:

```text
Customer
   ↓
Places Order
   ↓
Order contains Product
   ↓
Product has Price & Quantity
   ↓
Revenue calculated
```

This type of modeling is useful when building larger applications.

---

# 3️⃣0️⃣ Data Engineering Connection

Data Engineering lo OOP use chesi data-related entities ni represent cheyyachu.

Example:

```text
DataSource
DataRecord
Pipeline
Validator
Transformer
Loader
```

Possible structure:

```python
class DataRecord:

    def __init__(self, name, value):
        self.name = name
        self.value = value
```

Later:

```text
Extract
   ↓
Transform
   ↓
Validate
   ↓
Load
```

lanti pipelines lo classes and objects useful avutayi.

---

# 3️⃣1️⃣ OOP + Previous Concepts

Mana learning journey ippudu connect avutundi.

```text
Day 07
Lists
   ↓
Day 08
Multiple Lists
   ↓
Day 12
Dictionaries
   ↓
Day 15
Filtering & Sorting
   ↓
Day 16
Comprehensions
   ↓
Day 20
JSON
   ↓
Day 21
Modules
   ↓
Day 22
OOP
   ↓
Day 23
OOP + Data Processing
```

Ippudu previous concepts ni OOP tho combine chestunnam.

---

# 3️⃣2️⃣ Practice Task 1 — Product OOP

Create:

```python
class Product:
```

Attributes:

```text
name
price
quantity
```

Methods:

```text
calculate_revenue()
check_stock()
check_price()
```

Create at least 5 products.

---

# 3️⃣3️⃣ Practice Task 2 — Total Revenue

Using your Product objects:

```text
Calculate total revenue
```

Expected formula:

```text
Revenue = Price × Quantity
```

Use:

```python
total_revenue = 0
```

and a loop.

---

# 3️⃣4️⃣ Practice Task 3 — Low Stock

Find all products where:

```text
Quantity < 5
```

Print:

```text
Low Stock Products
```

---

# 3️⃣5️⃣ Practice Task 4 — Expensive Products

Find products where:

```text
Price >= 1000
```

Print their:

```text
Name
Price
```

---

# 3️⃣6️⃣ Practice Task 5 — Highest Revenue

Find the product with the highest revenue using:

```python
max()
```

and:

```python
lambda
```

Expected output:

```text
Highest Revenue Product: Cat Food
Revenue: 2700
```

---

# 3️⃣7️⃣ Practice Task 6 — Sort by Revenue

Sort products from:

```text
Highest Revenue
        ↓
Lowest Revenue
```

Use:

```python
sorted()
```

with:

```python
key=lambda
```

and:

```python
reverse=True
```

---

# 3️⃣8️⃣ Day 23 Mini Project

## 🐾 Life Care Pet Zone — OOP Data Processing System

Create:

```text
Product Class
      ↓
Product Objects
      ↓
Data Processing
      ↓
Business Analysis
```

Use:

```python
products = [
    Product("Dog Food", 1200, 2),
    Product("Cat Food", 900, 3),
    Product("Treats", 300, 5),
    Product("Bones", 500, 4),
    Product("Shampoo", 1100, 6)
]
```

Calculate:

```text
1. Product Details
2. Product Revenue
3. Total Revenue
4. Total Stock
5. Low Stock Products
6. Expensive Products
7. Highest Price Product
8. Lowest Price Product
9. Highest Revenue Product
10. Products Sorted by Revenue
```

---

# 3️⃣9️⃣ Business Rules

Use these rules:

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

# 4️⃣0️⃣ Common Mistakes

## ❌ Mistake 1 — Forgetting `self`

Wrong:

```python
def calculate_revenue():
```

Correct:

```python
def calculate_revenue(self):
```

---

## ❌ Mistake 2 — Wrong Object Attribute

If:

```python
self.quantity = quantity
```

then:

```python
product.quantity
```

use cheyyali.

---

## ❌ Mistake 3 — Forgetting Object Creation

Class create cheyyadam matrame saripodu.

```python
class Product:
    ...
```

Object kuda create cheyyali:

```python
product1 = Product("Dog Food", 1200, 2)
```

---

## ❌ Mistake 4 — Mixing Class and Object

```text
Class
↓
Blueprint

Object
↓
Actual data
```

Difference clear ga remember cheyyali.

---

# 🧠 Day 23 Key Concepts

```text
Class
Object
Attribute
Method
self
__init__()
List of Objects
Loop Through Objects
Object Methods
Filtering Objects
Sorting Objects
max()
min()
Comprehension
Business Logic
```

---

# 📝 Day 23 Practice Checklist

- [ ] Create Product class
- [ ] Create multiple Product objects
- [ ] Store objects in a list
- [ ] Loop through objects
- [ ] Calculate product revenue
- [ ] Calculate total revenue
- [ ] Calculate total stock
- [ ] Find low-stock products
- [ ] Find expensive products
- [ ] Find highest price
- [ ] Find lowest price
- [ ] Find highest revenue
- [ ] Sort objects
- [ ] Use list comprehension with objects
- [ ] Complete OOP Data Processing Mini Project

---

# 📌 Day 23 Summary

Today I learned how to combine **OOP with Data Processing**.

Important concepts:

```text
Class
   ↓
Object
   ↓
Attributes + Methods
   ↓
List of Objects
   ↓
Loop
   ↓
Data Processing
   ↓
Business Analysis
```

I learned how to process real-world product data using objects and calculate:

```text
Revenue
Stock
Low Stock
Expensive Products
Highest Price
Lowest Price
Highest Revenue
Sorted Revenue
```

This is an important step toward building larger Python and Data Engineering projects.

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
```

---

# 🎯 Next Day

## DAY 24 — Python Mini Project

Next I will combine the Python concepts learned so far into a practical project:

```text
Lists
Dictionaries
Functions
Exception Handling
Files
CSV
JSON
Modules
OOP
Data Processing
Business Logic
```

This will help me practice Python in a more real-world way before moving toward **NumPy, Pandas, SQL, and Data Engineering**.

---

# 👨‍💻 Developed By

## Durga Vamsi

**Python → Data Engineering Learning Journey** 🐍🚀