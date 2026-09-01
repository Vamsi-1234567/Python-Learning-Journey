# 📅 Day 08 — Multiple Lists & Data Handling

Welcome to **Day 08** of my Python Learning Journey! 🚀🐍

Today I am going one step further with Python Lists.

In **Day 07**, I learned how to create lists, access elements, use indexing, find the length of a list, and loop through list items.

Today I will learn how to work with **multiple lists together** and connect related data using the same index position.

This is an important step toward understanding how real-world data is structured and processed.

---

# 🎯 Day 08 Learning Goal

By the end of Day 08, I will understand:

- How to create multiple lists
- How multiple lists can store related data
- How indexing connects data between lists
- How to use `range(len())`
- How to process multiple lists using a `for` loop
- How to calculate values from multiple lists
- How to connect product, price, and quantity data
- How this concept is useful for Data Engineering

---

# 📚 Topics Learned

1. Multiple Lists
2. Related Data
3. List Indexing
4. `len()`
5. `range()`
6. `range(len())`
7. `for` Loop with Multiple Lists
8. Calculations using Multiple Lists
9. Product + Price + Quantity Data
10. Basic Business Data Processing

---

# 🧠 1. What is a List?

A **list** is used to store multiple values in one variable.

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Here, the variable `products` contains multiple product names.

Each value has an index position.

```text
Index     Product
  0       Dog Food
  1       Cat Food
  2       Treats
  3       Toy
```

Python list indexing starts from **0**.

---

# 🧠 2. What is a Multiple List?

Sometimes one list is not enough.

For example, a Pet Shop needs to store:

- Product names
- Product prices
- Product quantities

We can create three separate lists:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

Each list stores a different type of information.

---

# 🔗 3. How Multiple Lists Are Connected

The important concept is the **index position**.

Look at the data:

```text
Index     Product       Price      Quantity
  0       Dog Food      1200          2
  1       Cat Food       900          3
  2       Treats         300          5
  3       Toy             500          4
```

At index `0`:

```python
products[0]     # Dog Food
prices[0]       # 1200
quantities[0]   # 2
```

So all three values belong to the same product.

### Simple understanding

```text
Same Index = Related Data
```

Idi chala important concept.

`products[0]`, `prices[0]`, and `quantities[0]` same index lo unnayi kabatti avi same product information ni represent chestayi.

---

# 🧪 4. Accessing Multiple Lists

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

print(products[0])
print(prices[0])
print(quantities[0])
```

### Output

```text
Dog Food
1200
2
```

Here:

```text
products[0]   → Dog Food
prices[0]     → 1200
quantities[0] → 2
```

---

# 🧠 5. Why Do We Need `len()`?

`len()` tells us how many elements are present in a list.

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

print(len(products))
```

### Output

```text
4
```

There are 4 products.

---

# 🔁 6. Using `range()` with `len()`

We can combine:

```python
range()
```

and

```python
len()
```

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

for i in range(len(products)):
    print(i)
```

### Output

```text
0
1
2
3
```

Here `i` represents the index.

---

# 🧠 7. Understanding `range(len())`

Suppose:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]
```

Then:

```python
len(products)
```

returns:

```text
4
```

So:

```python
range(len(products))
```

becomes:

```python
range(4)
```

Which produces:

```text
0
1
2
3
```

This allows us to access the same index from multiple lists.

---

# 🚀 8. Looping Through Multiple Lists

Example:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

for i in range(len(products)):
    print(products[i])
    print(prices[i])
    print(quantities[i])
```

### Output

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
Toy
500
4
```

The loop moves through the indexes one by one.

---

# 🔍 9. Understanding the Loop

Code:

```python
for i in range(len(products)):
```

First:

```text
i = 0
```

Then:

```python
products[0]
prices[0]
quantities[0]
```

Next:

```text
i = 1
```

Then:

```python
products[1]
prices[1]
quantities[1]
```

Then:

```text
i = 2
```

Then:

```python
products[2]
prices[2]
quantities[2]
```

Finally:

```text
i = 3
```

Then:

```python
products[3]
prices[3]
quantities[3]
```

So the loop processes all related data.

---

# 💰 10. Calculating Total Revenue

Now let's use multiple lists for a real business calculation.

Suppose:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

The revenue formula is:

```text
Revenue = Price × Quantity
```

Python:

```python
for i in range(len(products)):
    revenue = prices[i] * quantities[i]
    print(products[i], revenue)
```

### Output

```text
Dog Food 2400
Cat Food 2700
Treats 1500
Toy 2000
```

---

# 🧮 11. Understanding the Calculation

For Dog Food:

```python
prices[0] * quantities[0]
```

means:

```text
1200 × 2
```

Result:

```text
2400
```

For Cat Food:

```python
prices[1] * quantities[1]
```

means:

```text
900 × 3
```

Result:

```text
2700
```

For Treats:

```python
prices[2] * quantities[2]
```

means:

```text
300 × 5
```

Result:

```text
1500
```

For Toy:

