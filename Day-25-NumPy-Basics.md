# 🐍 DAY 25 — NumPy Basics

## 📚 Python Learning Journey

**Goal:** Python → Data Engineering

Day 25 nundi manam Python nundi **Data Science & Data Engineering side** ki important step start chestunnam.

Ippativaraku manam Python fundamentals and practical programming concepts nerchukunnam.

Now we are starting:

> **NumPy — Numerical Python**

NumPy is especially useful for working with **arrays, numerical data, mathematical calculations, and efficient data processing**.

---

# 🎯 Day 25 Learning Objectives

Day 25 complete ayyaka nenu:

- NumPy ante enti?
- NumPy enduku use chestam?
- NumPy install/import ela cheyyali?
- NumPy array ante enti?
- Python list vs NumPy array
- 1D arrays
- 2D arrays
- Array indexing
- Array slicing
- Array shape
- Array size
- Array dimensions
- Array data type
- Mathematical operations
- `sum()`
- `mean()`
- `max()`
- `min()`
- `zeros()`
- `ones()`
- `arange()`

laanti basics understand cheskuntanu.

---

# 1️⃣ NumPy Ante Enti?

NumPy stands for:

> **Numerical Python**

NumPy is a Python library designed mainly for numerical and array-based operations.

Simple ga:

```text
Python List
     ↓
General-purpose collection

NumPy Array
     ↓
Efficient numerical data processing
```

Data-related work lo large amounts of numerical data process cheyyadaniki NumPy useful.

---

# 2️⃣ NumPy Enduku Learn Cheyyali?

Manam Python lists tho numbers process cheyyachu.

Example:

```python
prices = [100, 200, 300, 400]
```

But numerical data ekkuva unte efficient array operations important avutayi.

NumPy tho:

```python
import numpy as np

prices = np.array([100, 200, 300, 400])
```

Array meeda mathematical operations easy ga perform cheyyachu.

---

# 3️⃣ NumPy Import

NumPy ni import cheyyadaniki:

```python
import numpy as np
```

Ikkada:

```text
numpy → library name
np → commonly used alias
```

Then:

```python
np.array()
```

use cheyyachu.

---

# 4️⃣ Creating a NumPy Array

```python
import numpy as np

prices = np.array([100, 200, 300, 400])

print(prices)
```

### Output

```text
[100 200 300 400]
```

Ikkada:

```text
prices
```

is a NumPy array.

---

# 5️⃣ Checking Array Type

```python
import numpy as np

prices = np.array([100, 200, 300, 400])

print(type(prices))
```

### Output

```text
<class 'numpy.ndarray'>
```

`ndarray` means:

> N-dimensional array.

---

# 6️⃣ Python List vs NumPy Array

### Python List

```python
prices = [100, 200, 300, 400]
```

### NumPy Array

```python
prices = np.array([100, 200, 300, 400])
```

Conceptually:

```text
List
→ General Python collection

NumPy Array
→ Numerical/array-oriented data structure
```

---

# 7️⃣ 1D NumPy Array

One-dimensional array simple sequence laga untundi.

```python
import numpy as np

prices = np.array([100, 200, 300, 400])

print(prices)
```

Structure:

```text
[100 200 300 400]
```

Idi:

```text
1 Dimension
```

---

# 8️⃣ 2D NumPy Array

Rows and columns form lo data represent cheyyachu.

```python
import numpy as np

sales = np.array([
    [100, 200, 300],
    [400, 500, 600]
])

print(sales)
```

### Output

```text
[[100 200 300]
 [400 500 600]]
```

Structure:

```text
Row 1 → 100 200 300
Row 2 → 400 500 600
```

Idi **2D array**.

---

# 9️⃣ 3D Array — Basic Idea

NumPy multiple dimensions support chestundi.

Conceptually:

```text
1D → [1, 2, 3]

2D →
[
 [1, 2],
 [3, 4]
]

3D →
Multiple 2D arrays
```

Day 25 lo mainly 1D and 2D arrays meeda focus chestam.

---

# 🔟 Array Indexing

Python lists laga NumPy arrays kuda indexing use chestayi.

