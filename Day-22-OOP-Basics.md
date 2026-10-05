# 🐍 DAY 22 — Object-Oriented Programming (OOP) Basics

## 📚 Python Learning Journey

**Goal:** Python → Data Engineering

Day 22 lo manam **Object-Oriented Programming (OOP)** basics nerchukuntam.

Ippativaraku manam Python lo:

- Variables
- Data Types
- Conditions
- Loops
- Lists
- Dictionaries
- Functions
- Comprehensions
- Exception Handling
- File Handling
- CSV
- JSON
- Modules & Packages

nerchukunnam.

Ippudu Python programming lo another important concept:

> **Object-Oriented Programming (OOP)**

OOP ante real-world objects ni programming lo represent cheyyadaniki use chese programming approach.

---

# 🎯 Day 22 Learning Objectives

Day 22 complete ayyaka nenu:

- OOP ante enti?
- Class ante enti?
- Object ante enti?
- Attributes ante enti?
- Methods ante enti?
- `__init__()` ante enti?
- `self` enduku use chestam?
- Class nundi objects ela create cheyyali?
- Object attributes ela access cheyyali?
- Methods ela call cheyyali?
- Real-world business data ni OOP tho ela represent cheyyali?

ani explain cheyyagalanu.

---

# 1️⃣ OOP Ante Enti?

OOP = **Object-Oriented Programming**

Simple ga cheppali ante:

> Real-world things ni **objects** laga represent chesi programming cheyyadam OOP.

For example, Life Care Pet Zone lo:

```text
Dog
Cat
Product
Customer
Order
Employee
Pet
```

ivi real-world entities.

Programming lo vatini objects ga represent cheyyachu.

---

# 2️⃣ Real-World Example

Suppose mana pet shop lo oka product undi:

```text
Product Name: Dog Food
Price: ₹1200
Quantity: 2
```

Normal variables tho:

```python
name = "Dog Food"
price = 1200
quantity = 2
```

But products chala unte variables manage cheyyadam difficult.

OOP use chesi:

```text
Product
   ↓
Object
   ↓
Dog Food
```

ila represent cheyyachu.

---

# 3️⃣ Class Ante Enti?

A **class** is a blueprint or template for creating objects.

Simple example:

```text
Class
  ↓
Blueprint

Object
  ↓
Actual item
```

Real life example:

```text
House Plan
   ↓
Blueprint

Actual House
   ↓
Object
```

Python example:

```python
class Product:
    pass
```

Ikkada:

```text
Product
```

is a class.

---

# 4️⃣ Object Ante Enti?

Class nundi create chesina actual instance ni **object** antaru.

Example:

```python
class Product:
    pass

product1 = Product()
```

Ikkada:

```text
Product
```

→ Class

```text
product1
```

→ Object

---

# 5️⃣ First Simple Class

```python
class Product:
    pass
```

Object create cheddam:

```python
product1 = Product()

print(product1)
```

Python memory lo `Product` class ki oka object create chestundi.

---

# 6️⃣ Class Naming Convention

Python classes ki generally **PascalCase** use chestam.

Correct:

```python
class Product:
    pass
```

```python
class PetShop:
    pass
```

```python
class Customer:
    pass
```

Avoid:

```python
class product:
    pass
```

Professional Python code lo:

```text
Product
Customer
PetShop
Order
```

better naming.

---

# 7️⃣ Attributes Ante Enti?

Object ki related information ni **attributes** antam.

Product example:

```text
Name
Price
Quantity
Brand
Category
```

ivi product attributes.

Example:

```python
class Product:
    pass


product1 = Product()

product1.name = "Dog Food"
product1.price = 1200
product1.quantity = 2
```

Ippudu:

```text
product1.name
product1.price
product1.quantity
```

attributes.

---

# 8️⃣ Accessing Attributes

```python
print(product1.name)
print(product1.price)
print(product1.quantity)
```

### Output

```text
Dog Food
1200
2
```

---

# 9️⃣ Multiple Objects

Oka class nundi multiple objects create cheyyachu.

```python
class Product:
    pass


product1 = Product()
product2 = Product()

product1.name = "Dog Food"
product1.price = 1200

product2.name = "Cat Food"
product2.price = 900

print(product1.name)
print(product2.name)
```

### Output

```text
Dog Food
Cat Food
```

Same class:

```text
Product
```

nundi two different objects:

```text
product1
product2
```

create chesam.

---

# 🔟 Why `__init__()`?

Prathi object create chesinappudu manually attributes assign cheyyadam inconvenient.

Example:

```python
product1 = Product()

product1.name = "Dog Food"
product1.price = 1200
product1.quantity = 2
```