```python
prices[3] * quantities[3]
```

means:

```text
500 × 4
```

Result:

```text
2000
```

---

# 📊 12. Complete Product Analysis

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

for i in range(len(products)):
    revenue = prices[i] * quantities[i]

    print("Product:", products[i])
    print("Price:", prices[i])
    print("Quantity:", quantities[i])
    print("Revenue:", revenue)
    print()
```

### Output

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
```

---

# 🏪 13. Life Care Pet Zone Example

Let's imagine **Life Care Pet Zone** has product sales data.

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

for i in range(len(products)):
    total = prices[i] * quantities[i]

    print(products[i], "Total:", total)
```

### Output

```text
Dog Food Total: 2400
Cat Food Total: 2700
Treats Total: 1500
Toy Total: 2000
```

This type of logic can be used for:

- Product sales
- Inventory systems
- Billing systems
- E-commerce applications
- Sales reports
- Business analytics

---

# 💡 14. Calculating Overall Revenue

We can also calculate the total revenue of all products.

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

total_revenue = 0

for i in range(len(products)):
    revenue = prices[i] * quantities[i]
    total_revenue = total_revenue + revenue

print("Total Revenue:", total_revenue)
```

### Output

```text
Total Revenue: 8600
```

### Calculation

```text
Dog Food = 1200 × 2 = 2400

Cat Food = 900 × 3 = 2700

Treats = 300 × 5 = 1500

Toy = 500 × 4 = 2000

Total = 2400 + 2700 + 1500 + 2000

Total Revenue = 8600
```

---

# 🔄 15. Important Pattern

One important pattern I learned today:

```python
total = 0

for i in range(len(list)):
    amount = ...
    total = total + amount
```

This pattern is called an **accumulator pattern**.

It is useful for calculating:

- Total sales
- Total revenue
- Total quantity
- Total expenses
- Total orders
- Total marks
- Total transactions

---

# 🧠 16. Multiple Lists + Index

The most important idea from Day 08:

```python
products[i]
prices[i]
quantities[i]
```

The same `i` connects the data.

For example:

```text
i = 2

products[2]     → Treats
prices[2]       → 300
quantities[2]   → 5
```

Therefore:

```python
prices[2] * quantities[2]
```

becomes:

```text
300 × 5 = 1500
```

---

# ⚠️ 17. List Length Should Match

When using multiple related lists, their lengths should normally match.

Correct:

```python
products = ["Dog Food", "Cat Food", "Treats"]

prices = [1200, 900, 300]

quantities = [2, 3, 5]
```

All lists contain 3 elements.

Incorrect:

```python
products = ["Dog Food", "Cat Food", "Treats"]

prices = [1200, 900]

quantities = [2, 3, 5]
```

Here the number of elements is different.

This can cause an indexing error when the loop reaches an index that does not exist in one of the lists.

---

# 🧪 18. Checking List Lengths

We can check the lengths:

```python
print(len(products))
print(len(prices))
print(len(quantities))
```

Example output:

```text
4
4
4
```

This means all three lists have the same number of elements.

---

# 🏗️ 19. Real-World Data Processing

In real applications, data often contains multiple related values.

For example:

```text
Product → Price → Quantity
```

or:

```text
Employee → Salary → Experience
```

or:

```text
Student → Marks → Grade
```

or:

```text
Order → Amount → Quantity
```

Python can process this type of data using loops and indexes.

This is an important foundation for later Data Engineering concepts.

---

# 🐍 20. Day 07 vs Day 08

### Day 07

I learned:

```python
products = ["Dog Food", "Cat Food", "Treats"]
```

I mainly worked with one list.

### Day 08

Now I am working with related lists:

```python
products = ["Dog Food", "Cat Food", "Treats"]

prices = [1200, 900, 300]

quantities = [2, 3, 5]
```

Then:

```python
for i in range(len(products)):
    print(products[i], prices[i], quantities[i])
```

So Day 08 builds directly on Day 07.

---

# 🧩 21. Practice Task 1 — Product Information

Create:

```python
products = ["Food", "Ball", "Treats"]

prices = [1000, 400, 250]

quantities = [2, 3, 4]
```

Use a loop to print:

```text
Product
Price
Quantity
```

for every product.

---

# 🧩 22. Practice Task 2 — Calculate Revenue

Using the same lists, calculate:

```text
Revenue = Price × Quantity
```

Expected output:

```text
Food 2000
Ball 1200
Treats 1000
```

---

# 🧩 23. Practice Task 3 — Total Revenue

Calculate the total revenue.

Expected:

```text
Total Revenue: 4200
```

---

# 🧩 24. Practice Task 4 — Product Count

Create a product list:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy", "Leash"]
```

Find the number of products using:

```python
len()
```

Expected:

```text
5
```

---

# 🧩 25. Practice Task 5 — Print Using Index

Create three lists:

```python
products = ["Dog Food", "Cat Food", "Toy"]

prices = [1200, 900, 500]