```python
import numpy as np

prices = np.array([100, 200, 300, 400])
```

First element:

```python
print(prices[0])
```

### Output

```text
100
```

Second:

```python
print(prices[1])
```

Output:

```text
200
```

---

# 1️⃣1️⃣ Negative Indexing

Last element access:

```python
print(prices[-1])
```

### Output

```text
400
```

Second-last:

```python
print(prices[-2])
```

### Output

```text
300
```

---

# 1️⃣2️⃣ Array Slicing

Array lo part of data select cheyyachu.

```python
prices = np.array([100, 200, 300, 400, 500])
```

Example:

```python
print(prices[1:4])
```

### Output

```text
[200 300 400]
```

Meaning:

```text
Start → index 1
Stop → index 4
```

Index 4 include avvadu.

---

# 1️⃣3️⃣ First Three Elements

```python
print(prices[:3])
```

Output:

```text
[100 200 300]
```

---

# 1️⃣4️⃣ From Index 2

```python
print(prices[2:])
```

Output:

```text
[300 400 500]
```

---

# 1️⃣5️⃣ Array Shape

Array lo rows and columns enni unnayo `shape` tho telusukovachu.

```python
sales = np.array([
    [100, 200, 300],
    [400, 500, 600]
])

print(sales.shape)
```

### Output

```text
(2, 3)
```

Meaning:

```text
2 rows
3 columns
```

---

# 1️⃣6️⃣ Array Dimensions

Use:

```python
print(sales.ndim)
```

### Output

```text
2
```

Meaning:

```text
2-dimensional array
```

For 1D:

```python
prices = np.array([100, 200, 300])

print(prices.ndim)
```

Output:

```text
1
```

---

# 1️⃣7️⃣ Array Size

`size` total number of elements ni return chestundi.

```python
sales = np.array([
    [100, 200, 300],
    [400, 500, 600]
])

print(sales.size)
```

### Output

```text
6
```

Because:

```text
2 rows × 3 columns = 6 elements
```

---

# 1️⃣8️⃣ Array Data Type

Use:

```python
prices = np.array([100, 200, 300])

print(prices.dtype)
```

Output integer type laga untundi, environment/platform batti exact dtype vary avvachu.

Example:

```text
int64
```

---

# 1️⃣9️⃣ Array of Floats

```python
prices = np.array([100.5, 200.5, 300.5])

print(prices)
print(prices.dtype)
```

Floating-point data type use avutundi.

---

# 2️⃣0️⃣ Mathematical Operations

NumPy arrays tho mathematical operations simple ga perform cheyyachu.

```python
import numpy as np

prices = np.array([100, 200, 300])
```

Add:

```python
print(prices + 10)
```

Output:

```text
[110 210 310]
```

Each element ki `10` add avutundi.

---

# 2️⃣1️⃣ Subtraction

```python
print(prices - 10)
```

Output:

```text
[ 90 190 290]
```

---

# 2️⃣2️⃣ Multiplication

```python
print(prices * 2)
```

Output:

```text
[200 400 600]
```

---

# 2️⃣3️⃣ Division

```python
print(prices / 2)
```

Output:

```text
[ 50. 100. 150.]
```

---

# 2️⃣4️⃣ Array + Array

Two arrays ni element-wise add cheyyachu.

```python
a = np.array([10, 20, 30])
b = np.array([1, 2, 3])

print(a + b)
```

### Output

```text
[11 22 33]
```

Calculation:

```text
10 + 1 = 11
20 + 2 = 22
30 + 3 = 33
```

---

# 2️⃣5️⃣ Array Multiplication

```python
a = np.array([10, 20, 30])
b = np.array([2, 3, 4])

print(a * b)
```

### Output

```text
[ 20  60 120]
```

---

# 2️⃣6️⃣ Sum

NumPy array values total calculate cheyyadaniki:

```python
prices = np.array([100, 200, 300, 400])

print(np.sum(prices))
```

### Output

```text
1000
```

---

# 2️⃣7️⃣ Mean

Average calculate cheyyadaniki:

