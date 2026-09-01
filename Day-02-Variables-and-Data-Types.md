# 📅 Day 02 — Variables & Data Types

Welcome to **Day 02 of my Python Learning Journey** 🐍🚀

Day 02 lo nenu Python lo different types of data ni understand cheyadam and variables lo different values ni store cheyadam nerchukunnanu.

Day 01 lo variables and basic `print()` nerchukunna taruvata, Day 02 lo variables lo store ayye data different types lo untundi ani practice chesanu.

---

# 🎯 Day 02 Learning Goal

The main goal of Day 02 was to understand:

- 📦 Variables
- 📝 Strings
- 🔢 Integers
- 🔢 Floats
- ✅ Booleans
- 🔄 Variable assignment
- 🧠 Different types of values
- 💻 Using different data types in Python programs

---

# 📚 Topics Learned

- `str` — String
- `int` — Integer
- `float` — Float
- `bool` — Boolean
- Variable assignment
- Storing different types of values
- Printing different data types

---

# 1. 📦 Variables

Variable ante data ni store cheyadaniki use chese name.

Example:

```python
product = "Dog Food"
price = 1200
```

Ikkada:

```text
product
   ↓
"Dog Food"

price
   ↓
1200
```

Variable ni oka container/box laga imagine cheyachu.

```text
Variable
   ↓
Stores a Value
```

Python program lo data ni future lo use cheyali ante variable lo store chestam.

---

# 2. 📝 String — `str`

String ante **text data**.

Python lo string ni quotes madhya represent chestam.

Example:

```python
product = "Dog Food"
```

Ikkada:

```text
product
   ↓
"Dog Food"
   ↓
String
```

Another example:

```python
name = "Durga Vamsi"
```

Here:

```text
"Durga Vamsi"
      ↓
    String
```

### 💻 Example

```python
product = "Dog Food"

print(product)
```

### 📊 Output

```text
Dog Food
```

### 🧠 Key Point

```text
str
 ↓
Text
```

Examples:

```python
"Dog Food"
"Cat Food"
"Life Care Pet Zone"
"Python"
```

All of these are strings.

---

# 3. 🔢 Integer — `int`

Integer ante **whole numbers**.

Decimal values lekunda unde numbers ni integer antam.

Examples:

```python
quantity = 2
price = 1200
stock = 50
```

Ikkada:

```text
2
1200
50
```

are integers.

### 💻 Example

```python
quantity = 2

print(quantity)
```

### 📊 Output

```text
2
```

### 🧠 Key Point

```text
int
 ↓
Whole Numbers
```

Examples:

```text
1
2
10
50
100
1200
```

---

# 4. 🔢 Float — `float`

Float ante **decimal numbers**.

Decimal point unna numbers ni float ga represent chestam.

Example:

```python
price = 1200.50
```

Ikkada:

```text
1200.50
   ↓
 Float
```

### 💻 Example

```python
price = 1200.50

print(price)
```

### 📊 Output

```text
1200.5
```

Python decimal value ni float ga handle chestundi.

### 🧠 Key Point

```text
float
  ↓
Decimal Numbers
```

Examples:

```text
10.5
25.75
1200.50
99.99
```

---

# 5. ✅ Boolean — `bool`

Boolean ante **True or False** values.

Python lo Boolean ki two possible values untayi:

```python
True
False
```

Example:

```python
available = True
```

Ikkada:

```text
available
    ↓
 True
    ↓
 Boolean
```

Another example:

```python
available = False
```

### 💻 Example

```python
available = True

print(available)
```

### 📊 Output

```text
True
```

### 🧠 Key Point

```text
bool
 ↓
True / False
```

Boolean values future lo conditions and decision making lo chala useful.

---

# 6. 🔄 Variable Assignment

Variable ki value assign cheyadam ni **variable assignment** antam.

Example:

```python
product = "Dog Food"
quantity = 2
price = 1200.50
available = True
```

Ikkada different variables ki different types of values assign chesam.

```text
product
   ↓
"Dog Food"
   ↓
str


quantity
   ↓
2
   ↓
int


price
   ↓
1200.50
   ↓
float


available
   ↓
True
   ↓
bool
```

---

# 7. 🧩 Different Data Types in One Program

Python lo same program lo different data types use cheyachu.

Example:

```python
product = "Dog Food"
quantity = 2
price = 1200.50
available = True
```

Ikkada:

```text
product   → String
quantity  → Integer
price     → Float
available → Boolean
```

