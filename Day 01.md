# 📅 Day 01 — Python Basics

Welcome to **Day 01 of my Python Learning Journey** 🐍🚀

Day 01 is the starting point of my Python learning journey.  
In this day, I learned the **basic structure of Python programs**, how Python executes instructions, how to use `print()`, and how to store information using **variables**.

The main goal of Day 01 was to understand the **fundamentals of Python programming** before moving to more advanced concepts.

---

## 🎯 Day 01 Learning Goal

The main goal of Day 01 was to understand:

- Python basic syntax
- How Python programs execute
- `print()` function
- Variables
- Storing data in variables
- Comments
- Basic programming structure

---

# 📚 Topics Learned

## 1. 🐍 What is Python?

Python is a programming language used to write instructions that a computer can understand and execute.

Python is beginner-friendly because its syntax is simple and easy to read.

### Telugu + English Explanation

Python ante computer ki manam instructions ivvadaniki use chese programming language.

Simple ga cheppali ante:

```text
Manam problem ni solve cheyadaniki
        ↓
Python lo instructions rastam
        ↓
Python aa instructions ni execute chestundi
        ↓
Manaki output vastundi
```

Example:

```python
print("Hello Python")
```

Output:

```text
Hello Python
```

Ikkada Python ki `Hello Python` ni screen meeda display cheyyamani instruction icham.

---

# 2. 📝 Python Basic Syntax

**Syntax** ante Python code rayadaniki follow avvalsina basic rules.

Python lo code clean ga and correct syntax tho rayali.

Example:

```python
print("Hello")
```

Output:

```text
Hello
```

### Telugu + English Explanation

Syntax ante oka language lo code rayadaniki follow avvalsina rules.

Manam English lo grammar follow chestam kada, alage Python lo kuda syntax rules follow cheyali.

Correct syntax:

```python
print("Hello")
```

Wrong syntax:

```python
print("Hello"
```

Second example lo closing `)` missing undi, kabatti Python error chupinchachu.

---

# 3. 🖨️ `print()` Function

`print()` Python lo screen meeda output display cheyadaniki use chestam.

## 💻 Basic Example

```python
print("Hello")
```

Output:

```text
Hello
```

Another example:

```python
print("Welcome to Python")
```

Output:

```text
Welcome to Python
```

### Telugu + English Explanation

`print()` ante **screen meeda information chupinchadam**.

Manam Python program run chesinappudu result ni user ki display cheyali ante `print()` use chestam.

Example:

```python
print("Dog Food")
```

Output:

```text
Dog Food
```

---

# 4. 📝 Printing Text

Python lo text ni print cheyadaniki text ni quotes madhya rayali.

Example:

```python
print("Dog Food")
print("Cat Food")
print("Pet Toy")
```

Output:

```text
Dog Food
Cat Food
Pet Toy
```

### Telugu + English Explanation

Text ni Python lo **String** laga represent chestam.

Text ni quotes madhya rayadam common format.

Example:

```python
"Dog Food"
"Cat Food"
"Pet Toy"
```

---

# 5. 🔢 Printing Numbers

Python lo numbers ni kuda `print()` tho display cheyachu.

Example:

```python
print(1200)
print(500)
print(100)
```

Output:

```text
1200
500
100
```

### Telugu + English Explanation

Number ni quotes lekunda kuda print cheyachu.

Example:

```python
print(1200)
```

Ikkada `1200` number.

Kani:

```python
print("1200")
```

Ikkada `"1200"` text/string laga treat avtundi.

Day 01 lo important point:

```text
1200    → Number
"1200"  → Text
```

---

# 6. 📦 Variables

Python lo information ni store cheyadaniki **variables** use chestam.

Example:

```python
product = "Dog Food"
price = 1200
```

Ikkada:

```text
product → Variable
"Dog Food" → Stored Value

price → Variable
1200 → Stored Value
```

### Telugu + English Explanation

Variable ante oka **container / box** laga think cheyachu.

Manam oka value ni future lo use cheyali ante danini variable lo store chestam.

Example:

```python
product = "Dog Food"
```

Ante:

```text
product
   ↓
"Dog Food"
```

Alage:

```python
price = 1200
```

Ante:

```text
price
  ↓
1200
```

---

# 7. 💻 Using Variables with `print()`

Variable lo value store chesina taruvata aa value ni `print()` cheyachu.

Example:

```python
product = "Dog Food"
price = 1200

print(product)
print(price)
```

Output:

```text
Dog Food
1200
```

### Telugu + English Explanation

First manam values ni variables lo store chesam:

```python
product = "Dog Food"
price = 1200
```

Taruvata variables ni print chesam:

```python
print(product)
print(price)
```

Python variable lo unna value ni read chesi output lo display chestundi.

---

# 8. 🔄 Variable Assignment

Variable create chesi value assign cheyadam ni **variable assignment** antam.

Example:

```python
product = "Dog Food"
price = 1200
quantity = 2
```

Ikkada:

```text
product  → "Dog Food"
price    → 1200
quantity → 2
```

### Telugu + English Explanation