```python
prices = np.array([100, 200, 300, 400])

print(np.mean(prices))
```

### Output

```text
250.0
```

Calculation:

```text
(100 + 200 + 300 + 400) / 4

= 250
```

---

# 2️⃣8️⃣ Maximum

Highest value:

```python
prices = np.array([100, 500, 200, 300])

print(np.max(prices))
```

### Output

```text
500
```

---

# 2️⃣9️⃣ Minimum

Lowest value:

```python
prices = np.array([100, 500, 200, 300])

print(np.min(prices))
```

### Output

```text
100
```

---

# 3️⃣0️⃣ Standard Deviation — Basic Introduction

NumPy statistical calculations kuda support chestundi.

Example:

```python
sales = np.array([100, 200, 300, 400])

print(np.std(sales))
```

`std` means:

> Standard deviation

It gives an idea about how spread out values are.

Day 25 lo basic introduction matrame; deep statistics later practice cheyyachu.

---

# 3️⃣1️⃣ Creating Zeros

`np.zeros()` use chesi zeros array create cheyyachu.

```python
zeros = np.zeros(5)

print(zeros)
```

Output:

```text
[0. 0. 0. 0. 0.]
```

5 elements.

---

# 3️⃣2️⃣ Creating Ones

```python
ones = np.ones(5)

print(ones)
```

Output:

```text
[1. 1. 1. 1. 1.]
```

---

# 3️⃣3️⃣ 2D Zeros Array

```python
matrix = np.zeros((2, 3))

print(matrix)
```

Output:

```text
[[0. 0. 0.]
 [0. 0. 0.]]
```

Meaning:

```text
2 rows
3 columns
```

---

# 3️⃣4️⃣ 2D Ones Array

```python
matrix = np.ones((2, 3))

print(matrix)
```

Output:

```text
[[1. 1. 1.]
 [1. 1. 1.]]
```

---

# 3️⃣5️⃣ `np.arange()`

Range-like numerical array create cheyyadaniki:

```python
numbers = np.arange(1, 6)

print(numbers)
```

### Output

```text
[1 2 3 4 5]
```

Important:

```python
np.arange(start, stop)
```

Stop value include avvadu.

---

# 3️⃣6️⃣ `arange()` With Step

```python
numbers = np.arange(0, 11, 2)

print(numbers)
```

### Output

```text
[ 0  2  4  6  8 10]
```

Meaning:

```text
Start = 0
Stop = 11
Step = 2
```

---

# 3️⃣7️⃣ `reshape()`

1D array ni different shape lo arrange cheyyachu.

```python
numbers = np.arange(1, 7)

matrix = numbers.reshape(2, 3)

print(matrix)
```

### Output

```text
[[1 2 3]
 [4 5 6]]
```

Original:

```text
[1 2 3 4 5 6]
```

After reshape:

```text
2 rows × 3 columns
```

---

# 3️⃣8️⃣ Reshape Important Rule

Number of elements same undali.

Example:

```text
6 elements
```

can become:

```text
2 × 3
```

or:

```text
3 × 2
```

But:

```text
2 × 4
```

possible kaadu because:

```text
2 × 4 = 8
```

and we only have 6 elements.

---

# 3️⃣9️⃣ 2D Array Indexing

Example:

```python
sales = np.array([
    [100, 200, 300],
    [400, 500, 600]
])
```

First row:

```python
print(sales[0])
```

Output:

```text
[100 200 300]
```

Second row:

```python
print(sales[1])
```

Output:

```text
[400 500 600]
```

---

# 4️⃣0️⃣ Access Specific 2D Element

```python
print(sales[0, 1])
```

Output:

```text
200
```

Meaning:

```text
Row = 0
Column = 1
```

Another:

```python
print(sales[1, 2])
```

Output:

```text
600
```

---

# 4️⃣1️⃣ 2D Array Slicing

```python
sales = np.array([
    [100, 200, 300],
    [400, 500, 600]
])
```

First column:

```python
print(sales[:, 0])
```

Output:

```text
[100 400]
```

Second column:

```python
print(sales[:, 1])
```