This is important because real-world data different forms lo untundi.

---

# 💻 Day 02 Complete Example

```python
product = "Dog Food"
quantity = 2
price = 1200.50
available = True

print(product)
print(quantity)
print(price)
print(available)
```

### 📊 Output

```text
Dog Food
2
1200.5
True
```

---

# 🔍 Understanding the Complete Example

## Step 1 — Product

```python
product = "Dog Food"
```

`"Dog Food"` text kabatti idi:

```text
String
```

---

## Step 2 — Quantity

```python
quantity = 2
```

`2` whole number kabatti idi:

```text
Integer
```

---

## Step 3 — Price

```python
price = 1200.50
```

`1200.50` decimal number kabatti idi:

```text
Float
```

---

## Step 4 — Availability

```python
available = True
```

`True` Boolean value kabatti idi:

```text
Boolean
```

---

# 🧠 Data Types

Python lo Day 02 lo practice chesina main data types:

| Data Type | Python | Meaning | Example |
|---|---|---|---|
| String | `str` | Text | `"Dog Food"` |
| Integer | `int` | Whole Number | `2` |
| Float | `float` | Decimal Number | `1200.50` |
| Boolean | `bool` | True or False | `True` |

---

# 📝 String — `str`

String is used for text.

```python
product = "Dog Food"
```

More examples:

```python
name = "Durga"
shop = "Life Care Pet Zone"
city = "Anantapur"
```

### Structure

```text
String
  ↓
Text
  ↓
Written inside quotes
```

Example:

```python
"Python"
```

---

# 🔢 Integer — `int`

Integer is used for whole numbers.

```python
quantity = 2
```

More examples:

```python
quantity = 5
stock = 100
price = 1200
```

### Structure

```text
Integer
   ↓
Whole Number
   ↓
No Decimal Point
```

---

# 🔢 Float — `float`

Float is used for decimal numbers.

```python
price = 1200.50
```

More examples:

```python
price = 99.99
weight = 2.5
rating = 4.5
```

### Structure

```text
Float
  ↓
Decimal Number
  ↓
Contains Decimal Point
```

---

# ✅ Boolean — `bool`

Boolean represents True or False.

Example:

```python
available = True
```

Another example:

```python
out_of_stock = False
```

### Structure

```text
Boolean
   ↓
True / False
```

Boolean values are very useful when a program needs to represent a yes/no type situation.

---

# 🐾 Real-World Pet Shop Example

Pet Shop product information ni different data types tho represent cheyachu.

```python
product = "Dog Food"
quantity = 2
price = 1200.50
available = True
```

Data structure:

```text
Product
   ↓
"Dog Food"
   ↓
String


Quantity
   ↓
2
   ↓
Integer


Price
   ↓
1200.50
   ↓
Float


Available
   ↓
True
   ↓
Boolean
```

---

# 💻 Life Care Pet Zone Example

```python
product = "Dog Food"
quantity = 2
price = 1200.50
available = True

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
print("Available:", available)
```

### 📊 Output

```text
Product: Dog Food
Quantity: 2
Price: 1200.5
Available: True
```

---

# 🧠 Why Data Types Are Important

Different data ni different ways lo process cheyali.

Example:

```text
Product Name
     ↓
String

Quantity
     ↓
Integer

Price
     ↓
Float

Available
     ↓
Boolean
```

Correct data type use cheyadam valla program data ni correct ga handle cheyagalugutundi.

---

# 🔄 Variable + Data Type Relationship

Example:

```python
product = "Dog Food"
```

```text
Variable
   ↓
product

Value
   ↓
"Dog Food"

Data Type
   ↓
str
```

Another example:

```python
quantity = 2
```

```text
Variable
   ↓
quantity

Value
   ↓
2

Data Type
   ↓
int
```

Another example:

```python
price = 1200.50
```

```text
Variable
   ↓
price

Value
   ↓
1200.50

Data Type
   ↓
float
```

Another example:

```python
available = True
```

```text
Variable
   ↓
available

Value
   ↓
True

Data Type
   ↓
bool
```

---

# 🔍 Data Type Identification

Given values:

```python
"Dog Food"
2
1200.50
True
```

Their types are:

```text
"Dog Food" → str
2           → int
1200.50     → float
True        → bool
```

---

# 💻 Day 02 Practice Program

```python
# Product Information

product = "Dog Food"
quantity = 2
price = 1200.50
available = True

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
print("Available:", available)
```