`=` symbol ni variable ki value assign cheyadaniki use chestam.

Example:

```python
price = 1200
```

Idi:

```text
price ki 1200 value assign chey
```

ani meaning.

---

# 9. 🧠 Variable Naming

Variables ki meaningful names use cheyadam important.

Example:

```python
product = "Dog Food"
price = 1200
quantity = 2
```

Ivi easy ga understand cheyachu.

Instead of:

```python
x = "Dog Food"
y = 1200
z = 2
```

Meaningful names better:

```python
product = "Dog Food"
price = 1200
quantity = 2
```

### Telugu + English Explanation

Variable name chustene aa variable lo emi store chesamo easy ga ardham avvali.

Example:

```python
price = 1200
```

`price` ani name chustene idi product price ani easy ga understand cheyachu.

---

# 10. 💬 Comments in Python

Comments ante code gurinchi explanation or note rayadaniki use chese text.

Python lo single-line comment kosam `#` use chestam.

Example:

```python
# Product information

product = "Dog Food"
price = 1200
```

### Telugu + English Explanation

Comment ni Python execute cheyadu.

Comment mainly developer ki code ardham avvadaniki use avtundi.

Example:

```python
# Store product name
product = "Dog Food"

# Store product price
price = 1200
```

Ikkada:

```python
# Store product name
```

and

```python
# Store product price
```

comments.

---

# 11. 📌 Why Comments Are Useful

Comments use cheyadam valla code ni future lo chusinappudu easy ga understand cheyachu.

Example:

```python
# Product details

product = "Dog Food"
price = 1200
```

### Telugu + English Explanation

Manam today code rasina taruvata konni days/months taruvata malli code chuste konni lines enduku rasamo marchipovachu.

Comments unte code purpose easy ga gurthostundi.

---

# 12. 🧩 Storing Real-World Data

Day 01 lo real-world example ga product information ni variables lo store chesanu.

Example:

```python
product = "Dog Food"
price = 1200
```

Ikkada:

```text
product → Dog Food
price   → 1200
```

### Telugu + English Explanation

Real-world applications lo information ni variables lo store cheyadam chala important.

Example:

```text
Pet Shop
   ↓
Product
   ↓
Dog Food

Price
   ↓
1200
```

Python lo:

```python
product = "Dog Food"
price = 1200
```

---

# 💻 Day 01 Complete Example

```python
# Product information

product = "Dog Food"
price = 1200

print(product)
print(price)
```

## 📊 Output

```text
Dog Food
1200
```

---

# 💻 Day 01 Example — Multiple Products

```python
# Product details

product1 = "Dog Food"
price1 = 1200

product2 = "Cat Food"
price2 = 900

product3 = "Pet Toy"
price3 = 500

print(product1)
print(price1)

print(product2)
print(price2)

print(product3)
print(price3)
```

## 📊 Output

```text
Dog Food
1200
Cat Food
900
Pet Toy
500
```

---

# 💡 Understanding the Code

Let's understand the above code step by step.

### Step 1 — Store Product

```python
product1 = "Dog Food"
```

Meaning:

```text
product1
   ↓
Dog Food
```

### Step 2 — Store Price

```python
price1 = 1200
```

Meaning:

```text
price1
  ↓
1200
```

### Step 3 — Display Product

```python
print(product1)
```

Output:

```text
Dog Food
```

### Step 4 — Display Price

```python
print(price1)
```

Output:

```text
1200
```

---

# 🧠 Important Python Concepts from Day 01

## Variable

```python
price = 1200
```

A variable stores information.

---

## Value

```python
1200
```

The actual information stored inside the variable.

---

## Assignment Operator

```python
=
```

Used to assign a value to a variable.

Example:

```python
price = 1200
```

---

## Print Function

```python
print()
```

Used to display output.

Example:

```python
print(price)
```

---

## Comment

```python
# This is a comment
```

Used to add notes or explanations inside code.

---

# 🔍 Python Execution Flow

Day 01 lo Python code ela execute avtundo basic ga understand chesanu.

Example:

```python
product = "Dog Food"
price = 1200

print(product)
print(price)
```

Execution flow:

```text
Python Program
      ↓
Read the code
      ↓
Create product variable
      ↓
Store "Dog Food"
      ↓
Create price variable
      ↓
Store 1200
      ↓
print(product)
      ↓
Display Dog Food
      ↓
print(price)
      ↓
Display 1200
```

---

# 🐾 Real-World Example — Pet Shop

Day 01 concepts ni **Pet Shop / Life Care Pet Zone** example tho practice chesanu.

```python
product = "Dog Food"
price = 1200

print("Product:", product)
print("Price:", price)
```

## 📊 Output

```text
Product: Dog Food
Price: 1200
```

### Telugu + English Explanation

Ikkada real-world product information ni Python variables lo store chesi, `print()` function tho display chesanu.

Idi future lo:

```text
Product Management
       ↓
Sales
       ↓
Billing
       ↓
Inventory
       ↓
Data Analysis
```

lanti applications ki basic foundation.