Output:

```text
[200 500]
```

---

# 4️⃣2️⃣ Array Comparison

NumPy arrays tho conditions apply cheyyachu.

```python
prices = np.array([500, 1200, 800, 1500])

print(prices >= 1000)
```

### Output

```text
[False  True False  True]
```

Each value ki condition check avutundi.

---

# 4️⃣3️⃣ Filtering Using Boolean Mask

```python
prices = np.array([500, 1200, 800, 1500])

expensive = prices[prices >= 1000]

print(expensive)
```

### Output

```text
[1200 1500]
```

Idi data analysis lo chala useful concept.

---

# 4️⃣4️⃣ Pet Shop Example

Suppose prices:

```python
prices = np.array([
    1200,
    900,
    300,
    500,
    1100
])
```

Average price:

```python
average_price = np.mean(prices)

print(average_price)
```

Output:

```text
800.0
```

Highest:

```python
print(np.max(prices))
```

Output:

```text
1200
```

Lowest:

```python
print(np.min(prices))
```

Output:

```text
300
```

---

# 4️⃣5️⃣ Pet Shop Sales Data

```python
sales = np.array([
    2400,
    2700,
    1500,
    2000,
    6600
])
```

Total sales:

```python
print(np.sum(sales))
```

Output:

```text
15200
```

Average sales:

```python
print(np.mean(sales))
```

Output:

```text
3040.0
```

Highest sales:

```python
print(np.max(sales))
```

Output:

```text
6600
```

Lowest sales:

```python
print(np.min(sales))
```

Output:

```text
1500
```

---

# 4️⃣6️⃣ NumPy + Business Analysis

Mana Pet Shop data:

```text
Product Revenue
```

can be represented as:

```python
sales = np.array([
    2400,
    2700,
    1500,
    2000,
    6600
])
```

Now:

```text
Total Revenue
Average Revenue
Highest Revenue
Lowest Revenue
```

easy ga calculate cheyyachu.

---

# 4️⃣7️⃣ NumPy + Quantity

```python
quantities = np.array([
    2,
    3,
    5,
    4,
    6
])
```

Total stock:

```python
print(np.sum(quantities))
```

Output:

```text
20
```

Average stock:

```python
print(np.mean(quantities))
```

Output:

```text
4.0
```

Maximum stock:

```python
print(np.max(quantities))
```

Output:

```text
6
```

---

# 4️⃣8️⃣ Low Stock Filtering

Business rule:

```text
Quantity < 5
```

NumPy:

```python
quantities = np.array([2, 3, 5, 4, 6])

low_stock = quantities[quantities < 5]

print(low_stock)
```

### Output

```text
[2 3 4]
```

---

# 4️⃣9️⃣ Expensive Price Filtering

```python
prices = np.array([
    1200,
    900,
    300,
    500,
    1100
])

expensive = prices[prices >= 1000]

print(expensive)
```

### Output

```text
[1200 1100]
```

---

# 5️⃣0️⃣ NumPy and Vectorized Operations

One important NumPy idea:

> Array operations can be applied to many values at once.

Example:

```python
prices = np.array([100, 200, 300])

new_prices = prices * 2

print(new_prices)
```

Output:

```text
[200 400 600]
```

Instead of manually looping through every element, NumPy can perform the operation across the array.

This style is called **vectorized operation**.

---

# 5️⃣1️⃣ Python Loop vs NumPy

### Python

```python
prices = [100, 200, 300]

new_prices = []

for price in prices:

    new_prices.append(price * 2)

print(new_prices)
```

### NumPy

```python
import numpy as np

prices = np.array([100, 200, 300])

new_prices = prices * 2

print(new_prices)
```

Both produce the same conceptual result:

```text
[200, 400, 600]
```

NumPy makes numerical array operations concise and efficient.

---

# 5️⃣2️⃣ NumPy Array Functions Quick Reference

