# 🐍 Python Learning Journey — Day 12

# 📅 Day 12 — Dictionaries & List of Dictionaries

Welcome to **Day 12** of my Python Learning Journey! 🚀

Day 12 lo, Python lo **Dictionaries** gurinchi nerchukunnanu.

Previous days lo Lists use chesi multiple values ni store chesanu.

But real-world data lo product ki different details untayi:

```text
Product Name
Price
Quantity
Brand
Category
```

Ila related information ni clear ga organize cheyyadaniki **Dictionary** chala useful.

Today I learned:

```text
Dictionary
    ↓
Key + Value
    ↓
Access Data
    ↓
Update Data
    ↓
Add Data
    ↓
Delete Data
    ↓
Loop Through Dictionary
    ↓
List of Dictionaries
    ↓
Dictionary + Functions
```

---

# 🎯 Day 12 Learning Goals

Today I will learn:

- Dictionary ante enti
- Key and Value
- Dictionary create cheyyadam
- Values access cheyyadam
- Values update cheyyadam
- New keys add cheyyadam
- Keys delete cheyyadam
- `len()`
- `keys()`
- `values()`
- `items()`
- Key exists check cheyyadam
- Dictionary ni loop cheyyadam
- List of Dictionaries
- Dictionary + Functions
- Real-world product data handling

---

# 🧠 1. What is a Dictionary?

Python Dictionary is used to store data in **key-value pairs**.

Simple ga cheppali ante:

```text
Key → Value
```

Example:

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}
```

Here:

```text
"name"     → "Dog Food"
"price"    → 1200
"quantity" → 2
```

Key is like a label.

Value is actual data.

---

# 🔑 2. Dictionary Structure

Basic structure:

```python
dictionary = {
    "key": "value"
}
```

Example:

```python
product = {
    "name": "Dog Food",
    "price": 1200
}
```

Here:

```text
name  → Dog Food
price → 1200
```

---

# 🏪 3. Life Care Pet Zone Example

Let's create a product dictionary.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

print(product)
```

### Output

```text
{'name': 'Dog Food', 'price': 1200, 'quantity': 2}
```

Dictionary lo product ki related information one place lo store chesam.

---

# 🔍 4. Access Dictionary Values

Dictionary lo value access cheyyadaniki key use chestam.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

print(product["name"])
print(product["price"])
print(product["quantity"])
```

### Output

```text
Dog Food
1200
2
```

Important:

```python
product["name"]
```

Meaning:

```text
product dictionary lo "name" key value ivvu
```

---

# 🧩 5. Key and Value

Example:

```python
product = {
    "name": "Dog Food",
    "price": 1200
}
```

Here:

```text
Key       Value
----------------
name      Dog Food
price     1200
```

Dictionary lo each key ki corresponding value untundi.

---

# ✏️ 6. Update a Dictionary Value

Existing value ni change cheyyachu.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

product["price"] = 1500

print(product)
```

### Output

```text
{'name': 'Dog Food', 'price': 1500, 'quantity': 2}
```

Price:

```text
1200 → 1500
```

change ayyindi.

---

# ➕ 7. Add a New Key

Dictionary lo new information add cheyyachu.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

product["brand"] = "Pedigree"

print(product)
```

### Output

```text
{'name': 'Dog Food', 'price': 1200, 'quantity': 2, 'brand': 'Pedigree'}
```

New key:

```text
brand
```

New value:

```text
Pedigree
```

---

# ❌ 8. Delete a Key

Dictionary nundi key-value pair remove cheyyadaniki `del` use cheyyachu.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2,
    "brand": "Pedigree"
}

del product["brand"]

print(product)
```

### Output

```text
{'name': 'Dog Food', 'price': 1200, 'quantity': 2}
```

`brand` remove ayyindi.

---

# 📏 9. Dictionary Length

`len()` use chesi dictionary lo enni key-value pairs unnayo telusukovachu.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

print(len(product))
```

### Output

```text
3
```

Because there are 3 keys:

```text
name
price
quantity
```

---

# 🔑 10. Dictionary `keys()`

`keys()` dictionary lo unna keys ni return chestundi.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

print(product.keys())
```

### Output

```text
dict_keys(['name', 'price', 'quantity'])
```

---

# 💰 11. Dictionary `values()`

`values()` dictionary lo unna values ni return chestundi.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

print(product.values())
```

### Output

```text
dict_values(['Dog Food', 1200, 2])
```

---

# 🔄 12. Dictionary `items()`

`items()` key and value rendu ni access cheyyadaniki useful.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

print(product.items())
```

