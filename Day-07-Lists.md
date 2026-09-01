# 📅 Day 07 — Lists

Welcome to **Day 07** of my Python Learning Journey! 🚀🐍

In Day 06, I learned how to use **`for` loops** to repeat operations and process data one by one.

Today I am learning one of the most important Python data structures:

> **Lists**

A list allows me to store **multiple values inside a single variable**.

For example, instead of creating separate variables:

```python
product1 = "Dog Food"
product2 = "Cat Food"
product3 = "Treats"
product4 = "Toy"
```

I can store all products together:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

This makes working with multiple values much easier.

---

# 🎯 Day 07 Learning Goal

By the end of Day 07, I should understand:

- What a list is
- How to create a list
- What list elements are
- How indexing works
- How to access list values
- How `len()` works
- How to loop through a list
- How lists can store business data
- How lists work together with `for` loops

---

# 📚 Topics Learned

### 1. Lists

### 2. Creating Lists

### 3. List Elements

### 4. Indexing

### 5. Accessing Values

### 6. `len()`

### 7. Looping Through Lists

### 8. Practical Business Examples

---

# 🧠 What Is a List?

A **list** is a Python data structure used to store multiple values in one variable.

Simple ga cheppali ante:

> Oka variable lo multiple values ni store cheyyadaniki **list** use chestham.

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Here:

```text
products
   ↓
["Dog Food", "Cat Food", "Treats", "Toy"]
```

The list contains four values.

---

# 🔹 Creating a List

A list is created using square brackets:

```python
[]
```

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

The values are separated using commas.

---

# 💻 Example 1 — Simple List

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

print(products)
```

Output:

```text
['Dog Food', 'Cat Food', 'Treats', 'Toy']
```

---

# 🧩 List Elements

The individual values inside a list are called **elements**.

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Here:

```text
Dog Food → Element
Cat Food → Element
Treats   → Element
Toy      → Element
```

So:

> **List = Collection of elements**

---

# 🔢 List Indexing

Python uses **index numbers** to identify the position of each element.

Important point:

> Python list indexing starts from **0**, not 1.

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

The indexes are:

```text
Index 0 → Dog Food
Index 1 → Cat Food
Index 2 → Treats
Index 3 → Toy
```

---

# 📊 List Index Table

| Index | Value |
|---:|---|
| `0` | Dog Food |
| `1` | Cat Food |
| `2` | Treats |
| `3` | Toy |

---

# 💻 Example 2 — Accessing List Values

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

print(products[0])
print(products[1])
print(products[2])
print(products[3])
```

Output:

```text
Dog Food
Cat Food
Treats
Toy
```

---

# 🎯 Accessing a Specific Value

Suppose I want only `"Treats"`.

The list is:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

`Treats` is at index `2`.

So:

```python
print(products[2])
```

Output:

```text
Treats
```

---

# ⚠️ Important — Index Starts From 0

This is one of the most important concepts.

For:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Do not think:

```text
Dog Food → 1
Cat Food → 2
Treats → 3
Toy → 4
```

Python thinks:

```text
Dog Food → 0
Cat Food → 1
Treats → 2
Toy → 3
```

---

# ❌ Common Index Error

Suppose:

```python
products = ["Dog Food", "Cat Food"]
```

There are only two elements.

Valid indexes are:

```text
0
1
```

This is incorrect:

```python
print(products[2])
```

Because index `2` does not exist.

Python will raise an:

```text
IndexError
```

---

# 🔢 `len()` Function

`len()` is used to find the **number of elements** in a list.

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

print(len(products))
```

Output:

```text
4
```

There are four products in the list.

---

# 🧠 Understanding `len()`

For:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

We have:

```text
Dog Food
Cat Food
Treats
Toy
```

Total number of elements:

```text
4
```

Therefore:

```python
len(products)
```

returns:

```text
4
```

---

# 💻 Example 3 — List Length

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

number_of_products = len(products)

print("Number of Products:", number_of_products)
```

Output:

```text
Number of Products: 4
```

---

# 🔄 Lists + `for` Loop

Lists become much more useful when combined with loops.

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for product in products:
    print(product)
```

Output:

```text
Dog Food
Cat Food
Treats
Toy
```

Python automatically takes each element from the list one by one.

---

# 🔍 Step-by-Step Loop Execution

Given:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

The loop:

```python
for product in products:
    print(product)
```

works like:

```text
Iteration 1 → Dog Food
Iteration 2 → Cat Food
Iteration 3 → Treats
Iteration 4 → Toy
```

So we don't need:

```python
print(products[0])
print(products[1])
print(products[2])
print(products[3])
```

Instead, one loop can process everything.

---

# 💻 Example 4 — Print Every Product

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for product in products:
    print("Product:", product)
```