quantities = [2, 3, 4]
```

Use:

```python
for i in range(len(products)):
```

and print all related information.

---

# 🚀 26. Day 08 Challenge

Create a simple sales report.

Use:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

Your program should calculate:

1. Product name
2. Price
3. Quantity
4. Revenue for each product
5. Total revenue

Expected total:

```text
Total Revenue: 8600
```

---

# ❌ 27. Common Beginner Mistakes

### Mistake 1 — Wrong Index

```python
print(products[4])
```

If the list contains only 4 elements, valid indexes are:

```text
0, 1, 2, 3
```

---

### Mistake 2 — Forgetting `range()`

Incorrect:

```python
for i in len(products):
    print(products[i])
```

Correct:

```python
for i in range(len(products)):
    print(products[i])
```

---

### Mistake 3 — Mixing Indexes

Incorrect:

```python
print(products[0])
print(prices[1])
print(quantities[2])
```

This combines different products.

Correct:

```python
print(products[0])
print(prices[0])
print(quantities[0])
```

Same index means related data.

---

### Mistake 4 — Different List Lengths

Always make sure related lists contain the expected number of elements.

```python
len(products)
len(prices)
len(quantities)
```

---

# 📌 28. Quick Reference

| Concept | Example |
|---|---|
| List | `products = ["Food", "Toy"]` |
| Index | `products[0]` |
| Length | `len(products)` |
| Range | `range(4)` |
| Loop | `for i in range(4):` |
| Multiple Lists | `products`, `prices`, `quantities` |
| Same Index | `products[i]`, `prices[i]` |
| Calculation | `prices[i] * quantities[i]` |
| Accumulator | `total = total + amount` |

---

# 🧠 29. Key Concepts I Learned

### 1. Multiple Lists

I can store different categories of related data in separate lists.

### 2. Indexing

Each list uses index positions starting from `0`.

### 3. Same Index

Using the same index allows me to connect related information.

### 4. `len()`

`len()` tells me how many elements are in a list.

### 5. `range(len())`

This allows me to loop through indexes.

### 6. Multiple List Processing

I can process several related lists using one loop.

### 7. Calculations

I can perform calculations using values from multiple lists.

### 8. Accumulator

I can continuously add values to calculate a final total.

---

# 💼 30. Business Applications

The concepts from Day 08 can be used in:

- 🛒 E-commerce
- 📦 Inventory Management
- 💰 Sales Analysis
- 🧾 Billing Systems
- 🐾 Pet Shop Management
- 📊 Business Reports
- 🚚 Order Processing
- 📈 Data Analysis
- 🗄️ Data Engineering

---

# 🏗️ 31. Data Engineering Connection

Data Engineers work with large amounts of structured data.

Today I learned how different pieces of related data can be connected using indexes.

For example:

```text
Product
   ↓
Price
   ↓
Quantity
   ↓
Revenue
```

This is a small Python example, but it helps me understand the basic idea of processing structured data.

Later, I will learn more powerful tools and technologies for handling large datasets.

---

# 📝 32. What I Understood Today

Today I understood that multiple lists can store different types of related information.

For example:

```python
products = ["Dog Food", "Cat Food", "Treats"]

prices = [1200, 900, 300]

quantities = [2, 3, 5]
```

Using the same index:

```python
products[i]
prices[i]
quantities[i]
```

I can connect the information and perform calculations.

---

# 🎯 33. My Day 08 Learning

Today I learned:

- ✅ Multiple Lists
- ✅ Related Data
- ✅ List Indexing
- ✅ `len()`
- ✅ `range()`
- ✅ `range(len())`
- ✅ For Loop with Multiple Lists
- ✅ Product Data Processing
- ✅ Revenue Calculation
- ✅ Total Revenue
- ✅ Accumulator Pattern
- ✅ Basic Business Data Processing

---

# 🏆 34. Day 08 Achievement

```text
Day 08 Completed! 🎉

I can now work with multiple related lists
and process their data using Python loops.
```

---

# 📈 Overall Python Learning Progress

```text
Day 01 → Python Basics
Day 02 → Variables & Data Types
Day 03 → Input & Type Conversion
Day 04 → Operators & Calculations
Day 05 → Conditional Statements
Day 06 → For Loops & Iteration
Day 07 → Lists
Day 08 → Multiple Lists & Data Handling
```

### Current Progress

```text
Python Fundamentals
████████░░░░░░░░░░░░ 40%
```

I am building my Python fundamentals step by step.

---

# 🚀 Next Step — Day 09

In Day 09, I will continue working with Python data and build more practical **sales/inventory analysis** logic.

The goal is to move from basic Python syntax toward solving real-world data problems.

---

# 🐍 Python Learning Journey

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
Multiple Lists
      ↓
Data Processing
      ↓
Functions
      ↓
Data Structures
      ↓
Data Engineering 🚀
```

---

# 👨‍💻 Developed By

## Durga Vamsi

> Learning Python step by step with the goal of becoming a **Data Engineer**.

**Day 08 — Completed Successfully! 🚀🐍**