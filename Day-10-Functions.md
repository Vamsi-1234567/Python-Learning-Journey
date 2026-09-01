# 📅 Day 10 — Functions

Welcome to **Day 10** of my Python Learning Journey! 🚀🐍

Today I am learning one of the most important concepts in Python:

# 🔧 Functions

Until Day 09, I wrote logic directly inside my programs.

Now I will learn how to **organize, reuse, and manage code using functions**.

Functions are very important because in real-world applications we often need to perform the same operation multiple times.

Instead of writing the same code again and again, I can create a function once and reuse it whenever I need it.

---

# 🎯 Day 10 Learning Goal

By the end of Day 10, I will understand:

- What is a function?
- Why functions are useful
- How to create a function
- `def`
- Function names
- Parameters
- Arguments
- Function calls
- `return`
- Functions with calculations
- Functions with loops
- Functions with conditions
- Reusing functions
- Business logic using functions

---

# 📚 Topics Learned

- `def`
- Creating Functions
- Function Names
- Parameters
- Arguments
- Function Calls
- `return`
- Functions with Calculations
- Functions with Loops
- Functions with Conditions
- Reusable Code
- Business Logic

---

# 🧠 1. What is a Function?

A **function** is a reusable block of code that performs a specific task.

Simple ga cheppali ante:

> Function ante oka particular task kosam create chesina reusable code block.

Example:

```python
def welcome():
    print("Welcome to Life Care Pet Zone")
```

Here:

```text
def       → Used to create a function
welcome   → Function name
()        → Parameters are written here
:         → Function body starts
```

---

# 🔧 2. Creating a Function

Basic syntax:

```python
def function_name():
    # code
```

Example:

```python
def welcome():
    print("Welcome to Life Care Pet Zone")
```

This creates the function.

But the function will not execute automatically.

We need to **call** the function.

---

# ▶️ 3. Calling a Function

```python
def welcome():
    print("Welcome to Life Care Pet Zone")

welcome()
```

### Output

```text
Welcome to Life Care Pet Zone
```

Here:

```python
welcome()
```

is the function call.

---

# 🔄 4. Function Flow

The basic function flow is:

```text
def
 ↓
Create Function
 ↓
Function Name
 ↓
Function Body
 ↓
Function Call
 ↓
Execute Code
```

Example:

```python
def welcome():
    print("Welcome")

welcome()
```

Flow:

```text
Create welcome()
      ↓
Call welcome()
      ↓
Execute print()
      ↓
Output: Welcome
```

---

# 🧠 5. Why Do We Use Functions?

Without functions:

```python
print("Welcome to Life Care Pet Zone")
print("Welcome to Life Care Pet Zone")
print("Welcome to Life Care Pet Zone")
```

We are repeating the same code.

With a function:

```python
def welcome():
    print("Welcome to Life Care Pet Zone")

welcome()
welcome()
welcome()
```

Now the same logic is written only once.

### Main advantages

- Reusability
- Less duplicate code
- Better organization
- Easier maintenance
- Easier debugging
- Cleaner programs

---

# 💡 6. Function with Parameters

A function can receive information.

Example:

```python
def greet(name):
    print("Hello", name)
```

Call the function:

```python
greet("Durga")
```

### Output

```text
Hello Durga
```

Here:

```text
name → Parameter
"Durga" → Argument
```

---

# 🧠 7. Parameter vs Argument

This is an important concept.

Example:

```python
def greet(name):
    print("Hello", name)
```

Here:

```text
name
```

is the **parameter**.

When we call:

```python
greet("Durga")
```

`"Durga"` is the **argument**.

Simple ga:

```text
Parameter → Function definition lo receive chese variable

Argument → Function call appudu pass chese actual value
```

---

# 💰 8. Function with Calculation

Functions become more useful when we use them for calculations.

Example:

```python
def calculate_total(price, quantity):
    return price * quantity
```

Call the function:

```python
total = calculate_total(500, 3)

print("Total:", total)
```

### Output

```text
Total: 1500
```

---

# 🔙 9. Understanding `return`

The `return` statement sends a value back from the function.

Example:

```python
def calculate_total(price, quantity):
    return price * quantity
```

When we call:

```python
total = calculate_total(500, 3)
```

The function calculates:

```text
500 × 3
```

and returns:

```text
1500
```

Then:

```python
total
```

contains:

```text
1500
```

---

# 🧠 10. `print()` vs `return`

These two concepts are different.

### `print()`

Displays something on the screen.

```python
def show_total():
    print(1500)
```

### `return`