Output:

```text
Product: Dog Food
Product: Cat Food
Product: Treats
Product: Toy
```

---

# 💰 List of Prices

Lists can store numbers too.

Example:

```python
prices = [1200, 900, 300, 500]

print(prices)
```

Output:

```text
[1200, 900, 300, 500]
```

We can access individual prices:

```python
print(prices[0])
print(prices[2])
```

Output:

```text
1200
300
```

---

# 📦 List of Quantities

```python
quantities = [2, 3, 5, 4]

print(quantities)
```

Output:

```text
[2, 3, 5, 4]
```

---

# 🐾 Pet Shop Data Using Lists

For a pet shop, we can store:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

Now we have three separate lists:

```text
Products
Prices
Quantities
```

These represent business data.

---

# 💻 Example 5 — Display Product Information

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

print("Products:", products)
print("Prices:", prices)
print("Quantities:", quantities)
```

Output:

```text
Products: ['Dog Food', 'Cat Food', 'Treats', 'Toy']
Prices: [1200, 900, 300, 500]
Quantities: [2, 3, 5, 4]
```

---

# 🔢 Accessing Product Data Using Index

We can access a particular product:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

print(products[0])
```

Output:

```text
Dog Food
```

We can access the corresponding price:

```python
prices = [1200, 900, 300, 500]

print(prices[0])
```

Output:

```text
1200
```

And quantity:

```python
quantities = [2, 3, 5, 4]

print(quantities[0])
```

Output:

```text
2
```

So index `0` refers to the first item in each list.

---

# 🧠 Understanding List Position

Consider:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

At index `0`:

```text
Product  → Dog Food
Price    → 1200
Quantity → 2
```

At index `1`:

```text
Product  → Cat Food
Price    → 900
Quantity → 3
```

This same-index concept will become very useful in the next learning stage.

---

# 🔄 Loop Through a List

The easiest way to process every list item is:

```python
for item in list:
    print(item)
```

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for product in products:
    print(product)
```

Output:

```text
Dog Food
Cat Food
Treats
Toy
```

---

# 🔢 Loop Using Index

We can also use:

```python
range(len(products))
```

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for i in range(len(products)):
    print(products[i])
```

Output:

```text
Dog Food
Cat Food
Treats
Toy
```

---

# 🔍 Understanding `range(len(products))`

Suppose:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Then:

```python
len(products)
```

gives:

```text
4
```

Therefore:

```python
range(len(products))
```

becomes:

```python
range(4)
```

which produces:

```text
0
1
2
3
```

Then Python accesses:

```python
products[0]
products[1]
products[2]
products[3]
```

---

# 💼 Business Example — Display Products With Index

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for i in range(len(products)):
    print("Index:", i, "Product:", products[i])
```

Output:

```text
Index: 0 Product: Dog Food
Index: 1 Product: Cat Food
Index: 2 Product: Treats
Index: 3 Product: Toy
```

---

# 📊 Product Counting

We can use `len()` to count products.

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

count = len(products)

print("Total Products:", count)
```

Output:

```text
Total Products: 4
```

This can be useful in inventory and product management systems.

---

# 🏪 Life Care Pet Zone Example

```python
products = [
    "Dog Food",
    "Cat Food",
    "Treats",
    "Toy"
]

print("Life Care Pet Zone Products")

for product in products:
    print("-", product)

print("Total Products:", len(products))
```

Output:

```text
Life Care Pet Zone Products
- Dog Food
- Cat Food
- Treats
- Toy
Total Products: 4
```

---

# 🧠 Why Lists Are Important

Without lists, we might need:

```python
product1 = "Dog Food"
product2 = "Cat Food"
product3 = "Treats"
product4 = "Toy"
```

With a list:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

This is much easier to manage.

Lists are especially useful when working with:

```text
Products
Customers
Prices
Orders
Sales
Quantities
Employee names
File names
Data records
```

---

# ⚠️ Common Beginner Mistakes

## Mistake 1 — Forgetting Square Brackets

Wrong:

```python
products = "Dog Food", "Cat Food", "Treats"
```

For clear list creation, use:

```python
products = ["Dog Food", "Cat Food", "Treats"]
```

---

## Mistake 2 — Forgetting That Index Starts From 0

For:

```python
products = ["Dog Food", "Cat Food", "Treats"]
```

Correct:

```python
products[0]
```

returns:

```text
Dog Food
```

Not:

```text
Cat Food
```

---

## Mistake 3 — Accessing an Invalid Index

Wrong:

```python
products = ["Dog Food", "Cat Food"]

print(products[2])
```