### Output

```text
dict_items([
    ('name', 'Dog Food'),
    ('price', 1200),
    ('quantity', 2)
])
```

---

# 🔁 13. Loop Through Dictionary

Dictionary ni loop cheyyachu.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

for key in product:
    print(key)
```

### Output

```text
name
price
quantity
```

By default, loop dictionary keys meeda run avutundi.

---

# 🔑 14. Loop Through Keys

```python
for key in product.keys():
    print(key)
```

### Output

```text
name
price
quantity
```

---

# 💰 15. Loop Through Values

```python
for value in product.values():
    print(value)
```

### Output

```text
Dog Food
1200
2
```

---

# 🔄 16. Loop Through Key + Value

`items()` use chesi key and value rendu access cheyyachu.

```python
for key, value in product.items():
    print(key, ":", value)
```

### Output

```text
name : Dog Food
price : 1200
quantity : 2
```

This is very useful when working with structured data.

---

# 🔎 17. Check Whether a Key Exists

Dictionary lo key unda leda check cheyyachu.

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

if "price" in product:
    print("Price exists")
```

### Output

```text
Price exists
```

---

# 🛡️ 18. Why Check Keys?

Suppose dictionary lo `"brand"` key ledu.

If we directly do:

```python
print(product["brand"])
```

Error ravachu.

So first:

```python
if "brand" in product:
    print(product["brand"])
```

This is safer data handling.

---

# 📦 19. List of Dictionaries

Real-world data lo one product matrame undadu.

Multiple products untayi.

Each product oka dictionary ga store cheyyachu.

Then multiple dictionaries ni list lo store cheyyachu.

Example:

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

This is called:

**List of Dictionaries**

---

# 🔄 20. Loop Through List of Dictionaries

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

for product in products:
    print(product)
```

### Output

```text
{'name': 'Dog Food', 'price': 1200, 'quantity': 2}
{'name': 'Cat Food', 'price': 900, 'quantity': 3}
{'name': 'Treats', 'price': 300, 'quantity': 5}
```

---

# 🎯 21. Access Product Information

Instead of printing complete dictionary, specific values access cheyyachu.

```python
for product in products:

    print("Product:", product["name"])
    print("Price:", product["price"])
    print("Quantity:", product["quantity"])
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
```

---

# 💰 22. Calculate Revenue from Dictionary

Day 09 and Day 11 lo revenue calculation nerchukunnam.

Now dictionary data tho calculate cheddam.

Business rule:

```text
Revenue = Price × Quantity
```

Code:

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

# 🧮 23. Total Revenue Using List of Dictionaries

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

total = 0

for product in products:

    revenue = product["price"] * product["quantity"]

    total = total + revenue

print("Total Revenue:", total)
```

### Output

```text
Total Revenue: 6600
```

---

# 📦 24. Check Low Stock

Business rule:

```text
Quantity < 5 → Low Stock
```

Code:

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

# 💎 25. Check Expensive Products

Business rule:

```text
Price >= 1000 → Expensive Product
```

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

# 🔗 26. Dictionary + Function

Day 11 lo functions + business logic nerchukunnam.

Now dictionary data ni function ki pass cheddam.

```python
def calculate_revenue(product):
    return product["price"] * product["quantity"]
```

Now call:

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}

revenue = calculate_revenue(product)

print("Revenue:", revenue)
```

### Output

```text
Revenue: 2400
```

---

# 🔄 27. Function + List of Dictionaries

Now complete combination:

```text
List
   ↓
Dictionary
   ↓
Function
   ↓
Loop
   ↓
Business Logic
```

Example:

```python
def calculate_revenue(product):
    return product["price"] * product["quantity"]


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

# 🧠 28. Why List of Dictionaries is Important?

Previous approach:

```python
products = ["Dog Food", "Cat Food", "Treats"]

prices = [1200, 900, 300]

quantities = [2, 3, 5]
```

Multiple lists ni same index tho connect cheyyali.

Example:

```python
products[i]
prices[i]
quantities[i]
```

This works, but data grow ayye koddi manage cheyyadam difficult avvachu.

List of dictionaries:

```python
products = [
    {
        "name": "Dog Food",
        "price": 1200,
        "quantity": 2
    }
]
```

Each product information one place lo untundi.

This makes structured data easier to understand.

---

# 🏢 29. Real-World Data Example

Real applications lo records ila untayi:

