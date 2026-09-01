# 🟢 Day 11 — Functions + Business Logic

Welcome to **Day 11** of my Python Learning Journey! 🚀

Today I am going one step further with **Functions**.

Day 10 lo functions ni create cheyyadam, parameters, arguments, `return` basics nerchukunnanu.

Today, those functions ni **real-world business problems** solve cheyyadaniki use chestanu.

My examples are based on a **Pet Shop / Life Care Pet Zone** business scenario.

---

## 🎯 Day 11 Learning Goals

Today I will learn:

- Functions ni business logic tho combine cheyyadam
- Parameters use cheyyadam
- `return` tho result return cheyyadam
- Functions + calculations
- Functions + conditions
- Functions + lists
- Functions + loops
- Multiple functions ni combine cheyyadam
- Reusable business logic create cheyyadam
- Clean and organized Python programs write cheyyadam

---

# 🧠 1. What is Business Logic?

**Business Logic** ante business lo oka decision or calculation ela perform cheyyali ane rules.

Example:

Pet Shop lo:

```text
Revenue = Price × Quantity
```

Stock `5` kanna takkuva unte:

```text
Low Stock
```

Price `1000` or more unte:

```text
Expensive Product
```

Instead of repeatedly writing these rules, we can create functions.

---

# 🧩 2. Simple Business Function

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Function ni call cheddam:

```python
price = 1200
quantity = 2

revenue = calculate_revenue(price, quantity)

print(revenue)
```

### Output

```text
2400
```

### Explanation

```text
price = 1200
quantity = 2
```

Function ki values pass chestunnam.

```python
calculate_revenue(1200, 2)
```

Inside function:

```python
1200 * 2
```

Result:

```text
2400
```

---

# 🔄 3. Why Use Functions for Business Logic?

Suppose 100 products unnayi.

Every product ki:

```python
price * quantity
```

ani repeatedly write cheyyadam unnecessary.

Instead:

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Once function create chesi, multiple times use cheyyachu.

```python
calculate_revenue(1200, 2)
calculate_revenue(900, 3)
calculate_revenue(300, 5)
```

This is called **reusability**.

---

# 🏪 4. Life Care Pet Zone Example

```python
def calculate_revenue(price, quantity):
    return price * quantity


price = 1200
quantity = 2

revenue = calculate_revenue(price, quantity)

print("Product Revenue:", revenue)
```

### Output

```text
Product Revenue: 2400
```

---

# 🧮 5. Function for Total Revenue

Let's calculate revenue for multiple products.

```python
def calculate_revenue(price, quantity):
    return price * quantity


prices = [1200, 900, 300, 500]
quantities = [2, 3, 5, 4]

total = 0

for i in range(len(prices)):
    revenue = calculate_revenue(prices[i], quantities[i])
    total = total + revenue

print("Total Revenue:", total)
```

### Output

```text
Total Revenue: 7600
```

### Important Concept

Here we are combining:

```text
Function
   ↓
Lists
   ↓
Indexing
   ↓
For Loop
   ↓
Business Calculation
```

This is a very important step in my Python learning journey.

---

# 📦 6. Function for Stock Checking

Business rule:

```text
Quantity < 5 → Low Stock
```

We can create a function.

```python
def check_stock(quantity):
    if quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"
```

Now:

```python
print(check_stock(3))
print(check_stock(10))
```

### Output

```text
Low Stock
Stock Available
```

---

# 💰 7. Function for Expensive Products

Business rule:

```text
Price >= 1000 → Expensive Product
```

Function:

```python
def check_price(price):
    if price >= 1000:
        return "Expensive Product"
    else:
        return "Normal Price"
```

Example:

```python
print(check_price(1200))
print(check_price(500))
```

### Output

```text
Expensive Product
Normal Price
```

---

# 🔗 8. Function + List + Loop

Now let's combine everything.

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]


def calculate_revenue(price, quantity):
    return price * quantity


for i in range(len(products)):

    revenue = calculate_revenue(prices[i], quantities[i])

    print(products[i], "Revenue:", revenue)
```

### Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
Toy Revenue: 2000
```

---

