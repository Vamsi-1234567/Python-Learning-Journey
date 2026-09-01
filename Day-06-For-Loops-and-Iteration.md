# 📅 Day 06 — For Loops and Iteration

Welcome to **Day 06** of my Python Learning Journey! 🚀🐍

In Day 05, I learned how Python can make decisions using:

```text
if
elif
else
```

Today I am learning how Python can **repeat a task multiple times automatically**.

The main concept for Day 06 is:

> **`for` loop and `range()`**

Loops are very important because in real-world programming we often need to process many items instead of writing the same code again and again.

---

# 🎯 Day 06 Learning Goal

By the end of Day 06, I should understand:

- What a loop is
- What iteration means
- How a `for` loop works
- How `range()` works
- How to loop through a list
- How to process multiple values
- How loops reduce repetitive code
- How loops can be used in business examples

---

# 📚 Topics Learned

### 1. Loops

### 2. Iteration

### 3. `for` Loop

### 4. `range()`

### 5. Looping Through Lists

### 6. Loop Variables

### 7. Repeating Tasks

### 8. Practical Business Examples

---

# 🧠 What Is a Loop?

A **loop** is used to repeat a block of code multiple times.

Simple ga cheppali ante:

> Same task ni repeatedly manually rayakunda, Python ki loop use chesi automatic ga repeat cheyyamani cheppachu.

For example, suppose we want to print:

```text
Dog Food
Cat Food
Treats
Toy
```

Without a loop:

```python
print("Dog Food")
print("Cat Food")
print("Treats")
print("Toy")
```

This works, but if we have 100 products, writing 100 `print()` statements is not practical.

Instead, we can use a loop.

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

Python automatically goes through each item.

---

# 🔄 What Is Iteration?

**Iteration** means processing items one by one.

For example:

```text
Dog Food
Cat Food
Treats
Toy
```

Python processes them like this:

```text
Iteration 1 → Dog Food
Iteration 2 → Cat Food
Iteration 3 → Treats
Iteration 4 → Toy
```

So:

> **Iteration = One-by-one processing of items.**

---

# 🔹 `for` Loop

The `for` loop is used to repeat code for each item in a sequence.

### Basic Syntax

```python
for variable in sequence:
    statement
```

Example:

```python
products = ["Dog Food", "Cat Food", "Treats"]

for product in products:
    print(product)
```

---

# 🔍 Understanding the Code

```python
products = ["Dog Food", "Cat Food", "Treats"]
```

Here we have a list containing three products.

Then:

```python
for product in products:
```

Python takes each product one by one.

First:

```text
product = "Dog Food"
```

Then:

```text
product = "Cat Food"
```

Then:

```text
product = "Treats"
```

For every item, this code runs:

```python
print(product)
```

---

# 💻 Example 1 — Simple `for` Loop

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

# 🧠 How the Loop Executes

The loop works like this:

```text
products
   ↓
Dog Food  → print
   ↓
Cat Food  → print
   ↓
Treats    → print
   ↓
Toy       → print
```

The loop stops after all items have been processed.

---

# 🔢 `range()`

`range()` is used when we want to repeat something a specific number of times.

Example:

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

Notice that Python starts from:

```text
0
```

and stops before:

```text
5
```

So:

```python
range(5)
```

produces:

```text
0, 1, 2, 3, 4
```

---

# 📌 Important Rule of `range()`

When we write:

```python
range(5)
```

Python generates:

```text
0 → 1 → 2 → 3 → 4
```

The ending number `5` is **not included**.

This is called the **exclusive stop value**.

---

# 💻 Example 2 — Print Numbers

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

---

# 💻 Example 3 — Start and Stop

We can give two values to `range()`.

```python
for i in range(1, 6):
    print(i)
```

Output:

```text
1
2
3
4
5
```

Here:

```python
range(1, 6)
```

means:

```text
Start = 1
Stop = 6
```

6 is not included.

---

# 📊 `range()` Examples

| Code | Output |
|---|---|
| `range(5)` | `0 1 2 3 4` |
| `range(1, 5)` | `1 2 3 4` |
| `range(1, 6)` | `1 2 3 4 5` |
| `range(2, 7)` | `2 3 4 5 6` |

---

# 🔢 Using `range()` With a Step

`range()` can also use a third value called **step**.

Syntax:

```python
range(start, stop, step)
```

Example:

```python
for i in range(0, 10, 2):
    print(i)
```

Output:

```text
0
2
4
6
8
```

Here:

```text
Start = 0
Stop = 10
Step = 2
```

Python increases the number by 2 each time.

---

# 💻 Example 4 — Counting by 2

```python
for number in range(2, 11, 2):
    print(number)
```

Output:

```text
2
4
6
8
10
```

---

# 🐾 Pet Shop Example

Suppose we want to print all products in our pet shop.

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

This is much better than manually writing four `print()` statements.

---

# 💰 Loop Through Prices

```python
prices = [1200, 900, 300, 500]

for price in prices:
    print("Price:", price)
```