Sends a value back to the calling code.

```python
def calculate_total():
    return 1500
```

Then we can store it:

```python
total = calculate_total()
```

This is useful because the returned value can be used later.

---

# 🧮 11. Multiple Function Calls

We can call the same function with different values.

```python
def calculate_total(price, quantity):
    return price * quantity

total1 = calculate_total(500, 3)
total2 = calculate_total(1200, 2)
total3 = calculate_total(300, 5)

print(total1)
print(total2)
print(total3)
```

### Output

```text
1500
2400
1500
```

Same function.

Different inputs.

Different results.

---

# 🐾 12. Pet Shop Example

Let's create a function for product revenue.

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Now:

```python
revenue = calculate_revenue(1200, 2)

print("Revenue:", revenue)
```

### Output

```text
Revenue: 2400
```

This follows the business rule:

```text
Revenue = Price × Quantity
```

---

# 📦 13. Function with Product Information

```python
def calculate_revenue(price, quantity):
    return price * quantity

product = "Dog Food"
price = 1200
quantity = 2

revenue = calculate_revenue(price, quantity)

print("Product:", product)
print("Price:", price)
print("Quantity:", quantity)
print("Revenue:", revenue)
```

### Output

```text
Product: Dog Food
Price: 1200
Quantity: 2
Revenue: 2400
```

---

# 🔁 14. Function + Loop

We can use functions together with loops.

Example:

```python
def calculate_revenue(price, quantity):
    return price * quantity

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

for i in range(len(prices)):
    revenue = calculate_revenue(prices[i], quantities[i])

    print("Revenue:", revenue)
```

### Output

```text
Revenue: 2400
Revenue: 2700
Revenue: 1500
Revenue: 2000
```

Here:

```text
Function → Calculates revenue
Loop → Processes every product
Lists → Store the data
```

---

# 🧠 15. Function + Multiple Lists

Now let's add product names.

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]


def calculate_revenue(price, quantity):
    return price * quantity


for i in range(len(products)):
    revenue = calculate_revenue(prices[i], quantities[i])

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

# 💼 16. Why This Is Better

Previously:

```python
revenue = prices[i] * quantities[i]
```

Now:

```python
revenue = calculate_revenue(prices[i], quantities[i])
```

The calculation logic is separated into a function.

This makes the program easier to understand.

```text
Main Program
     ↓
Call Function
     ↓
Calculate Revenue
     ↓
Return Result
     ↓
Continue Program
```

---

# ⚠️ 17. Function with Conditions

A function can also contain conditions.

Example:

```python
def check_price(price):

    if price >= 1000:
        return "Expensive"
    else:
        return "Normal"
```

Call:

```python
result = check_price(1200)

print(result)
```

### Output

```text
Expensive
```

---

# 🧠 18. Understanding the Condition Function

If:

```python
price = 1200
```

Then:

```python
if price >= 1000:
```

becomes:

```text
1200 >= 1000
```

This is:

```text
True
```

So the function returns:

```text
Expensive
```

---

# 🔄 19. Function + Loop + Condition

Now we can combine all three.

```python
def check_price(price):

    if price >= 1000:
        return "Expensive"
    else:
        return "Normal"


prices = [500, 1200, 800, 1500]

for price in prices:

    result = check_price(price)

    print(price, result)
```

### Output

```text
500 Normal
1200 Expensive
800 Normal
1500 Expensive
```

---

# 🏪 20. Life Care Pet Zone Example

Let's analyze product prices.

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]


def check_price(price):

    if price >= 1000:
        return "Expensive"
    else:
        return "Normal"


for i in range(len(products)):

    result = check_price(prices[i])

    print(products[i], result)
```

### Output

```text
Dog Food Expensive
Cat Food Normal
Treats Normal
Toy Normal
```

---

# 📊 21. Function + List + Calculation

Let's create a reusable revenue function.

```python
def calculate_revenue(price, quantity):
    return price * quantity


products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]


for i in range(len(products)):

    revenue = calculate_revenue(
        prices[i],
        quantities[i]
    )

    print("Product:", products[i])
    print("Revenue:", revenue)
    print()
```

### Output

```text
Product: Dog Food
Revenue: 2400

Product: Cat Food
Revenue: 2700

Product: Treats
Revenue: 1500

Product: Toy
Revenue: 2000
```

---

# 💰 22. Function + Total Revenue

We can use a function to calculate individual revenue and a loop to calculate total revenue.

```python
def calculate_revenue(price, quantity):
    return price * quantity


prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]

total = 0