| Function | Purpose |
|---|---|
| `np.array()` | Create array |
| `np.zeros()` | Create zeros |
| `np.ones()` | Create ones |
| `np.arange()` | Create number sequence |
| `np.sum()` | Total |
| `np.mean()` | Average |
| `np.max()` | Maximum |
| `np.min()` | Minimum |
| `np.std()` | Standard deviation |
| `.shape` | Rows/columns shape |
| `.size` | Total elements |
| `.ndim` | Number of dimensions |
| `.dtype` | Data type |
| `.reshape()` | Change array shape |

---

# 5️⃣3️⃣ Practice Task 1 — Create Array

Create:

```python
prices = np.array([
    1200,
    900,
    300,
    500,
    1100
])
```

Find:

```text
Maximum
Minimum
Average
Total
```

---

# 5️⃣4️⃣ Practice Task 2 — Quantity Analysis

Create:

```python
quantities = np.array([
    2,
    3,
    5,
    4,
    6
])
```

Find:

```text
Total Stock
Average Stock
Maximum Stock
Minimum Stock
```

---

# 5️⃣5️⃣ Practice Task 3 — Filtering

Using prices:

```python
prices = np.array([
    1200,
    900,
    300,
    500,
    1100
])
```

Find prices:

```text
>= 1000
```

Expected:

```text
[1200 1100]
```

---

# 5️⃣6️⃣ Practice Task 4 — Low Stock

Using:

```python
quantities = np.array([
    2,
    3,
    5,
    4,
    6
])
```

Find:

```text
Quantity < 5
```

Expected:

```text
[2 3 4]
```

---

# 5️⃣7️⃣ Practice Task 5 — Sales Analysis

Create:

```python
sales = np.array([
    2400,
    2700,
    1500,
    2000,
    6600
])
```

Calculate:

```text
Total Revenue
Average Revenue
Highest Revenue
Lowest Revenue
```

---

# 5️⃣8️⃣ Practice Task 6 — Reshape

Create:

```python
numbers = np.arange(1, 13)
```

Convert into:

```text
3 rows
4 columns
```

Expected:

```text
[[ 1  2  3  4]
 [ 5  6  7  8]
 [ 9 10 11 12]]
```

---

# 5️⃣9️⃣ Day 25 Mini Project

## 🐾 Pet Shop Numerical Data Analysis

Create NumPy arrays for:

```text
Prices
Quantities
Revenue
```

Example:

```python
prices = np.array([
    1200,
    900,
    300,
    500,
    1100
])

quantities = np.array([
    2,
    3,
    5,
    4,
    6
])

revenue = prices * quantities
```

Then calculate:

```text
1. Total Revenue
2. Average Revenue
3. Highest Revenue
4. Lowest Revenue
5. Total Stock
6. Average Stock
7. Low Stock Quantities
8. Expensive Prices
```

---

# 6️⃣0️⃣ Mini Project Solution

```python
import numpy as np

prices = np.array([
    1200,
    900,
    300,
    500,
    1100
])

quantities = np.array([
    2,
    3,
    5,
    4,
    6
])

revenue = prices * quantities


print("Prices:", prices)

print("Quantities:", quantities)

print("Revenue:", revenue)

print("Total Revenue:", np.sum(revenue))

print("Average Revenue:", np.mean(revenue))

print("Highest Revenue:", np.max(revenue))

print("Lowest Revenue:", np.min(revenue))

print("Total Stock:", np.sum(quantities))

print("Average Stock:", np.mean(quantities))

print("Low Stock:", quantities[quantities < 5])

print("Expensive Prices:", prices[prices >= 1000])
```

### Expected Output

```text
Prices: [1200  900  300  500 1100]

Quantities: [2 3 5 4 6]

Revenue: [2400 2700 1500 2000 6600]

Total Revenue: 15200

Average Revenue: 3040.0

Highest Revenue: 6600

Lowest Revenue: 1500

Total Stock: 20

Average Stock: 4.0

Low Stock: [2 3 4]

Expensive Prices: [1200 1100]
```

---

# 6️⃣1️⃣ Data Engineering Connection

NumPy is an important numerical computing foundation.

Data-related workflow:

```text
Raw Data
   ↓
Python
   ↓
NumPy
   ↓
Numerical Processing
   ↓
Pandas
   ↓
Data Cleaning
   ↓
Data Analysis
   ↓
SQL
   ↓
Data Engineering
```