### 📊 Output

```text
Product: Dog Food
Quantity: 2
Price: 1200.5
Available: True
```

---

# 🎯 Day 02 Practice Tasks

## Practice Task 1 — String

```python
product = "Dog Food"

print(product)
```

### Output

```text
Dog Food
```

---

## Practice Task 2 — Integer

```python
quantity = 5

print(quantity)
```

### Output

```text
5
```

---

## Practice Task 3 — Float

```python
price = 1200.50

print(price)
```

### Output

```text
1200.5
```

---

## Practice Task 4 — Boolean

```python
available = True

print(available)
```

### Output

```text
True
```

---

## Practice Task 5 — All Data Types

```python
product = "Cat Food"
quantity = 3
price = 900.50
available = True

print(product)
print(quantity)
print(price)
print(available)
```

### Output

```text
Cat Food
3
900.5
True
```

---

# 🧪 Practice Challenge

Create variables for a pet product using all four data types.

```python
product = "Dog Food"
quantity = 2
price = 1200.50
available = True

print("Product:", product)
print("Quantity:", quantity)
print("Price:", price)
print("Available:", available)
```

### Expected Output

```text
Product: Dog Food
Quantity: 2
Price: 1200.5
Available: True
```

---

# 🧠 Important Concepts to Remember

## `str`

```python
product = "Dog Food"
```

Used for text.

---

## `int`

```python
quantity = 2
```

Used for whole numbers.

---

## `float`

```python
price = 1200.50
```

Used for decimal numbers.

---

## `bool`

```python
available = True
```

Used for True/False values.

---

# 📚 Day 02 Key Notes

```text
str
 ↓
Text
 ↓
"Dog Food"


int
 ↓
Whole Number
 ↓
2


float
 ↓
Decimal Number
 ↓
1200.50


bool
 ↓
True / False
 ↓
True
```

---

# 🐾 Real-World Data Structure

A real product can contain different types of information.

```text
Product
│
├── Name
│      ↓
│    String
│
├── Quantity
│      ↓
│    Integer
│
├── Price
│      ↓
│    Float
│
└── Available
       ↓
     Boolean
```

Python representation:

```python
product = "Dog Food"
quantity = 2
price = 1200.50
available = True
```

---

# 💭 My Day 02 Learning

Day 02 lo nenu Python lo different types of data untayi ani understand chesanu.

Text information kosam `str`, whole numbers kosam `int`, decimal numbers kosam `float`, and True/False information kosam `bool` use chestam ani nerchukunnanu.

Variables lo different data types values ni store chesi, `print()` function tho output display cheyadam practice chesanu.

Real-world example ga Pet Shop products ni use chesi product name, quantity, price, availability information ni different data types tho represent chesanu.

---

# 📝 What I Learned — Day 02

I learned that variables can store different types of data in Python.

I learned:

```text
str   → Text
int   → Whole Numbers
float → Decimal Numbers
bool  → True / False
```

I also learned how to assign these values to variables and display them using `print()`.

Day 02 helped me understand that choosing the correct data type is important when working with real-world data.

---

# 🏆 Day 02 Achievement

By completing Day 02, I learned:

- ✅ String (`str`)
- ✅ Integer (`int`)
- ✅ Float (`float`)
- ✅ Boolean (`bool`)
- ✅ Variable assignment
- ✅ Storing different data types
- ✅ Printing different data types
- ✅ Understanding text values
- ✅ Understanding whole numbers
- ✅ Understanding decimal numbers
- ✅ Understanding True/False values
- ✅ Real-world product data practice

---

# 🎯 Day 02 Summary

```text
Day 02
   ↓
Variables
   ↓
Different Data Types
   ↓
String
   ↓
Integer
   ↓
Float
   ↓
Boolean
   ↓
Store Different Values
   ↓
Print Values
   ↓
Real-World Practice
```

---

# 📈 Learning Progress

```text
Day 01
Python Basics
   ↓
Day 02
Variables & Data Types
   ↓
Day 03
Input & Type Conversion
```

---

# 🚀 Next Step

## 📅 Day 03 — Input & Type Conversion

In Day 03, I will learn:

- `input()`
- `int()`
- `float()`
- User input
- Type conversion

I will practice taking information from the user and converting the input into the required data type.

---

# 🐍 Python Learning Journey

**Day 02 → Completed ✅**

> **Learn → Practice → Make Mistakes → Understand → Improve.** 🚀