for i in range(len(prices)):

    revenue = calculate_revenue(
        prices[i],
        quantities[i]
    )

    total = total + revenue


print("Total Revenue:", total)
```

### Output

```text
Total Revenue: 8600
```

---

# 🧠 23. Function Flow

Let's understand the complete flow.

```text
Function Definition
        ↓
def calculate_revenue()
        ↓
Receive price & quantity
        ↓
price × quantity
        ↓
return result
        ↓
Function Call
        ↓
Store Result
        ↓
Use Result
```

---

# 🧩 24. Function with Multiple Parameters

A function can have multiple parameters.

Example:

```python
def product_details(name, price, quantity):

    print("Product:", name)
    print("Price:", price)
    print("Quantity:", quantity)
```

Call:

```python
product_details("Dog Food", 1200, 2)
```

### Output

```text
Product: Dog Food
Price: 1200
Quantity: 2
```

---

# 🔢 25. Function Returning Multiple Values

Python functions can return multiple values.

Example:

```python
def calculate(price, quantity):

    total = price * quantity

    return price, quantity, total
```

Call:

```python
price, quantity, total = calculate(1200, 2)

print(price)
print(quantity)
print(total)
```

### Output

```text
1200
2
2400
```

This is useful when a function needs to provide more than one result.

---

# 🔁 26. Reusing a Function

One of the biggest advantages of functions is **reuse**.

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

We can reuse it:

```python
calculate_revenue(1200, 2)
```

```python
calculate_revenue(900, 3)
```

```python
calculate_revenue(300, 5)
```

```python
calculate_revenue(500, 4)
```

We don't need to rewrite:

```python
price * quantity
```

every time.

---

# 🧠 27. Function Naming

Function names should clearly describe what the function does.

Good names:

```python
calculate_revenue()
calculate_total()
check_price()
calculate_discount()
get_product_price()
```

Avoid unclear names:

```python
abc()
xyz()
test1()
doit()
```

Clear names make the code easier to understand.

---

# ⚠️ 28. Common Beginner Mistakes

### Mistake 1 — Forgetting `def`

Incorrect:

```python
calculate_total(price, quantity):
    return price * quantity
```

Correct:

```python
def calculate_total(price, quantity):
    return price * quantity
```

---

### Mistake 2 — Forgetting to Call the Function

Creating a function does not automatically execute it.

```python
def welcome():
    print("Welcome")
```

You need:

```python
welcome()
```

---

### Mistake 3 — Forgetting `return`

Incorrect:

```python
def calculate_total(price, quantity):
    price * quantity
```

Correct:

```python
def calculate_total(price, quantity):
    return price * quantity
```

---

### Mistake 4 — Wrong Number of Arguments

If:

```python
def calculate_total(price, quantity):
```

expects two parameters, call it with two values:

```python
calculate_total(500, 3)
```

---

### Mistake 5 — Indentation Error

Correct:

```python
def welcome():
    print("Welcome")
```

The function body must be indented.

---

# 📌 29. Quick Reference

| Concept | Example |
|---|---|
| Create Function | `def welcome():` |
| Function Call | `welcome()` |
| Parameter | `def greet(name):` |
| Argument | `greet("Durga")` |
| Return | `return price * quantity` |
| Calculation Function | `calculate_total()` |
| Condition Function | `check_price()` |
| Loop + Function | `for ... calculate_total()` |
| Reusable Logic | Call same function multiple times |

---

# 🧠 30. Key Concepts I Learned

### 1. Function

A reusable block of code that performs a specific task.

### 2. `def`

Used to define a function.

### 3. Parameter

A variable that receives a value inside the function.

### 4. Argument

The actual value passed to the function.

### 5. Function Call

Used to execute the function.

### 6. `return`

Sends a result back from the function.

### 7. Reusability

The same function can be used multiple times.

### 8. Function + Loop

Functions can process multiple values through loops.

### 9. Function + Condition

Functions can contain decision-making logic.

---

# 💼 31. Real-World Applications

Functions are used in:

- 🛒 E-commerce
- 📦 Inventory Systems
- 💰 Sales Applications
- 🧾 Billing Systems
- 🐾 Pet Shop Management
- 📊 Data Processing
- 📈 Data Analysis
- 🚚 Order Processing
- 🗄️ Data Engineering

---

# 🏗️ 32. Data Engineering Connection

Functions are very important in Data Engineering because data-processing tasks are often repeated.

For example:

```text
Read Data
    ↓
Clean Data
    ↓
Transform Data
    ↓
Calculate Values
    ↓