```python
customer = {
    "name": "Ravi",
    "city": "Hyderabad",
    "order_total": 1500
}
```

Employee:

```python
employee = {
    "name": "Durga",
    "role": "Data Engineer",
    "experience": 1
}
```

Product:

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}
```

Dictionary is very useful for representing one structured record.

---

# 🧪 30. Practice Task 1 — Create a Dictionary

Create a product dictionary containing:

```text
name
price
quantity
brand
```

Example:

```python
product = {
    "name": "Cat Food",
    "price": 900,
    "quantity": 3,
    "brand": "Whiskas"
}
```

Print all values.

---

# 🧪 31. Practice Task 2 — Update Dictionary

Create:

```python
product = {
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}
```

Update:

```text
price → 1500
quantity → 5
```

Then print the dictionary.

---

# 🧪 32. Practice Task 3 — List of Dictionaries

Create 4 products:

```text
Dog Food
Cat Food
Treats
Toy
```

Each product should contain:

```text
name
price
quantity
```

Store all products inside a list.

---

# 🧪 33. Practice Task 4 — Product Revenue

Using your list of dictionaries, calculate:

```text
Revenue = Price × Quantity
```

Print each product's revenue.

---

# 🧪 34. Practice Task 5 — Total Revenue

Using the same product data:

Calculate:

```text
Total Revenue
```

Use:

- List
- Dictionary
- `for` loop
- Function
- Accumulator

---

# 🏆 35. Day 12 Challenge

Create a complete **Pet Shop Product Analysis Program**.

Use:

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
```

Create a function:

```python
def calculate_revenue(product):
    return product["price"] * product["quantity"]
```

Then display:

```text
Product Name
Price
Quantity
Revenue
Stock Status
```

Also calculate:

```text
Total Revenue
Total Stock
Low Stock Products
Expensive Products
```

---

# 🔥 36. Day 11 vs Day 12

| Day | Concept |
|---|---|
| Day 11 | Functions + Business Logic |
| Day 12 | Dictionaries & Structured Data |
| Day 11 | Functions with lists and conditions |
| Day 12 | Dictionary-based product records |
| Day 11 | Reusable business logic |
| Day 12 | Structured data handling |
| Day 11 | Revenue/price/stock functions |
| Day 12 | List of dictionaries + functions |

Day 11 lo:

```text
Functions
    ↓
Business Logic
```

Day 12 lo:

```text
Structured Data
    ↓
Dictionaries
    ↓
Functions
    ↓
Business Logic
```

---

# 📊 37. Data Engineering Connection

Dictionaries are an important step toward working with real-world structured data.

Today I learned to represent a product as:

```python
{
    "name": "Dog Food",
    "price": 1200,
    "quantity": 2
}
```

Later, Data Engineering lo I will work with structured data from:

```text
CSV
JSON
APIs
Databases
SQL Tables
DataFrames
```

JSON data especially looks very similar to Python dictionaries.

So this concept is an important foundation for future data processing.

---

# 🧠 38. Day 12 Key Concepts

| Concept | Meaning |
|---|---|
| Dictionary | Key-value based data structure |
| Key | Data label |
| Value | Actual stored data |
| `dict[key]` | Access a value |
| `len()` | Number of key-value pairs |
| `keys()` | Get dictionary keys |
| `values()` | Get dictionary values |
| `items()` | Get key-value pairs |
| `in` | Check whether key exists |
| `del` | Delete a key |
| List of Dictionaries | Multiple structured records |
| Dictionary + Function | Process structured data using reusable logic |

---

# 📝 39. What I Learned Today

Today I learned that a **Dictionary** is useful when I want to store related information using meaningful labels.

For example:

```python
product["name"]
product["price"]
product["quantity"]
```

Instead of remembering which list index represents which information, the key itself tells me what the data means.

I also learned how to combine:

```text
Dictionary
+
List
+
Loop
+
Function
+
Condition
+
Business Logic
```

This is a major step from basic Python toward real-world data processing.

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
```

---

# 🚀 Next Step — Day 13

My next step is to continue improving my Python data-handling skills.

Upcoming concepts will gradually move toward:

```text
Python
   ↓
Data Structures
   ↓
Data Handling
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

Every day I am improving my Python programming and problem-solving skills step by step.

---

# 👨‍💻 Developed By

**Durga Vamsi**

📌 **Project:** Python Learning Journey  
📅 **Progress:** Day 01 → Day 12  
🎯 **Goal:** Python → Data Engineering

---

⭐ **Thanks for visiting my Python Learning Journey!**