Output:

```text
Price: 1200
Price: 900
Price: 300
Price: 500
```

---

# 📦 Loop Through Quantities

```python
quantities = [2, 3, 5, 4]

for quantity in quantities:
    print("Quantity:", quantity)
```

Output:

```text
Quantity: 2
Quantity: 3
Quantity: 5
Quantity: 4
```

---

# 🔢 Using a Loop With `range()`

Suppose we want to process four products.

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for i in range(4):
    print(products[i])
```

Output:

```text
Dog Food
Cat Food
Treats
Toy
```

Here `i` represents the index.

The values of `i` are:

```text
0
1
2
3
```

---

# 📌 Understanding Index + Loop

Consider:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Indexes are:

```text
Index 0 → Dog Food
Index 1 → Cat Food
Index 2 → Treats
Index 3 → Toy
```

Now:

```python
for i in range(4):
    print(products[i])
```

Python executes:

```python
products[0]
products[1]
products[2]
products[3]
```

So it prints every product.

---

# 🧠 Better Way Using `len()`

Instead of manually writing:

```python
range(4)
```

we can use:

```python
len(products)
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

This is useful because if the list size changes, the loop automatically adjusts.

---

# 📊 Why `range(len(list))` Is Useful

Suppose today we have:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

There are:

```text
4 products
```

Tomorrow we add:

```python
"Leash"
```

Now there are:

```text
5 products
```

With:

```python
for i in range(len(products)):
```

Python automatically processes all 5 items.

---

# 💻 Example — Product Index

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for i in range(len(products)):
    print("Index:", i)
    print("Product:", products[i])
```

Output:

```text
Index: 0
Product: Dog Food
Index: 1
Product: Cat Food
Index: 2
Product: Treats
Index: 3
Product: Toy
```

---

# 💼 Business Example — Product and Price

Suppose we have:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
prices = [1200, 900, 300, 500]
```

We can process both lists using the index.

```python
for i in range(len(products)):
    print(products[i], prices[i])
```

Output:

```text
Dog Food 1200
Cat Food 900
Treats 300
Toy 500
```

This is an important programming pattern.

---

# 🧮 Business Example — Calculate Revenue

Suppose:

```python
prices = [1200, 900, 300, 500]
quantities = [2, 3, 5, 4]
```

We can calculate each product's revenue.

```python
prices = [1200, 900, 300, 500]
quantities = [2, 3, 5, 4]

for i in range(len(prices)):
    revenue = prices[i] * quantities[i]
    print("Revenue:", revenue)
```

Output:

```text
Revenue: 2400
Revenue: 2700
Revenue: 1500
Revenue: 2000
```

---

# 🔍 Step-by-Step Revenue Calculation

For the first product:

```text
1200 × 2 = 2400
```

Second:

```text
900 × 3 = 2700
```

Third:

```text
300 × 5 = 1500
```

Fourth:

```text
500 × 4 = 2000
```

The loop automatically performs the calculation for every product.

---

# 💰 Total Revenue Using a Loop

We can also calculate the complete revenue.

```python
prices = [1200, 900, 300, 500]
quantities = [2, 3, 5, 4]

total_revenue = 0

for i in range(len(prices)):
    revenue = prices[i] * quantities[i]
    total_revenue = total_revenue + revenue

print("Total Revenue:", total_revenue)
```

Output:

```text
Total Revenue: 8600
```

Calculation:

```text
2400 + 2700 + 1500 + 2000 = 8600
```

---

# 🧠 Important Concept — Accumulator

In this example:

```python
total_revenue = 0
```

We start with zero.

Then inside the loop:

```python
total_revenue = total_revenue + revenue
```

The value keeps increasing.

Example:

```text
Start → 0

After Product 1 → 2400

After Product 2 → 5100

After Product 3 → 6600

After Product 4 → 8600
```

This pattern is called an **accumulator**.

It is very useful for totals, sums, counts, and other calculations.

---

# 🏪 Life Care Pet Zone Example

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
prices = [1200, 900, 300, 500]
quantities = [2, 3, 5, 4]

total_revenue = 0

for i in range(len(products)):
    revenue = prices[i] * quantities[i]

    print("Product:", products[i])
    print("Price:", prices[i])
    print("Quantity:", quantities[i])
    print("Revenue:", revenue)
    print()

    total_revenue = total_revenue + revenue

print("Total Revenue:", total_revenue)
```

Output:

```text
Product: Dog Food
Price: 1200
Quantity: 2
Revenue: 2400

Product: Cat Food
Price: 900
Quantity: 3
Revenue: 2700

Product: Treats
Price: 300
Quantity: 5
Revenue: 1500

Product: Toy
Price: 500
Quantity: 4
Revenue: 2000

Total Revenue: 8600
```

---

# 🔄 Loop Execution Flow

```text
Start
  ↓
Get first item
  ↓
Execute code
  ↓
Get next item
  ↓
Execute code
  ↓
Continue
  ↓
All items completed?
  ↓
Yes
  ↓