Validate Data
    ↓
Store Data
```

Later, I will create reusable functions for different data-processing tasks.

For now, I am learning the foundation:

```python
def process_data():
    # processing logic
```

This will help me write cleaner and more maintainable Data Engineering programs.

---

# 🧩 33. Practice Task 1 — Welcome Function

Create a function:

```python
def welcome():
    print("Welcome to Life Care Pet Zone")
```

Call the function.

Expected output:

```text
Welcome to Life Care Pet Zone
```

---

# 🧩 34. Practice Task 2 — Total Function

Create:

```python
def calculate_total(price, quantity):
    return price * quantity
```

Call:

```python
calculate_total(500, 3)
```

Expected:

```text
1500
```

---

# 🧩 35. Practice Task 3 — Revenue Function

Create:

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Test it with different products.

---

# 🧩 36. Practice Task 4 — Price Checker

Create:

```python
def check_price(price):
```

If price is `>= 1000`, return:

```text
Expensive
```

Otherwise return:

```text
Normal
```

---

# 🧩 37. Practice Task 5 — Function + Loop

Create:

```python
prices = [500, 1200, 800, 1500]
```

Create a function that checks whether each price is expensive or normal.

Use a `for` loop to process every price.

---

# 🧩 38. Practice Task 6 — Function + Multiple Lists

Use:

```python
products = ["Dog Food", "Cat Food", "Treats", "Toy"]

prices = [1200, 900, 300, 500]

quantities = [2, 3, 5, 4]
```

Create a function:

```python
calculate_revenue(price, quantity)
```

Then use a loop to calculate the revenue of every product.

---

# 🚀 39. Day 10 Challenge

Build a small **Pet Shop Sales Program using Functions**.

Your program should:

1. Store products
2. Store prices
3. Store quantities
4. Create a revenue function
5. Calculate product revenue
6. Create a price-checking function
7. Identify expensive products
8. Calculate total revenue

Expected total:

```text
Total Revenue: 8600
```

Try to write the program using reusable functions instead of putting all logic directly inside the loop.

---

# 🔗 40. Day 09 + Day 10 Connection

### Day 09

I learned how to perform:

```text
Sales Analysis
Inventory Analysis
Revenue Calculation
Low Stock Detection
Expensive Product Detection
Highest Revenue
Lowest Revenue
```

### Day 10

Now I am learning how to organize these operations using:

```text
Functions
     ↓
Reusable Logic
     ↓
Cleaner Code
```

For example:

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

This function can be reused throughout my sales analysis program.

---

# 📝 41. What I Understood Today

Today I understood that functions help me write reusable code.

Instead of writing the same calculation repeatedly:

```python
price * quantity
```

I can create:

```python
def calculate_revenue(price, quantity):
    return price * quantity
```

Then I can reuse it whenever required.

I also learned that functions can work together with:

```text
Lists
Loops
Conditions
Calculations
```

This makes Python programs more organized and powerful.

---

# 🎯 42. My Day 10 Learning

Today I learned:

- ✅ Functions
- ✅ `def`
- ✅ Function Names
- ✅ Parameters
- ✅ Arguments
- ✅ Function Calls
- ✅ `return`
- ✅ Function Reusability
- ✅ Functions with Calculations
- ✅ Functions with Loops
- ✅ Functions with Conditions
- ✅ Functions with Lists
- ✅ Business Logic with Functions
- ✅ Data Processing with Functions

---

# 🏆 43. Day 10 Achievement

```text
Day 10 Completed! 🎉

I can now create reusable Python functions
and combine them with lists, loops,
conditions, and calculations.
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
Day 08 → Multiple Lists & Indexing
Day 09 → Sales & Inventory Analysis
Day 10 → Functions
```

### Current Progress

```text
Python Fundamentals
██████████░░░░░░░░░░ 50%
```

I am now moving from basic Python syntax toward writing reusable and structured programs.

---

# 🚀 Next Step — Day 11

In **Day 11**, I will continue with **Functions + Business Logic**.

I will combine functions with:

- Conditions
- Loops
- Lists
- Counting
- Calculations
- Highest and lowest values
- Business rules

This will help me build more practical Python programs.

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
Sales & Inventory Analysis
      ↓
Functions
      ↓
Functions + Business Logic
      ↓
Dictionaries
      ↓
Data Engineering 🚀
```

---

# 👨‍💻 Developed By

## Durga Vamsi

> Learning Python step by step with the goal of becoming a **Data Engineer**.

**Day 10 — Completed Successfully! 🚀🐍**