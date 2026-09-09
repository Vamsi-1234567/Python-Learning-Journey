# 🐍 DAY 18 — File Handling

## 📌 Day 18 Goal

Today we will learn **File Handling in Python**.

Until Day 17, we worked mostly with data directly inside Python programs.

But in real-world applications and Data Engineering, data is often stored in files.

For example:

```text
products.txt
sales.csv
customers.csv
products.json
sales_data.csv
```

Python can read data from files, write data to files, and process the information.

Today we will learn:

- What is File Handling?
- Opening a file
- `open()`
- Reading files
- `read()`
- `readline()`
- `readlines()`
- Writing files
- `write()`
- Append mode
- File modes
- `with open()`
- Exception handling with files
- Product/business examples
- Data Engineering connection

---

# 1️⃣ What is File Handling?

**File Handling** means using Python to work with files.

We can:

```text
Create
Read
Write
Append
Process
```

files using Python.

Example:

```text
Python Program
      ↓
    File
      ↓
 Product Data
```

Instead of keeping everything inside Python code, we can store the data in external files.

---

# 2️⃣ Why File Handling is Important?

In real-world Data Engineering, data may come from:

- CSV files
- Text files
- JSON files
- Log files
- Database exports
- API responses

For example:

```text
sales.csv
```

may contain:

```text
Product,Price,Quantity
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
```

Python can read and process this data.

---

# 3️⃣ `open()` Function

Python provides:

```python
open()
```

to open a file.

Basic syntax:

```python
open("filename", "mode")
```

Example:

```python
file = open("products.txt", "r")
```

Here:

```text
products.txt → File name
r             → Read mode
```

---

# 4️⃣ File Modes

Important file modes:

| Mode | Purpose |
|---|---|
| `r` | Read |
| `w` | Write |
| `a` | Append |
| `x` | Create new file |

The most important modes for now are:

```text
r → Read
w → Write
a → Append
```

---

# 5️⃣ Reading a File

Suppose we have:

```text
products.txt
```

containing:

```text
Dog Food
Cat Food
Treats
Bones
```

Python code:

```python
file = open("products.txt", "r")

content = file.read()

print(content)

file.close()
```

### Output

```text
Dog Food
Cat Food
Treats
Bones
```

---

# 6️⃣ `read()`

The `read()` method reads the entire file.

```python
file = open("products.txt", "r")

data = file.read()

print(data)

file.close()
```

`read()` means:

```text
Read complete file
```

---

# 7️⃣ Why `close()`?

After opening a file, we should close it.

```python
file.close()
```

Example:

```python
file = open("products.txt", "r")

data = file.read()

print(data)

file.close()
```

Closing the file releases the resources used by the file.

---

# 8️⃣ Using `with open()`

A better approach is:

```python
with open("products.txt", "r") as file:
    data = file.read()

print(data)
```

This is preferred because Python automatically handles closing the file.

So instead of:

```python
file = open(...)
...
file.close()
```

we can use:

```python
with open(...) as file:
    ...
```

---

# 9️⃣ Reading File Line by Line

We can loop through a file.

```python
with open("products.txt", "r") as file:

    for line in file:
        print(line)
```

Each line is processed one at a time.

This is useful when working with larger files.

---

# 🔟 Removing Extra Newline

When reading lines, the line may contain `\n`.

We can use:

```python
strip()
```

Example:

```python
with open("products.txt", "r") as file:

    for line in file:
        print(line.strip())
```

Now the output is cleaner.

---

# 1️⃣1️⃣ `readline()`

`readline()` reads one line at a time.

Example:

```python
with open("products.txt", "r") as file:

    line = file.readline()

    print(line)
```

If the file contains:

```text
Dog Food
Cat Food
Treats
Bones
```

the first call reads:

```text
Dog Food
```

---

# 1️⃣2️⃣ Multiple `readline()` Calls

```python
with open("products.txt", "r") as file:

    line1 = file.readline()
    line2 = file.readline()

    print(line1)
    print(line2)
```

Output:

```text
Dog Food
Cat Food
```

---

# 1️⃣3️⃣ `readlines()`

`readlines()` reads all lines and returns them as a list.

```python
with open("products.txt", "r") as file:

    lines = file.readlines()

print(lines)
```

Output:

```text
['Dog Food\n', 'Cat Food\n', 'Treats\n', 'Bones\n']
```

We can remove the newline characters:

```python
with open("products.txt", "r") as file:

    lines = [
        line.strip()
        for line in file.readlines()
    ]

print(lines)
```