Only these indexes exist:

```text
0
1
```

---

## Mistake 4 — Forgetting Indentation in a Loop

Wrong:

```python
for product in products:
print(product)
```

Correct:

```python
for product in products:
    print(product)
```

---

# 📝 Practice Tasks

## Task 1 — Create a Product List

Create:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Print the complete list.

---

## Task 2 — Access List Elements

Using the same list, print:

```text
Dog Food
Treats
```

Use their indexes.

---

## Task 3 — Count Products

Use:

```python
len(products)
```

to find the number of products.

Expected output:

```text
4
```

---

## Task 4 — Loop Through Products

Use a `for` loop to print every product.

Expected output:

```text
Dog Food
Cat Food
Treats
Toy
```

---

## Task 5 — Create a Price List

Create:

```python
prices = [1200, 900, 300, 500]
```

Print every price using a loop.

---

## Task 6 — Create a Quantity List

Create:

```python
quantities = [2, 3, 5, 4]
```

Use a loop to print every quantity.

---

## Task 7 — Product Count

Create a list with five products and use `len()` to find the total number of products.

---

# 🎯 Day 07 Challenge

Create a simple **Pet Shop Product List Program**.

Use:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Your program should:

1. Print the complete list
2. Print the first product
3. Print the third product
4. Print the number of products
5. Loop through all products

Expected output:

```text
Products: ['Dog Food', 'Cat Food', 'Treats', 'Toy']

First Product: Dog Food

Third Product: Treats

Total Products: 4

All Products:
Dog Food
Cat Food
Treats
Toy
```

---

# 💡 Real-World Applications

Lists are commonly used to organize collections of data.

Examples:

### 🛒 E-Commerce

```text
Products
Prices
Orders
Customers
```

### 📦 Inventory

```text
Stock quantities
Product names
Product prices
```

### 📊 Sales

```text
Sales values
Order quantities
Revenue values
```

### 🐾 Pet Shop

```text
Dog Food
Cat Food
Treats
Toys
```

Lists provide the foundation for processing multiple values programmatically.

---

# 🔗 Day 06 + Day 07 Connection

In Day 06, I learned:

```text
for loop
range()
Iteration
```

In Day 07, I learned:

```text
Lists
Indexing
len()
Looping through lists
```

Now I can combine them:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for product in products:
    print(product)
```

This combination is very important because it allows me to process multiple pieces of data automatically.

---

# 🧠 What I Understood Today

Today I understood that a **list** can store multiple values inside a single variable.

I learned:

```text
List
   ↓
Multiple Elements
   ↓
Indexing
   ↓
Access Values
   ↓
len()
   ↓
Loop Through Data
```

I also understood that Python indexing starts from `0`.

---

# 📚 My Day 07 Learning

Today I practiced:

- Creating lists
- List elements
- Square brackets `[]`
- Indexing
- Accessing list values
- `len()`
- `for` loops with lists
- `range(len())`
- Product lists
- Price lists
- Quantity lists
- Basic business data processing

---

# 🏆 Day 07 Achievement

I can now store multiple values in a list, access individual elements using indexes, count elements using `len()`, and process list data using loops.

### My Progress

```text
Day 01 → Python Basics              ✅
Day 02 → Variables & Data Types     ✅
Day 03 → Input & Type Conversion    ✅
Day 04 → Operators & Calculations   ✅
Day 05 → Conditional Statements     ✅
Day 06 → For Loops & Iteration      ✅
Day 07 → Lists                      ✅
```

---

# 🚀 Next Step — Day 08

In **Day 08**, I will learn how to work with **multiple related lists**.

I will practice:

```text
Multiple Lists
Indexing
range(len())
Products
Prices
Quantities
Connecting related data
```

This will help me process product-level business data such as:

```text
Product → Price → Quantity
```

and calculate values such as revenue.

---

# 🐍 Python Learning Journey

My goal is to build strong Python fundamentals and gradually move toward:

```text
Python Basics
      ↓
Variables & Data Types
      ↓
Input & Type Conversion
      ↓
Operators
      ↓
Conditions
      ↓
Loops
      ↓
Lists
      ↓
Multiple Lists + Indexing
      ↓
Sales & Inventory Analysis
      ↓
Functions
      ↓
Business Logic
      ↓
Dictionaries
      ↓
Data Processing
      ↓
SQL
      ↓
ETL
      ↓
Data Engineering
```

I am learning step-by-step and improving my programming and problem-solving skills through practical examples.

---

# 👨‍💻 Developed By

## **Durga Vamsi**

> Learning Python step-by-step and building my journey toward **Data Engineering** 🚀🐍📊

**Day 07 completed successfully! 🎯**