End
```

---

# ⚠️ Common Beginner Mistakes

## Mistake 1 — Forgetting Indentation

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

## Mistake 2 — Wrong Range

Remember:

```python
range(5)
```

means:

```text
0, 1, 2, 3, 4
```

Not:

```text
0, 1, 2, 3, 4, 5
```

---

## Mistake 3 — Using Wrong Index

Wrong:

```python
products = ["Dog Food", "Cat Food"]

print(products[2])
```

This causes an index error because valid indexes are:

```text
0
1
```

---

## Mistake 4 — Hardcoding the List Length

Instead of:

```python
for i in range(4):
```

Prefer:

```python
for i in range(len(products)):
```

when the list size may change.

---

# 📝 Practice Tasks

## Task 1 — Print Products

Create:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Use a `for` loop to print every product.

Expected output:

```text
Dog Food
Cat Food
Treats
Toy
```

---

## Task 2 — Print Numbers

Use:

```python
range()
```

to print numbers from 1 to 10.

Expected output:

```text
1
2
3
4
5
6
7
8
9
10
```

---

## Task 3 — Print Prices

Create:

```python
prices = [1200, 900, 300, 500]
```

Use a loop to print each price.

---

## Task 4 — Product and Price

Create:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
prices = [1200, 900, 300, 500]
```

Use:

```python
range(len(products))
```

to print:

```text
Dog Food 1200
Cat Food 900
Treats 300
Toy 500
```

---

## Task 5 — Calculate Revenue

Create:

```python
prices = [1200, 900, 300, 500]
quantities = [2, 3, 5, 4]
```

Use a `for` loop to calculate the revenue of every product.

---

## Task 6 — Calculate Total Revenue

Using the same lists, calculate:

```text
Total Revenue
```

Expected result:

```text
8600
```

---

# 🎯 Day 06 Challenge

Create a small **Pet Shop Sales Analysis** program.

Use:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

Use a loop to calculate:

```text
Product
Price
Quantity
Revenue
```

for every product.

Then calculate:

```text
Total Revenue
```

Expected total:

```text
8600
```

---

# 💡 Why Loops Are Important for Data Engineering

Loops are an important programming foundation.

In Data Engineering, we often work with:

```text
Thousands of records
Millions of records
Files
Rows
Products
Customers
Transactions
Sales
```

The basic idea of processing data repeatedly is related to iteration.

For example:

```python
sales = [100, 200, 300, 400]

total = 0

for sale in sales:
    total = total + sale

print(total)
```

Output:

```text
1000
```

This simple concept helps build the foundation for more advanced data processing.

---

# 📌 Quick Reference

### Basic `for` Loop

```python
for item in items:
    print(item)
```

### `range()`

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

### Start and Stop

```python
for i in range(1, 6):
    print(i)
```

### List With Index

```python
for i in range(len(products)):
    print(products[i])
```

### Loop With Calculation

```python
for i in range(len(prices)):
    revenue = prices[i] * quantities[i]
    print(revenue)
```

---

# 🧠 What I Understood Today

Today I understood that loops help Python **repeat tasks automatically**.

I learned:

```text
for       → repeats code for each item
range()   → generates a sequence of numbers
iteration → processing items one by one
len()     → gives the number of items
index     → identifies an item's position
```

I also learned how to combine:

```text
Lists
+
Indexes
+
Loops
+
Calculations
```

to process multiple products and calculate sales revenue.

---

# 📚 My Day 06 Learning

Today I practiced:

- `for` loop
- `range()`
- `len()`
- Iteration
- List traversal
- Index-based looping
- Multiple lists
- Revenue calculation
- Total calculation
- Accumulator pattern
- Business data processing

---

# 🏆 Day 06 Achievement

I can now use Python loops to process multiple items automatically instead of repeating the same code manually.

### My Progress

```text
Day 01 → Python Basics              ✅
Day 02 → Variables & Data Types     ✅
Day 03 → Input & Type Conversion    ✅
Day 04 → Operators & Calculations   ✅
Day 05 → Conditional Statements     ✅
Day 06 → For Loops & Iteration      ✅
```

---

# 🚀 Next Step — Day 07

In **Day 07**, I will continue working with **Lists** and learn how to work with list data more effectively.

I will practice:

```text
Lists
Indexing
len()
Loops
List Data
```

This will help me become more comfortable working with collections of data before moving toward more advanced Python and Data Engineering concepts.

---

# 🐍 Python Learning Journey

My goal is to build strong Python fundamentals and gradually move toward:

```text
Python
   ↓
Data Handling
   ↓
Data Analysis
   ↓
SQL
   ↓
ETL / ELT
   ↓
Data Pipelines
   ↓
Cloud & Big Data
   ↓
Data Engineering
```

I am learning step-by-step and building my skills through practical examples.

---

# 👨‍💻 Developed By

## **Durga Vamsi**

> Learning Python step-by-step and building my journey toward **Data Engineering** 🚀🐍📊

**Day 06 completed successfully! 🎯**