Output:

```text
['Dog Food', 'Cat Food', 'Treats', 'Bones']
```

---

# 1️⃣4️⃣ Writing to a File

Use:

```python
w
```

mode.

Example:

```python
with open("products.txt", "w") as file:

    file.write("Dog Food\n")
    file.write("Cat Food\n")
    file.write("Treats\n")
```

The file will contain:

```text
Dog Food
Cat Food
Treats
```

---

# 1️⃣5️⃣ Important — Write Mode

Be careful with:

```python
"w"
```

Write mode can replace the existing contents of a file.

For example:

```python
with open("products.txt", "w") as file:
    file.write("Bones")
```

The previous contents may be replaced.

So remember:

```text
w → Write / replace
```

---

# 1️⃣6️⃣ Append Mode

If we want to add new information without replacing existing content, use:

```python
"a"
```

Example:

```python
with open("products.txt", "a") as file:

    file.write("\nBones")
```

If the file already contains:

```text
Dog Food
Cat Food
Treats
```

after appending:

```text
Dog Food
Cat Food
Treats
Bones
```

So:

```text
a → Add to existing content
```

---

# 1️⃣7️⃣ Writing Multiple Lines

We can use a list.

```python
products = [
    "Dog Food",
    "Cat Food",
    "Treats",
    "Bones"
]

with open("products.txt", "w") as file:

    for product in products:
        file.write(product + "\n")
```

This creates:

```text
Dog Food
Cat Food
Treats
Bones
```

---

# 1️⃣8️⃣ Reading and Processing a File

We can read a file and process each line.

```python
with open("products.txt", "r") as file:

    for product in file:

        product = product.strip()

        print("Product:", product)
```

Output:

```text
Product: Dog Food
Product: Cat Food
Product: Treats
Product: Bones
```

This is the beginning of a data-processing workflow.

---

# 1️⃣9️⃣ File Handling + List

We can read file data into a list.

```python
products = []

with open("products.txt", "r") as file:

    for line in file:

        products.append(line.strip())

print(products)
```

Output:

```text
['Dog Food', 'Cat Food', 'Treats', 'Bones']
```

Now the file data is available as a Python list.

---

# 2️⃣0️⃣ File Handling + List Comprehension

We learned List Comprehension on Day 16.

Now we can combine it with File Handling.

```python
with open("products.txt", "r") as file:

    products = [
        line.strip()
        for line in file
    ]

print(products)
```

Output:

```text
['Dog Food', 'Cat Food', 'Treats', 'Bones']
```

This connects:

```text
Day 16 → Comprehension
Day 18 → File Handling
```

---

# 2️⃣1️⃣ Writing Product Data

We can create product information.

```python
products = [
    "Dog Food,1200,2",
    "Cat Food,900,3",
    "Treats,300,5",
    "Bones,500,4"
]
```

Write it to a file:

```python
with open("products.txt", "w") as file:

    for product in products:
        file.write(product + "\n")
```

The file will contain:

```text
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
Bones,500,4
```

---

# 2️⃣2️⃣ Reading Product Data

Now read the file.

```python
with open("products.txt", "r") as file:

    for line in file:

        data = line.strip()

        print(data)
```

Output:

```text
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
Bones,500,4
```

---

# 2️⃣3️⃣ Splitting File Data

We can use:

```python
split()
```

to separate values.

Example:

```python
line = "Dog Food,1200,2"

data = line.split(",")

print(data)
```

Output:

```text
['Dog Food', '1200', '2']
```

Now:

```text
data[0] → Dog Food
data[1] → 1200
data[2] → 2
```

---

# 2️⃣4️⃣ Convert File Data to Dictionary

File data is initially text.

Example:

```text
Dog Food,1200,2
```

We can convert it into a dictionary.

```python
line = "Dog Food,1200,2"

data = line.split(",")

product = {
    "Name": data[0],
    "Price": int(data[1]),
    "Quantity": int(data[2])
}

print(product)
```

Output:

```text
{'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2}
```

This connects:

```text
File
 ↓
String
 ↓
Split
 ↓
Convert
 ↓
Dictionary
```

---

# 2️⃣5️⃣ Read Complete Product File

```python
products = []

with open("products.txt", "r") as file:

    for line in file:

        data = line.strip().split(",")

        product = {
            "Name": data[0],
            "Price": int(data[1]),
            "Quantity": int(data[2])
        }

        products.append(product)

print(products)
```

### Output

