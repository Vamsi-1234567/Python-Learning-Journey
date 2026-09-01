# 📅 Day 05 — Conditional Statements

Welcome to **Day 05** of my Python Learning Journey! 🚀🐍

Today I learned how Python can **make decisions based on conditions**.

Until Day 04, I learned how to store data, take input, perform calculations, and use operators.

Now I am learning how to tell Python:

> **"If this condition is true, do this. Otherwise, do something else."**

This is called **Conditional Logic**.

---

# 🎯 Day 05 Learning Goal

By the end of Day 05, I should understand:

- What conditional statements are
- How `if` works
- How `else` works
- How `elif` works
- How comparison operators work
- How to create conditions
- How Python makes decisions
- How conditions can be used in real-world business logic

---

# 📚 Topics Learned

### 1. Conditional Statements

### 2. `if` Statement

### 3. `else` Statement

### 4. `elif` Statement

### 5. Comparison Operators

### 6. Boolean Conditions

### 7. Multiple Conditions

### 8. Business Logic Using Conditions

---

# 🧠 What Are Conditional Statements?

Conditional statements are used to make **decisions** in Python.

Simple ga cheppali ante:

**Condition true అయితే one action, false అయితే another action.**

Example:

```python
age = 20

if age >= 18:
    print("Eligible")
```

Here Python checks:

```text
Is age greater than or equal to 18?
```

If the answer is `True`, Python executes the `print()` statement.

### Real-world example

Suppose a pet shop gives free delivery for orders above ₹1000.

```python
order_total = 1200

if order_total >= 1000:
    print("Free Delivery")
```

Output:

```text
Free Delivery
```

---

# 🔹 1. `if` Statement

The `if` statement is used when we want Python to perform an action **only when a condition is true**.

### Syntax

```python
if condition:
    statement
```

The colon `:` is important.

The code inside the `if` block must be indented.

---

# 💻 Example 1 — Simple `if`

```python
price = 1200

if price > 1000:
    print("Premium Product")
```

Output:

```text
Premium Product
```

### Explanation

Python checks:

```text
price > 1000
1200 > 1000
True
```

Because the condition is `True`, Python executes:

```python
print("Premium Product")
```

---

# 💻 Example 2 — Condition Is False

```python
price = 500

if price > 1000:
    print("Premium Product")
```

Output:

```text
```

Nothing is printed because:

```text
500 > 1000
False
```

So Python skips the `if` block.

---

# 🔹 2. `else` Statement

Sometimes we want Python to perform one action when the condition is true and another action when it is false.

For this, we use `else`.

### Syntax

```python
if condition:
    statement
else:
    statement
```

---

# 💻 Example

```python
price = 500

if price >= 1000:
    print("Free Delivery")
else:
    print("Delivery Charges Apply")
```

Output:

```text
Delivery Charges Apply
```

### Explanation

Python checks:

```text
500 >= 1000
False
```

So the `if` block is skipped.

Python executes the `else` block.

---

# 🐾 Life Care Pet Zone Example

Suppose a customer order is ₹1500.

```python
order_total = 1500

if order_total >= 1000:
    print("Free Delivery")
else:
    print("Delivery Charges Apply")
```

Output:

```text
Free Delivery
```

This is an example of **business logic**.

---

# 🔹 3. `elif` Statement

`elif` means:

> **else if**

It is used when we have **multiple conditions**.

### Syntax

```python
if condition1:
    statement
elif condition2:
    statement
else:
    statement
```

Python checks the conditions from top to bottom.

---

# 💻 Example

```python
price = 800

if price >= 1500:
    print("Premium Product")
elif price >= 800:
    print("Standard Product")
else:
    print("Budget Product")
```

Output:

```text
Standard Product
```

### How Python checks

```text
price >= 1500
800 >= 1500
False

price >= 800
800 >= 800
True
```

So Python executes:

```python
print("Standard Product")
```

---

# 🔄 How `if`, `elif`, and `else` Work

Consider:

```python
price = 500

if price >= 1500:
    print("Premium")
elif price >= 800:
    print("Standard")
else:
    print("Budget")
```

Python follows this flow:

```text
             price >= 1500?
                  |
            +-----+-----+
            |           |
          True        False
            |           |
         Premium     price >= 800?
                        |
                  +-----+-----+
                  |           |
                True        False
                  |           |
              Standard      Budget
```

Only the matching block is executed.

---

# 🔢 Comparison Operators

Comparison operators are used to compare two values.

They return:

```text
True
```

or

```text
False
```

---

# 📊 Comparison Operator Table

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `10 == 10` | `True` |
| `!=` | Not equal to | `10 != 5` | `True` |
| `>` | Greater than | `10 > 5` | `True` |
| `<` | Less than | `5 < 10` | `True` |
| `>=` | Greater than or equal to | `10 >= 10` | `True` |
| `<=` | Less than or equal to | `5 <= 10` | `True` |