# 📊 9. Multiple Business Functions

We can create different functions for different business rules.

```python
def calculate_revenue(price, quantity):
    return price * quantity


def check_stock(quantity):
    if quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"


def check_price(price):
    if price >= 1000:
        return "Expensive Product"
    else:
        return "Normal Price"
```

Now use them together:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]


def calculate_revenue(price, quantity):
    return price * quantity


def check_stock(quantity):
    if quantity < 5:
        return "Low Stock"
    else:
        return "Stock Available"


def check_price(price):
    if price >= 1000:
        return "Expensive Product"
    else:
        return "Normal Price"


for i in range(len(products)):

    revenue = calculate_revenue(prices[i], quantities[i])
    stock_status = check_stock(quantities[i])
    price_status = check_price(prices[i])

    print("Product:", products[i])
    print("Revenue:", revenue)
    print("Stock:", stock_status)
    print("Price:", price_status)
    print("--------------------")
```

---

# 🧠 10. Understanding the Flow

Program execution ila untundi:

```text
Product Data
     ↓
For Loop
     ↓
Get Product Index
     ↓
Calculate Revenue
     ↓
Check Stock
     ↓
Check Price
     ↓
Display Result
```

This type of thinking is very useful for **Data Engineering**.

---

# 🔢 11. Function with Multiple Parameters

A function can have multiple parameters.

```python
def calculate_order_total(price, quantity, delivery_charge):
    return (price * quantity) + delivery_charge
```

Example:

```python
total = calculate_order_total(500, 2, 100)

print("Order Total:", total)
```

### Output

```text
Order Total: 1100
```

Calculation:

```text
500 × 2 = 1000

1000 + 100 = 1100
```

---

# 🔁 12. Calling the Same Function Multiple Times

Functions can be reused many times.

```python
def calculate_revenue(price, quantity):
    return price * quantity


revenue1 = calculate_revenue(1200, 2)
revenue2 = calculate_revenue(900, 3)
revenue3 = calculate_revenue(300, 5)

print(revenue1)
print(revenue2)
print(revenue3)
```

### Output

```text
2400
2700
1500
```

One function → Multiple uses.

---

# 🧮 13. Function + Accumulator

Day 09 lo total calculation kosam accumulator concept nerchukunnam.

Now function tho combine cheddam.

```python
def calculate_revenue(price, quantity):
    return price * quantity


prices = [1200, 900, 300, 500]
quantities = [2, 3, 5, 4]

total = 0

for i in range(len(prices)):

    amount = calculate_revenue(prices[i], quantities[i])

    total = total + amount

print("Total Revenue:", total)
```

### Output

```text
Total Revenue: 8600
```

> Note: Always calculate the expected output carefully based on the values in the lists.

---

# ⚠️ 14. Common Mistake — Forgetting return

Incorrect:

```python
def calculate_revenue(price, quantity):
    price * quantity
```

Correct:

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Without `return`, function result ni outside store/use cheyyadam possible kaadu.

---

# ⚠️ 15. Common Mistake — Wrong Arguments

Function:

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Correct:

```python
calculate_revenue(1200, 2)
```

Incorrect:

```python
calculate_revenue(1200)
```

Because function ki two values required:

```text
price
quantity
```

---

# ⚠️ 16. Common Mistake — Confusing print and return

### `print()`

Screen meeda result display chestundi.

```python
def calculate_revenue(price, quantity):
    print(price * quantity)
```

### `return`

Result ni function nundi outside ki send chestundi.

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Example:

```python
revenue = calculate_revenue(1200, 2)

print(revenue)
```

Data processing programs lo `return` chala useful.

---

# 🧪 17. Practice Task 1 — Revenue Function

Create:

```python
def calculate_revenue(price, quantity):
```

Use:

```text
Price = 1500
Quantity = 3
```

Expected:

```text
4500
```

---

# 🧪 18. Practice Task 2 — Stock Function

Create:

```python
def check_stock(quantity):
```

Rule:

```text
quantity < 5 → Low Stock
quantity >= 5 → Stock Available
```

Test with:

```python
check_stock(2)
check_stock(10)
```

---

# 🧪 19. Practice Task 3 — Product Revenue

Use:

```python
products = ["Dog Food", "Cat Food", "Treats"]