```text
[
    {'Name': 'Dog Food', 'Price': 1200, 'Quantity': 2},
    {'Name': 'Cat Food', 'Price': 900, 'Quantity': 3},
    {'Name': 'Treats', 'Price': 300, 'Quantity': 5},
    {'Name': 'Bones', 'Price': 500, 'Quantity': 4}
]
```

This is a very important step toward real data processing.

---

# 2️⃣6️⃣ Calculate Revenue from File Data

Now we can process the data.

```python
products = []

with open("products.txt", "r") as file:

    for line in file:

        data = line.strip().split(",")

        product = {
            "Name": data[0],
            "Price": int(data[1]),
            "Quantity": int(data[2])
        }

        products.append(product)


total_revenue = 0

for product in products:

    revenue = product["Price"] * product["Quantity"]

    total_revenue += revenue

    print(
        product["Name"],
        "Revenue:",
        revenue
    )


print("Total Revenue:", total_revenue)
```

### Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
Bones Revenue: 2000

Total Revenue: 8600
```

---

# 2️⃣7️⃣ Exception Handling with Files

Day 17 taught us Exception Handling.

Now we can combine it with File Handling.

```python
try:

    with open("products.txt", "r") as file:

        data = file.read()

        print(data)

except FileNotFoundError:

    print("File not found")
```

If the file does not exist:

```text
File not found
```

This prevents the program from stopping unexpectedly.

---

# 2️⃣8️⃣ File Handling + Exception Handling + Data Processing

```python
try:

    with open("products.txt", "r") as file:

        for line in file:

            data = line.strip().split(",")

            name = data[0]
            price = int(data[1])
            quantity = int(data[2])

            revenue = price * quantity

            print(name, revenue)

except FileNotFoundError:

    print("Product file does not exist")

except ValueError:

    print("Invalid product data")
```

Now we are combining:

```text
Day 12 → Dictionaries
Day 16 → Comprehensions
Day 17 → Exception Handling
Day 18 → File Handling
```

---

# 2️⃣9️⃣ Complete Day 18 Program

```python
products = [
    "Dog Food,1200,2",
    "Cat Food,900,3",
    "Treats,300,5",
    "Bones,500,4"
]


# Write product data

with open("products.txt", "w") as file:

    for product in products:
        file.write(product + "\n")


# Read and process product data

product_data = []

try:

    with open("products.txt", "r") as file:

        for line in file:

            data = line.strip().split(",")

            product = {
                "Name": data[0],
                "Price": int(data[1]),
                "Quantity": int(data[2])
            }

            product_data.append(product)


except FileNotFoundError:

    print("File not found")

except ValueError:

    print("Invalid data")


# Business Analysis

total_revenue = 0
total_stock = 0

for product in product_data:

    revenue = product["Price"] * product["Quantity"]

    total_revenue += revenue
    total_stock += product["Quantity"]

    print(
        product["Name"],
        "Revenue:",
        revenue
    )


print("Total Revenue:", total_revenue)
print("Total Stock:", total_stock)
```

### Output

```text
Dog Food Revenue: 2400
Cat Food Revenue: 2700
Treats Revenue: 1500
Bones Revenue: 2000

Total Revenue: 8600
Total Stock: 14
```

---

# 3️⃣0️⃣ Important File Methods

| Method | Purpose |
|---|---|
| `open()` | Open a file |
| `read()` | Read complete file |
| `readline()` | Read one line |
| `readlines()` | Read all lines as a list |
| `write()` | Write data |
| `close()` | Close file |
| `strip()` | Remove extra whitespace/newline |
| `split()` | Split text into parts |

---

# 3️⃣1️⃣ File Modes Quick Reference

```text
"r" → Read
"w" → Write / replace
"a" → Append
"x" → Create new file
```

Remember:

```text
r = Read
w = Write
a = Append
```

---

# 3️⃣2️⃣ Common Mistakes

### ❌ Mistake 1 — Forgetting to Close

Traditional approach:

```python
file = open("products.txt", "r")

data = file.read()

file.close()
```

Better:

```python
with open("products.txt", "r") as file:
    data = file.read()
```

---

### ❌ Mistake 2 — Using `w` When You Want to Add

Wrong:

```python
open("products.txt", "w")
```

if you want to preserve existing data.

Use:

```python
open("products.txt", "a")
```

---

### ❌ Mistake 3 — Forgetting `strip()`

File lines can contain:

```text
\n
```

Use:

```python
line.strip()
```

---

### ❌ Mistake 4 — Forgetting Type Conversion

File data is read as text.

For example:

```python
price = data[1]
```

may give:

```text
"1200"
```

Convert it:

```python
price = int(data[1])
```

---

### ❌ Mistake 5 — Missing File

If the file doesn't exist:

```python
with open("missing.txt", "r") as file:
```

Python can raise:

```text
FileNotFoundError
```

Handle it:

```python
try:

    with open("missing.txt", "r") as file:
        data = file.read()