---

# 🔹 `==` Equal To

Used to check whether two values are equal.

```python
price = 500

if price == 500:
    print("Price is 500")
```

Output:

```text
Price is 500
```

### Important

`=` means assignment.

```python
price = 500
```

`==` means comparison.

```python
price == 500
```

This difference is very important.

---

# 🔹 `!=` Not Equal To

Checks whether two values are different.

```python
price = 500

if price != 1000:
    print("Price is not 1000")
```

Output:

```text
Price is not 1000
```

---

# 🔹 `>` Greater Than

```python
price = 1200

if price > 1000:
    print("High Value Product")
```

Output:

```text
High Value Product
```

---

# 🔹 `<` Less Than

```python
price = 300

if price < 500:
    print("Low Price Product")
```

Output:

```text
Low Price Product
```

---

# 🔹 `>=` Greater Than or Equal To

```python
order_total = 1000

if order_total >= 1000:
    print("Free Delivery")
```

Output:

```text
Free Delivery
```

Here:

```text
1000 >= 1000
```

is `True`.

---

# 🔹 `<=` Less Than or Equal To

```python
quantity = 3

if quantity <= 5:
    print("Small Order")
```

Output:

```text
Small Order
```

---

# 🧠 Boolean Conditions

Conditions usually produce a Boolean value.

Boolean values are:

```python
True
False
```

Example:

```python
price = 1200

print(price > 1000)
```

Output:

```text
True
```

Another example:

```python
price = 500

print(price > 1000)
```

Output:

```text
False
```

So we can think of a condition like:

```text
Condition → True / False
```

Python then decides what code should execute.

---

# 🛒 Business Logic Example

Suppose Life Care Pet Zone has the following rule:

```text
Order >= ₹1000 → Free Delivery
Order < ₹1000 → Delivery Charges
```

Python implementation:

```python
order_total = 1200

if order_total >= 1000:
    print("Free Delivery")
else:
    print("Delivery Charges Apply")
```

Output:

```text
Free Delivery
```

---

# 🐶 Pet Shop Product Example

```python
product = "Dog Food"
price = 1200

if price >= 1000:
    print(product, "is a premium product")
else:
    print(product, "is a regular product")
```

Output:

```text
Dog Food is a premium product
```

---

# 📦 Inventory Example

Suppose we want to check whether a product is available.

```python
stock = 10

if stock > 0:
    print("Product Available")
else:
    print("Out of Stock")
```

Output:

```text
Product Available
```

If:

```python
stock = 0
```

Output:

```text
Out of Stock
```

This is another example of real-world business logic.

---

# 💰 Discount Example

Suppose customers get a discount when their order is above ₹2000.

```python
order_total = 2500

if order_total >= 2000:
    print("10% Discount Available")
else:
    print("No Discount")
```

Output:

```text
10% Discount Available
```

---

# 📊 Multiple Conditions Using `elif`

Suppose we classify orders:

```text
₹2000 or above → Premium Order
₹1000 or above → Standard Order
Below ₹1000 → Small Order
```

Python:

```python
order_total = 1500

if order_total >= 2000:
    print("Premium Order")
elif order_total >= 1000:
    print("Standard Order")
else:
    print("Small Order")
```

Output:

```text
Standard Order
```

---

# 🧮 Combining Variables With Conditions

We can use calculations inside conditions.

```python
price = 500
quantity = 3

total = price * quantity

if total >= 1000:
    print("Free Delivery")
else:
    print("Delivery Charges Apply")
```

Output:

```text
Free Delivery
```

Calculation:

```text
500 × 3 = 1500
```

Then:

```text
1500 >= 1000
True
```

Therefore:

```text
Free Delivery
```

---

# 🧑‍💻 Complete Business Example

```python
product = "Dog Food"
price = 1200
quantity = 2

total = price * quantity

print("Product:", product)
print("Price:", price)
print("Quantity:", quantity)
print("Total:", total)

if total >= 2000:
    print("Premium Order")
elif total >= 1000:
    print("Standard Order")
else:
    print("Small Order")
```

Output:

```text
Product: Dog Food
Price: 1200
Quantity: 2
Total: 2400
Premium Order
```

---

# 🔍 Step-by-Step Execution

Python first stores:

```python
product = "Dog Food"
price = 1200
quantity = 2
```

Then calculates:

```python
total = price * quantity
```

So:

```text
1200 × 2 = 2400
```

Then Python checks:

```python
if total >= 2000:
```

That becomes:

```text
2400 >= 2000
True
```

Therefore:

```text
Premium Order
```

---

# ⚠️ Important: Indentation

Python uses indentation to identify a block of code.

Correct:

```python
price = 1200

if price >= 1000:
    print("Premium Product")
```