Instead `__init__()` use cheyyachu.

---

# 1️⃣1️⃣ `__init__()` Method

`__init__()` object create ayinappudu automatically execute avutundi.

Example:

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity
```

Object create cheddam:

```python
product1 = Product("Dog Food", 1200, 2)
```

Ippudu attributes automatically set avutayi.

---

# 1️⃣2️⃣ Understanding `self`

`self` beginner ki important concept.

Example:

```python
class Product:

    def __init__(self, name, price):
        self.name = name
        self.price = price
```

Ikkada:

```text
name
```

→ function ki vachina value

```text
self.name
```

→ object lo store ayye attribute

Example:

```python
product1 = Product("Dog Food", 1200)
```

Internally conceptually:

```text
product1.name = "Dog Food"
product1.price = 1200
```

---

# 1️⃣3️⃣ Simple `self` Explanation

Suppose:

```python
product1 = Product("Dog Food", 1200)
```

`self` refers to:

```text
product1
```

Another object:

```python
product2 = Product("Cat Food", 900)
```

Ikkada `self` refers to:

```text
product2
```

So:

> `self` current object ni refer chestundi.

---

# 1️⃣4️⃣ Complete Product Class

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity


product1 = Product("Dog Food", 1200, 2)

print(product1.name)
print(product1.price)
print(product1.quantity)
```

### Output

```text
Dog Food
1200
2
```

---

# 1️⃣5️⃣ Multiple Product Objects

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity


product1 = Product("Dog Food", 1200, 2)
product2 = Product("Cat Food", 900, 3)
product3 = Product("Treats", 300, 5)

print(product1.name)
print(product2.name)
print(product3.name)
```

### Output

```text
Dog Food
Cat Food
Treats
```

---

# 1️⃣6️⃣ Methods Ante Enti?

Class lo create chese functions ni generally **methods** antam.

Example:

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

    def calculate_revenue(self):
        return self.price * self.quantity
```

Ikkada:

```python
calculate_revenue()
```

is a method.

---

# 1️⃣7️⃣ Calling a Method

```python
product1 = Product("Dog Food", 1200, 2)

revenue = product1.calculate_revenue()

print(revenue)
```

### Output

```text
2400
```

Because:

```text
Price = 1200
Quantity = 2

Revenue = 1200 × 2

Revenue = 2400
```

---

# 1️⃣8️⃣ Class + Attributes + Methods

Complete structure:

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
```

Method:

```python
print(product1.calculate_revenue())
```

Output:

```text
2400
```

---

# 1️⃣9️⃣ Method With Condition

Business logic ni method lo write cheyyachu.

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

    def check_stock(self):

        if self.quantity < 5:
            return "Low Stock"
        else:
            return "Stock Available"
```

Object:

```python
product1 = Product("Dog Food", 1200, 2)

print(product1.check_stock())
```

### Output

```text
Low Stock
```

---

# 2️⃣0️⃣ Price Check Method

```python
class Product:

    def __init__(self, name, price, quantity):
        self.name = name
        self.price = price
        self.quantity = quantity

    def check_price(self):

        if self.price >= 1000:
            return "Expensive"
        else:
            return "Affordable"
```

Usage:

```python
product1 = Product("Dog Food", 1200, 2)

print(product1.check_price())
```

### Output

```text
Expensive
```

---

# 2️⃣1️⃣ Product Class — Complete Example

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
```

Create object:

```python
product1 = Product("Dog Food", 1200, 2)

print("Product:", product1.name)
print("Price:", product1.price)
print("Quantity:", product1.quantity)
print("Revenue:", product1.calculate_revenue())
print("Stock:", product1.check_stock())
print("Price Status:", product1.check_price())
```

### Output

```text
Product: Dog Food
Price: 1200
Quantity: 2
Revenue: 2400
Stock: Low Stock
Price Status: Expensive
```

---

# 2️⃣2️⃣ Multiple Objects + Methods

```python
product1 = Product("Dog Food", 1200, 2)
product2 = Product("Cat Food", 900, 3)
product3 = Product("Treats", 300, 5)

print(product1.calculate_revenue())
print(product2.calculate_revenue())
print(product3.calculate_revenue())
```

### Output

```text
2400
2700
1500
```

---

# 2️⃣3️⃣ Using a List of Objects

Multiple objects ni list lo store cheyyachu.

```python
products = [
    Product("Dog Food", 1200, 2),
    Product("Cat Food", 900, 3),
    Product("Treats", 300, 5)
]
```

Loop:

```python
for product in products:
    print(product.name)