except FileNotFoundError:

    print("File not found")
```

---

# 3️⃣3️⃣ Day 18 Practice Tasks

## 🟢 Task 1 — Create a File

Create:

```text
products.txt
```

and write:

```text
Dog Food
Cat Food
Treats
Bones
```

---

## 🟢 Task 2 — Read the File

Read the complete file using:

```python
read()
```

---

## 🟢 Task 3 — Read Line by Line

Use:

```python
for line in file:
```

and print every product.

---

## 🟢 Task 4 — Use `readline()`

Read the first two lines.

---

## 🟡 Task 5 — Use `readlines()`

Read all products into a list.

---

## 🟡 Task 6 — Append Product

Add:

```text
Shampoo
```

without deleting the existing products.

---

## 🟡 Task 7 — Product Data File

Create:

```text
Dog Food,1200,2
Cat Food,900,3
Treats,300,5
Bones,500,4
```

---

## 🟠 Task 8 — Convert to Dictionaries

Read the file and convert every row into:

```python
{
    "Name": "...",
    "Price": ...,
    "Quantity": ...
}
```

---

## 🟠 Task 9 — Calculate Revenue

Calculate:

```text
Revenue = Price × Quantity
```

for every product.

---

## 🔴 Task 10 — Mini Project

Build a **Product File Analysis Program**.

Your program should:

```text
Create File
    ↓
Write Product Data
    ↓
Read File
    ↓
Convert Data
    ↓
Create Dictionaries
    ↓
Calculate Revenue
    ↓
Calculate Total Revenue
    ↓
Calculate Total Stock
    ↓
Handle File Errors
    ↓
Display Report
```

---

# 3️⃣4️⃣ Day 17 vs Day 18

| Day | Main Concept |
|---|---|
| Day 17 | Exception Handling |
| Day 18 | File Handling |

Day 17 taught us how to handle errors:

```text
try
except
else
finally
raise
```

Day 18 teaches us how to work with external data:

```text
Open
Read
Write
Append
Process
```

Together:

```text
File
 ↓
Read
 ↓
Exception Handling
 ↓
Process
 ↓
Business Analysis
```

---

# 3️⃣5️⃣ Data Engineering Connection 🔥

File Handling is an important foundation for Data Engineering.

Real data can arrive in files such as:

```text
CSV
JSON
TXT
LOG
```

A basic Data Engineering workflow can look like:

```text
Data Source
    ↓
File
    ↓
Read Data
    ↓
Validate Data
    ↓
Handle Errors
    ↓
Transform Data
    ↓
Clean Data
    ↓
Store Data
    ↓
Analytics
```

Today you started working with data outside your Python program.

This is a major step toward:

```text
Python
   ↓
File Handling
   ↓
CSV
   ↓
JSON
   ↓
Pandas
   ↓
SQL
   ↓
ETL
   ↓
Data Pipelines
   ↓
Data Engineering 🚀
```

---

# 📌 Day 18 Summary

Today I learned:

- ✅ File Handling
- ✅ `open()`
- ✅ File modes
- ✅ Read mode
- ✅ Write mode
- ✅ Append mode
- ✅ `read()`
- ✅ `readline()`
- ✅ `readlines()`
- ✅ `write()`
- ✅ `close()`
- ✅ `with open()`
- ✅ `strip()`
- ✅ `split()`
- ✅ Reading file data
- ✅ Writing file data
- ✅ Processing file data
- ✅ Converting text into dictionaries
- ✅ File Exception Handling
- ✅ Product business analysis from file data

---

# 📈 Python Learning Progress

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
```

---

# 🚀 Next Step — Day 19

The next topic is:

## 📊 CSV Data Processing

We will move from basic text files to **CSV files**, which are very common in Data Engineering.

```text
File Handling
      ↓
CSV Files
      ↓
Rows & Columns
      ↓
CSV Data Processing
      ↓
Data Cleaning
      ↓
Pandas
      ↓
SQL
      ↓
ETL
      ↓
Data Engineering 🚀
```

---

# 👨‍💻 Developed By

## **Durga Vamsi**

🐍 Python Learning Journey  
📊 Data Engineering Goal  
🚀 Learning by Building Real-World Business Examples