Incorrect:

```python
price = 1200

if price >= 1000:
print("Premium Product")
```

The `print()` statement should be indented.

Usually we use **4 spaces**.

---

# ⚠️ Common Beginner Mistakes

## Mistake 1 — Using `=` Instead of `==`

Wrong:

```python
if price = 500:
    print("Price is 500")
```

Correct:

```python
if price == 500:
    print("Price is 500")
```

Remember:

```text
=   → Assignment
==  → Comparison
```

---

## Mistake 2 — Forgetting `:`

Wrong:

```python
if price > 1000
    print("Premium")
```

Correct:

```python
if price > 1000:
    print("Premium")
```

---

## Mistake 3 — Wrong Indentation

Wrong:

```python
if price > 1000:
print("Premium")
```

Correct:

```python
if price > 1000:
    print("Premium")
```

---

## Mistake 4 — Wrong Condition Order

Example:

```python
price = 1500

if price >= 1000:
    print("Standard")
elif price >= 1500:
    print("Premium")
```

Here `1500 >= 1000` is already `True`, so Python never reaches the `elif`.

Better:

```python
price = 1500

if price >= 1500:
    print("Premium")
elif price >= 1000:
    print("Standard")
else:
    print("Budget")
```

Output:

```text
Premium
```

So, when using ranges, **condition order matters**.

---

# 📝 Practice Tasks

## Task 1 — Check Price

Create a variable:

```python
price = 1200
```

If price is greater than 1000, print:

```text
Expensive Product
```

---

## Task 2 — Check Stock

Create:

```python
stock = 5
```

If stock is greater than 0:

```text
Product Available
```

Otherwise:

```text
Out of Stock
```

---

## Task 3 — Free Delivery

Create:

```python
total = 1500
```

If total is greater than or equal to 1000:

```text
Free Delivery
```

Otherwise:

```text
Delivery Charges Apply
```

---

## Task 4 — Product Classification

Use:

```python
price = 1800
```

Conditions:

```text
1500 or above → Premium
800 or above → Standard
Below 800 → Budget
```

---

## Task 5 — Pet Shop Order

Create:

```python
product = "Dog Food"
price = 900
quantity = 2
```

Calculate:

```python
total = price * quantity
```

Then check whether the customer qualifies for free delivery.

---

# 🎯 Day 05 Challenge

Create a simple order classification program.

Use:

```python
product = "Dog Food"
price = 1200
quantity = 2
```

Calculate the total.

Then use conditions:

```text
Total >= 2000 → Premium Customer
Total >= 1000 → Regular Customer
Total < 1000 → Small Order
```

Expected output:

```text
Product: Dog Food
Total: 2400
Premium Customer
```

---

# 💡 Real-World Applications

Conditional statements are very important in programming and Data Engineering.

They can be used for:

- Checking whether data is valid
- Checking stock availability
- Applying discounts
- Calculating delivery charges
- Categorizing customers
- Checking order status
- Data validation
- Business rules
- Filtering records
- Processing different types of data

Example:

```python
age = 25

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

This same decision-making concept is used in many larger programs.

---

# 📌 Quick Reference

```python
# if

if condition:
    statement
```

```python
# if + else

if condition:
    statement
else:
    statement
```

```python
# if + elif + else

if condition1:
    statement
elif condition2:
    statement
else:
    statement
```

### Comparison Operators

```text
==    Equal
!=    Not Equal
>     Greater Than
<     Less Than
>=    Greater Than or Equal
<=    Less Than or Equal
```

---

# 🧠 What I Understood Today

Today I understood that Python can make decisions using **conditional statements**.

I learned that:

```text
if     → checks a condition
elif   → checks another condition
else   → runs when previous conditions are false
```

I also learned that comparison operators return:

```text
True
False
```

These results help Python decide which block of code should execute.

---

# 📚 My Day 05 Learning

Today I practiced:

- `if`
- `elif`
- `else`
- `==`
- `!=`
- `>`
- `<`
- `>=`
- `<=`
- Boolean conditions
- Business logic
- Order classification
- Delivery conditions
- Inventory conditions

---

# 🏆 Day 05 Achievement

I can now write Python programs that **make decisions based on conditions**.

### My Progress

```text
Day 01 → Python Basics              ✅
Day 02 → Variables & Data Types     ✅
Day 03 → Input & Type Conversion    ✅
Day 04 → Operators & Calculations   ✅
Day 05 → Conditional Statements     ✅
```

---

# 🚀 Next Step — Day 06

In **Day 06**, I will learn about:

```text
Loops
for loop
range()
Iteration
```

I will learn how to make Python **repeat tasks automatically**.

This will be useful when working with lists of products, orders, customers, sales data, and eventually large datasets.

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

**Day 05 completed successfully! 🎯**