```

### Output

```text
Dog Food
Cat Food
Treats
```

---

# 2️⃣4️⃣ Calculate Total Revenue

```python
total_revenue = 0

for product in products:
    total_revenue += product.calculate_revenue()

print("Total Revenue:", total_revenue)
```

### Output

```text
Total Revenue: 6600
```

---

# 2️⃣5️⃣ Find Low Stock Products

```python
for product in products:

    if product.quantity < 5:
        print(product.name)
```

### Output

```text
Dog Food
Cat Food
```

---

# 2️⃣6️⃣ Find Expensive Products

```python
for product in products:

    if product.price >= 1000:
        print(product.name)
```

### Output

```text
Dog Food
```

---

# 2️⃣7️⃣ OOP vs Dictionary

Previous days lo product data dictionary tho represent chesam:

```python
product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

OOP lo:

```python
product = Product("Dog Food", 1200, 2)
```

Dictionary:

```text
Data
```

OOP:

```text
Data + Behavior
```

Example:

```python
product.calculate_revenue()
```

Object itself business logic ni handle cheyyagaladu.

---

# 2️⃣8️⃣ OOP Real-World Example

Life Care Pet Zone lo:

```text
Product
Customer
Pet
Order
Employee
Appointment
```

different classes ga represent cheyyachu.

Example:

```python
class Customer:

    def __init__(self, name, phone):
        self.name = name
        self.phone = phone
```

Object:

```python
customer1 = Customer("Ravi", "9876543210")
```

Access:

```python
print(customer1.name)
print(customer1.phone)
```

---

# 2️⃣9️⃣ Pet Class

```python
class Pet:

    def __init__(self, name, species, age):
        self.name = name
        self.species = species
        self.age = age
```

Create object:

```python
pet1 = Pet("Bruno", "Dog", 3)

print(pet1.name)
print(pet1.species)
print(pet1.age)
```

### Output

```text
Bruno
Dog
3
```

---

# 3️⃣0️⃣ Pet Method

```python
class Pet:

    def __init__(self, name, species, age):
        self.name = name
        self.species = species
        self.age = age

    def pet_info(self):
        return f"{self.name} is a {self.species}"
```

Usage:

```python
pet1 = Pet("Bruno", "Dog", 3)

print(pet1.pet_info())
```

### Output

```text
Bruno is a Dog
```

---

# 3️⃣1️⃣ OOP Structure

Basic OOP structure:

```text
Class
  ↓
__init__()
  ↓
Attributes
  ↓
Methods
  ↓
Objects
```

Example:

```python
class Product:

    def __init__(self, name, price):
        self.name = name
        self.price = price

    def show_product(self):
        print(self.name, self.price)
```

Object:

```python
product1 = Product("Dog Food", 1200)
```

---

# 3️⃣2️⃣ Important OOP Terms

| Term | Meaning |
|---|---|
| Class | Blueprint |
| Object | Instance of class |
| Attribute | Object data |
| Method | Function inside class |
| `__init__()` | Initializes object |
| `self` | Current object |

---

# 3️⃣3️⃣ Common Mistakes

## ❌ Mistake 1 — Forgetting `self`

Wrong:

```python
class Product:

    def __init__(name, price):
        name = name
        price = price
```

Correct:

```python
class Product:

    def __init__(self, name, price):
        self.name = name
        self.price = price
```

---

## ❌ Mistake 2 — Forgetting Parentheses

Object creation:

```python
product1 = Product("Dog Food", 1200)
```

Not:

```python
product1 = Product
```

---

## ❌ Mistake 3 — Incorrect Attribute

If:

```python
self.price = price
```

then access:

```python
product1.price
```

Not:

```python
product1.cost
```

unless `cost` was actually created.

---

## ❌ Mistake 4 — Missing `self` in Method

Wrong:

```python
def calculate_revenue():
    return self.price * self.quantity
```

Correct:

```python
def calculate_revenue(self):
    return self.price * self.quantity
```

---

# 3️⃣4️⃣ Practice Task 1 — Product Class

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

Create:

```python
product1
product2
product3
```

Print all details.

---

# 3️⃣5️⃣ Practice Task 2 — Revenue Method

Create:

```python
calculate_revenue()
```

Business rule:

```text
Revenue = Price × Quantity
```

Test with:

```text
Dog Food
₹1200
Quantity 2
```

Expected:

```text
2400
```

---

# 3️⃣6️⃣ Practice Task 3 — Stock Method

Create:

```python
check_stock()
```

Business rule:

```text
Quantity < 5 → Low Stock
Quantity >= 5 → Stock Available
```