prices = [1200, 900, 300]

quantities = [2, 3, 5]
```

Create a function:

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Then use a loop to calculate each product revenue.

---

# 🧪 20. Practice Task 4 — Total Revenue

Using the same lists:

```python
products = ["Dog Food", "Cat Food", "Treats"]

prices = [1200, 900, 300]

quantities = [2, 3, 5]
```

Calculate:

```text
Total Revenue
```

Use:

- Function
- `for` loop
- `range()`
- Lists
- Accumulator

---

# 🏆 21. Day 11 Challenge

Create a complete **Pet Shop Sales Analysis Program**.

Use:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

Create these functions:

```python
def calculate_revenue(price, quantity):
    pass
```

```python
def check_stock(quantity):
    pass
```

```python
def check_price(price):
    pass
```

Then use a `for` loop to display:

```text
Product Name
Price
Quantity
Revenue
Stock Status
Price Status
```

Finally calculate:

```text
Total Revenue
```

---

# 🔥 22. Day 10 vs Day 11

| Day | Concept |
|---|---|
| Day 10 | Functions Basics |
| Day 11 | Functions + Business Logic |
| Day 10 | Create and call functions |
| Day 11 | Use functions in real problems |
| Day 10 | Parameters and return |
| Day 11 | Functions + Lists + Loops + Conditions |

Day 10 lo **function ela work chestundo** nerchukunna.

Day 11 lo **function ni real-world problem solving ki ela use cheyyalo** practice chestunna.

---

# 🏢 23. Real-World Business Connection

Real company applications lo different operations ki reusable functions create chestaru.

For example:

```text
calculate_revenue()
       ↓
check_stock()
       ↓
calculate_order_total()
       ↓
check_price()
       ↓
generate_report()
```

Instead of writing everything in one large program, logic ni small reusable functions ga divide cheyyachu.

This makes the program:

- Easy to understand
- Easy to test
- Easy to reuse
- Easy to maintain

---

# 📊 24. Data Engineering Connection

Functions are very important in **Data Engineering**.

Later I will work with:

```text
Python
   ↓
Data Cleaning
   ↓
Data Transformation
   ↓
Data Processing
   ↓
Pandas
   ↓
SQL
   ↓
ETL Pipelines
   ↓
Data Engineering
```

Example:

```python
def clean_data(data):
    pass
```

```python
def transform_data(data):
    pass
```

```python
def calculate_metrics(data):
    pass
```

Real ETL pipelines lo different tasks ni functions ga separate cheyyadam common.

---

# 📝 25. Day 11 Key Concepts

| Concept | Meaning |
|---|---|
| `def` | Function create cheyyadaniki |
| Function | Reusable block of code |
| Parameter | Function definition lo input |
| Argument | Function call lo actual value |
| `return` | Result ni outside ki send cheyyadam |
| Business Logic | Business rules/calculations |
| Reusability | Same function ni multiple times use cheyyadam |
| Loop + Function | Multiple records process cheyyadam |
| Condition + Function | Business decisions handle cheyyadam |

---

# 🎯 Day 11 Summary

Today I learned how to combine **Functions with Business Logic**.

I practiced:

- Creating reusable functions
- Passing parameters
- Returning values
- Revenue calculations
- Stock checking
- Price checking
- Functions + Lists
- Functions + Loops
- Functions + Conditions
- Multiple functions
- Accumulator with functions
- Real-world Pet Shop business logic

Most importantly:

> **Functions are not just about writing code once. They help us build reusable business logic.**

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
```

---

# 🚀 Next Step — Day 12

Next I will continue with:

**Dictionaries + Data Handling + Functions**

I will start working with structured data that looks more like real-world business records.

My goal is to gradually move from:

```text
Basic Python
     ↓
Python Data Handling
     ↓
Data Processing
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

# 👨‍💻 Developed By

**Durga Vamsi**

🐍 Python Learning Journey  
📊 Future Data Engineer  
🚀 Learning Python step by step toward Data Engineering