---

# 🎯 Day 01 Practice Tasks

## Practice Task 1 — Product

```python
product = "Dog Food"
print(product)
```

Expected Output:

```text
Dog Food
```

---

## Practice Task 2 — Price

```python
price = 1200
print(price)
```

Expected Output:

```text
1200
```

---

## Practice Task 3 — Product + Price

```python
product = "Dog Food"
price = 1200

print(product)
print(price)
```

Expected Output:

```text
Dog Food
1200
```

---

## Practice Task 4 — Product Information

```python
product = "Dog Food"
price = 1200
quantity = 2

print(product)
print(price)
print(quantity)
```

Expected Output:

```text
Dog Food
1200
2
```

---

# 🧪 Day 01 Practice Program

```python
# Life Care Pet Zone - Product Information

product = "Dog Food"
price = 1200

print("Product:", product)
print("Price:", price)
```

## 📊 Output

```text
Product: Dog Food
Price: 1200
```

---

# 🧠 What I Understood in Day 01

Day 01 lo nenu following concepts understand chesanu:

### 1. Python Basics

Python programming language tho computer ki instructions ivvachu.

### 2. Basic Syntax

Python code correct syntax tho rayali.

### 3. `print()`

Output ni screen meeda display cheyadaniki `print()` use chestam.

### 4. Variables

Data ni store cheyadaniki variables use chestam.

### 5. Assignment

`=` operator tho value ni variable ki assign chestam.

### 6. Comments

`#` use chesi code gurinchi notes rayachu.

### 7. Real-World Data

Product name, price lanti information ni variables lo store cheyachu.

---

# 📚 Day 01 Key Notes

```text
Python
  ↓
Programming Language

print()
  ↓
Display Output

Variable
  ↓
Store Information

=
  ↓
Assign Value

#
  ↓
Comment
```

---

# 🔑 Important Syntax

## Print Text

```python
print("Hello")
```

## Print Number

```python
print(1200)
```

## Create Variable

```python
price = 1200
```

## Store Text

```python
product = "Dog Food"
```

## Print Variable

```python
print(product)
```

## Comment

```python
# Product information
```

---

# ❌ Common Beginner Mistakes

## Mistake 1 — Missing Quotes for Text

Incorrect:

```python
product = Dog Food
```

Correct:

```python
product = "Dog Food"
```

---

## Mistake 2 — Missing Closing Bracket

Incorrect:

```python
print("Hello"
```

Correct:

```python
print("Hello")
```

---

## Mistake 3 — Confusing Variable Name and Value

Example:

```python
product = "Dog Food"
```

Here:

```text
product   → Variable
"Dog Food" → Value
```

---

# 💭 My Day 01 Learning in Telugu + English

Day 01 na Python journey ki **basic foundation**.

Ee day lo nenu Python ante enti, basic syntax ela use cheyali, `print()` function tho output ela display cheyali, variables lo data ela store cheyali ane concepts nerchukunnanu.

Starting lo simple ga anipinchina, ee concepts future Python programming ki chala important.

Example:

```text
Variables
   ↓
Data Types
   ↓
Conditions
   ↓
Loops
   ↓
Lists
   ↓
Functions
   ↓
Dictionaries
   ↓
Data Processing
   ↓
Data Engineering
```

So, **Day 01 is the foundation for my complete Python learning journey.**

---

# 🏆 Day 01 Achievement

By completing Day 01, I learned:

- ✅ Python basics
- ✅ Basic Python syntax
- ✅ `print()`
- ✅ Variables
- ✅ Variable assignment
- ✅ Storing information
- ✅ Printing stored values
- ✅ Comments
- ✅ Basic program execution
- ✅ Real-world product examples

---

# 📝 What I Learned — Day 01

### English

I learned the basic structure of Python programs and how Python executes simple instructions.

I learned how to use `print()` to display output, how to create variables, how to store information inside variables, and how to use comments to explain code.

I also practiced these concepts using simple **Pet Shop / Life Care Pet Zone** examples.

### Telugu + English

Nenu Day 01 lo Python programming yokka basic foundation nerchukunnanu.

`print()` use chesi output display cheyadam, variables create cheyadam, variables lo information store cheyadam, `=` operator tho values assign cheyadam, and comments use cheyadam practice chesanu.

Real-world example ga **Pet Shop / Life Care Pet Zone** products ni use chesi practice chesanu.

---

# 🎯 Day 01 Summary

```text
Day 01
  ↓
Python Basics
  ↓
Basic Syntax
  ↓
print()
  ↓
Variables
  ↓
Assignment
  ↓
Comments
  ↓
Store Data
  ↓
Display Data
  ↓
Real-World Practice
```

---

# 🚀 Next Step

## 📅 Day 02 — Variables & Data Types

In Day 02, I will learn about different types of data used in Python:

- `str`
- `int`
- `float`
- `bool`

and understand how Python handles different types of values.

---

## 🐍 Python Learning Journey

**Day 01 → Completed ✅**

> **Learn → Practice → Make Mistakes → Understand → Improve.** 🚀