---

# 3️⃣7️⃣ Practice Task 4 — Customer Class

Create:

```python
class Customer:
```

Attributes:

```text
name
phone
city
```

Create two customer objects.

Print their details.

---

# 3️⃣8️⃣ Practice Task 5 — Pet Class

Create:

```python
class Pet:
```

Attributes:

```text
name
species
age
```

Method:

```python
pet_info()
```

Expected output:

```text
Bruno is a Dog
```

---

# 3️⃣9️⃣ Day 22 Mini Project

## 🐾 Life Care Pet Zone OOP Product System

Create a `Product` class with:

```text
Name
Price
Quantity
```

Methods:

```text
calculate_revenue()
check_stock()
check_price()
display_product()
```

Create at least 4 products:

```python
products = [
    Product("Dog Food", 1200, 2),
    Product("Cat Food", 900, 3),
    Product("Treats", 300, 5),
    Product("Bones", 500, 4)
]
```

Then calculate:

```text
Product Revenue
Total Revenue
Total Stock
Low Stock Products
Expensive Products
```

---

# 4️⃣0️⃣ Expected Business Analysis

### Dog Food

```text
Price = 1200
Quantity = 2
Revenue = 2400
Status = Low Stock
Price Status = Expensive
```

### Cat Food

```text
Price = 900
Quantity = 3
Revenue = 2700
Status = Low Stock
Price Status = Affordable
```

### Treats

```text
Price = 300
Quantity = 5
Revenue = 1500
Status = Stock Available
Price Status = Affordable
```

### Bones

```text
Price = 500
Quantity = 4
Revenue = 2000
Status = Low Stock
Price Status = Affordable
```

---

# 4️⃣1️⃣ Data Engineering Connection

OOP Data Engineering lo kuda useful.

Large applications lo different entities untayi:

```text
Customer
Product
Order
Transaction
DataSource
Pipeline
Database
```

OOP use chesi these entities ni model cheyyachu.

For example:

```python
class DataSource:

    def __init__(self, name, source_type):
        self.name = name
        self.source_type = source_type
```

Later Data Engineering projects lo:

```text
Data Extraction
Data Transformation
Data Validation
Data Loading
Pipeline Management
```

lanti reusable components build cheyyadaniki OOP concepts help avutayi.

---

# 4️⃣2️⃣ Day 21 vs Day 22

| Day | Topic |
|---|---|
| Day 21 | Modules & Packages |
| Day 22 | OOP Basics |

### Day 21

Code ni different files/modules ga organize cheyyadam nerchukunnam.

### Day 22

Data + behavior ni classes and objects tho organize cheyyadam nerchukuntunnam.

So:

```text
Day 21
Code Organization
       ↓
Modules & Packages

Day 22
Data + Behavior
       ↓
Classes & Objects
```

---

# 🧠 Day 22 Quick Revision

Remember:

```text
Class
   ↓
Blueprint
```

```text
Object
   ↓
Instance of a class
```

```text
Attribute
   ↓
Object data
```

```text
Method
   ↓
Function inside class
```

```text
__init__()
   ↓
Initializes object
```

```text
self
   ↓
Current object
```

---

# 📝 Day 22 Practice Checklist

- [ ] Understand OOP
- [ ] Understand Class
- [ ] Understand Object
- [ ] Create a class
- [ ] Create objects
- [ ] Create attributes
- [ ] Understand `__init__()`
- [ ] Understand `self`
- [ ] Create methods
- [ ] Use methods with objects
- [ ] Create multiple objects
- [ ] Store objects in a list
- [ ] Process objects using loops
- [ ] Build Product class
- [ ] Complete Pet Shop OOP Mini Project

---

# 📌 Day 22 Summary

Today I learned the basics of **Object-Oriented Programming**.

Important concepts:

```text
OOP
Class
Object
Attributes
Methods
__init__()
self
Multiple Objects
List of Objects
```

I also learned how to represent real-world Life Care Pet Zone products using Python classes.

Example:

```python
product1 = Product("Dog Food", 1200, 2)
```

And use methods:

```python
product1.calculate_revenue()
product1.check_stock()
product1.check_price()
```

This is an important foundation for building larger Python applications and Data Engineering projects.

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
```

---

# 🎯 Next Day

## DAY 23 — OOP + Data Processing

Next I will combine:

```text
Classes
Objects
Methods
Lists
Dictionaries
Loops
Business Logic
Data Processing
```

and build a more practical **OOP-based data processing project**.

---

# 👨‍💻 Developed By

## Durga Vamsi

**Python → Data Engineering Learning Journey** 🐍🚀