NumPy concepts will also help understand how numerical data is represented and processed efficiently.

---

# 6️⃣2️⃣ Why NumPy Before Pandas?

Next stages lo manam Pandas nerchukuntam.

Pandas internally works heavily with array-based numerical structures.

So first:

```text
NumPy Basics
```

understand cheskunte later:

```text
Pandas
```

concepts easier ga understand cheyyachu.

---

# 6️⃣3️⃣ Common Mistakes

## ❌ Mistake 1 — Forgetting Import

Wrong:

```python
prices = np.array([100, 200, 300])
```

without:

```python
import numpy as np
```

Correct:

```python
import numpy as np

prices = np.array([100, 200, 300])
```

---

## ❌ Mistake 2 — Wrong Shape

If array has 6 elements:

```python
np.arange(1, 7)
```

then:

```python
reshape(2, 3)
```

works.

But:

```python
reshape(2, 4)
```

does not work because 8 positions are required.

---

## ❌ Mistake 3 — Confusing `size` and `shape`

```python
array.shape
```

→ structure

```text
(2, 3)
```

```python
array.size
```

→ total elements

```text
6
```

---

# 🧠 Day 25 Key Concepts

Remember:

```text
NumPy
   ↓
Numerical Python
```

```text
np.array()
   ↓
Create Array
```

```text
.shape
   ↓
Array Shape
```

```text
.ndim
   ↓
Number of Dimensions
```

```text
.size
   ↓
Number of Elements
```

```text
np.sum()
   ↓
Total
```

```text
np.mean()
   ↓
Average
```

```text
np.max()
   ↓
Maximum
```

```text
np.min()
   ↓
Minimum
```

```text
np.arange()
   ↓
Number Sequence
```

```text
.reshape()
   ↓
Change Shape
```

---

# 📝 Day 25 Practice Checklist

- [ ] Understand NumPy
- [ ] Import NumPy
- [ ] Create NumPy array
- [ ] Understand 1D array
- [ ] Understand 2D array
- [ ] Practice indexing
- [ ] Practice slicing
- [ ] Understand `shape`
- [ ] Understand `size`
- [ ] Understand `ndim`
- [ ] Understand `dtype`
- [ ] Practice arithmetic operations
- [ ] Practice `sum()`
- [ ] Practice `mean()`
- [ ] Practice `max()`
- [ ] Practice `min()`
- [ ] Practice `zeros()`
- [ ] Practice `ones()`
- [ ] Practice `arange()`
- [ ] Practice `reshape()`
- [ ] Practice boolean filtering
- [ ] Complete Pet Shop NumPy Mini Project

---

# 📌 Day 25 Summary

Today I started learning **NumPy**, an important Python library for numerical and array-based data processing.

I learned:

```text
NumPy Arrays
1D Arrays
2D Arrays
Indexing
Slicing
Shape
Size
Dimensions
Data Types
Arithmetic Operations
Sum
Mean
Maximum
Minimum
Zeros
Ones
Arange
Reshape
Boolean Filtering
Vectorized Operations
```

I also applied NumPy to a **Life Care Pet Zone Pet Shop numerical analysis** example.

This gives me a foundation for the next stage of my journey:

```text
NumPy
   ↓
Pandas
   ↓
Data Cleaning
   ↓
Data Analysis
   ↓
SQL
   ↓
Data Engineering
```

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
Day 23 → OOP + Data Processing
Day 24 → Python Mini Project
Day 25 → NumPy Basics
```

---

# 🎯 Next Day

## DAY 26 — NumPy Array Operations & Data Analysis

Next I will go deeper into NumPy:

```text
Array Operations
Broadcasting
Axis
Aggregation
Boolean Filtering
Multiple Conditions
Sorting
Random Data
2D Data Analysis
Practical Numerical Analysis
```

This will prepare me for **Pandas Basics**.

---

# 👨‍💻 Developed By

## Durga Vamsi

**Python → Data Engineering Learning Journey** 🐍🚀