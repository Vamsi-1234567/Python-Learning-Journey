# 🐍 DAY 17 — Exception Handling

## 📌 Day 17 Goal

Today we will learn **Exception Handling in Python**.

Until now, we have written programs assuming everything works correctly.

But real-world programs can have errors.

For example:

- User enters text instead of a number
- A product key does not exist
- A file does not exist
- Division by zero happens
- Invalid data is received
- API or database operations fail

Instead of allowing the entire program to stop, Python provides **Exception Handling**.

Today we will learn:

- What is an Exception?
- What is an Error?
- `try`
- `except`
- Handling specific exceptions
- Multiple `except`
- `else`
- `finally`
- `raise`
- Exception handling with functions
- Exception handling with user input
- Exception handling with dictionaries
- Business-data examples
- Data Engineering connection

---

# 1️⃣ What is an Exception?

An **exception** is an error that occurs while a Python program is running.

Example:

```python
price = 100
quantity = 0

total = price / quantity

print(total)
```

This produces:

```text
ZeroDivisionError
```

Because we cannot divide a number by zero.

Without exception handling, the program stops at the error.

---

# 2️⃣ Why Do We Need Exception Handling?

Consider this program:

```python
price = int(input("Enter price: "))

print("Price:", price)
```

If the user enters:

```text
1200
```

the program works.

But if the user enters:

```text
abc
```

Python produces:

```text
ValueError
```

Instead of allowing the program to stop, we can handle the error.

---

# 3️⃣ Basic `try` and `except`

The basic syntax is:

```python
try:
    # code that may cause an error

except:
    # code to handle the error
```

Example:

```python
try:
    number = int(input("Enter a number: "))
    print("Number:", number)

except:
    print("Invalid input")
```

If the user enters:

```text
100
```

Output:

```text
Number: 100
```

If the user enters:

```text
abc
```

Output:

```text
Invalid input
```

The program does not crash.

---

# 4️⃣ Understanding `try`

The `try` block contains code that **may produce an exception**.

Example:

```python
try:
    number = int(input("Enter a number: "))
```

Python tries to execute the code.

If there is no error:

```text
try → success
```

If an exception occurs:

```text
try → error → except
```

---

# 5️⃣ Understanding `except`

The `except` block handles the exception.

Example:

```python
try:
    number = int(input("Enter a number: "))

except:
    print("Please enter a valid number")
```

This is useful when dealing with user input.

---

# 6️⃣ Handling `ValueError`

`ValueError` occurs when a function receives a value of the correct type but an inappropriate value.

A common example is converting invalid text to an integer.

```python
try:
    age = int(input("Enter age: "))
    print("Age:", age)

except ValueError:
    print("Please enter a valid number")
```

If input is:

```text
25
```

Output:

```text
Age: 25
```

If input is:

```text
abc
```

Output:

```text
Please enter a valid number
```

---

# 7️⃣ Handling `ZeroDivisionError`

Example:

```python
try:
    price = 100
    quantity = 0

    result = price / quantity

    print(result)

except ZeroDivisionError:
    print("Cannot divide by zero")
```

Output:

```text
Cannot divide by zero
```

---

# 8️⃣ Why Specific Exceptions Are Better

You can write:

```python
except:
```

But it is usually better to specify the expected exception.

Instead of:

```python
try:
    number = int(input("Enter number: "))

except:
    print("Something went wrong")
```

Use:

```python
try:
    number = int(input("Enter number: "))

except ValueError:
    print("Please enter a valid number")
```

This makes the program more understandable.

---

# 9️⃣ Multiple `except` Blocks

A program can have different types of exceptions.

Example:

```python
try:
    number = int(input("Enter number: "))
    result = 100 / number

    print(result)

except ValueError:
    print("Please enter a valid number")

except ZeroDivisionError:
    print("Number cannot be zero")
```

If the user enters:

```text
abc
```

Output:

```text
Please enter a valid number
```

If the user enters:

```text
0
```

Output:

```text
Number cannot be zero
```

---

# 🔟 `else` Block

Python also provides:

```python
else
```

The `else` block runs **only when no exception occurs**.

Syntax:

```python
try:
    # risky code

except:
    # error handling

else:
    # successful code
```

Example:

```python
try:
    number = int(input("Enter number: "))

except ValueError:
    print("Invalid number")

else:
    print("Number entered successfully")
```

If input is:

```text
100
```

Output:

```text
Number entered successfully
```

If input is:

```text
abc
```

Output:

```text
Invalid number
```

---

# 1️⃣1️⃣ `finally` Block

`finally` runs whether an exception occurs or not.

Syntax:

```python
try:
    # code

except:
    # error

finally:
    # always runs
```

Example:

```python
try:
    number = int(input("Enter number: "))
    print(number)

except ValueError:
    print("Invalid input")

finally:
    print("Program completed")
```

If input is valid:

```text
100
Program completed
```

If input is invalid:

```text
Invalid input
Program completed
```

---

# 1️⃣2️⃣ `try + except + else + finally`

We can use all four together.

```python
try:
    number = int(input("Enter number: "))

except ValueError:
    print("Invalid number")

else:
    print("Valid number:", number)

finally:
    print("Execution completed")
```

Flow:

```text
             try
              ↓
       Is there an error?
        ↙             ↘
      YES              NO
       ↓                ↓
    except            else
       ↘              ↙
          finally
             ↓
          Continue
```

---

# 1️⃣3️⃣ Dictionary Exception

Our product data uses dictionaries.

```python
product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}
```

If we try to access a key that doesn't exist:

```python
print(product["Category"])
```

Python produces:

```text
KeyError
```

We can handle it.

```python
try:
    print(product["Category"])

except KeyError:
    print("Category key does not exist")
```

Output:

```text
Category key does not exist
```

---

# 1️⃣4️⃣ Handling `KeyError`

Example:

```python
product = {
    "Name": "Dog Food",
    "Price": 1200
}

try:
    quantity = product["Quantity"]

except KeyError:
    print("Quantity information is missing")
```

Output:

```text
Quantity information is missing
```

This is important when processing real-world data because not every record may contain the same fields.

---

# 1️⃣5️⃣ Exception Handling with Functions

We can use exception handling inside functions.

```python
def calculate_total(price, quantity):

    try:
        return price * quantity

    except TypeError:
        return "Invalid price or quantity"
```

Example:

```python
print(calculate_total(1200, 2))
```

Output:

```text
2400
```

---

# 1️⃣6️⃣ Safe Division Function

```python
def divide_numbers(a, b):

    try:
        return a / b

    except ZeroDivisionError:
        return "Cannot divide by zero"
```

Example:

```python
print(divide_numbers(100, 5))
print(divide_numbers(100, 0))
```

Output:

```text
20.0
Cannot divide by zero
```

This is an example of creating **reusable error-handling logic**.

---

# 1️⃣7️⃣ Product Price Input

Let's build a small business example.

```python
try:
    price = float(input("Enter product price: "))

    print("Product Price:", price)

except ValueError:
    print("Invalid price")
```

If the user enters:

```text
1200
```

Output:

```text
Product Price: 1200.0
```

If the user enters:

```text
abc
```

Output:

```text
Invalid price
```

---

# 1️⃣8️⃣ Product Quantity Input

```python
try:
    quantity = int(input("Enter quantity: "))

    print("Quantity:", quantity)

except ValueError:
    print("Quantity must be a number")
```

This protects our program from invalid user input.

---

# 1️⃣9️⃣ Product Revenue with Exception Handling

Business Rule:

```text
Revenue = Price × Quantity
```

Example:

```python
def calculate_revenue(price, quantity):

    try:
        return price * quantity

    except TypeError:
        return "Invalid price or quantity"


print(calculate_revenue(1200, 2))
```

Output:

```text
2400
```

---

# 2️⃣0️⃣ Exception Handling with Product Dictionary

```python
product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}


try:

    price = product["Price"]
    quantity = product["Quantity"]

    revenue = price * quantity

    print("Revenue:", revenue)

except KeyError:
    print("Required product information is missing")
```

Output:

```text
Revenue: 2400
```

---

# 2️⃣1️⃣ Handling Multiple Problems

We can combine multiple exception types.

```python
product = {
    "Name": "Dog Food",
    "Price": 1200,
    "Quantity": 2
}

try:

    price = product["Price"]
    quantity = product["Quantity"]

    revenue = price / quantity

    print("Revenue:", revenue)

except KeyError:
    print("Product information is missing")

except ZeroDivisionError:
    print("Quantity cannot be zero")
```

This makes the program safer.

---

# 2️⃣2️⃣ `raise` Keyword

Sometimes we want to create our own exception when a business rule is violated.

Python provides:

```python
raise
```

Example:

```python
price = -100

if price < 0:
    raise ValueError("Price cannot be negative")
```

Output:

```text
ValueError: Price cannot be negative
```

We can use this for business validation.

---

# 2️⃣3️⃣ Validate Product Price

```python
def validate_price(price):

    if price < 0:
        raise ValueError("Price cannot be negative")

    return price


print(validate_price(1200))
```

Output:

```text
1200
```

If:

```python
print(validate_price(-100))
```

Python raises:

```text
ValueError: Price cannot be negative
```

---

# 2️⃣4️⃣ `raise` + `try/except`

We can catch our own exception.

```python
def validate_price(price):

    if price < 0:
        raise ValueError("Price cannot be negative")

    return price


try:

    price = validate_price(-100)

    print(price)

except ValueError as error:

    print("Error:", error)
```

Output:

```text
Error: Price cannot be negative
```

---

# 2️⃣5️⃣ Getting the Error Message

We can store the exception in a variable.

```python
try:
    number = int("abc")

except ValueError as error:
    print("Error:", error)
```

Output will be similar to:

```text
Error: invalid literal for int() with base 10: 'abc'
```

Here:

```python
as error
```

stores the exception information.

---

# 2️⃣6️⃣ Complete Product Validation

```python
def validate_product(price, quantity):

    if price < 0:
        raise ValueError("Price cannot be negative")

    if quantity < 0:
        raise ValueError("Quantity cannot be negative")

    return True


try:

    validate_product(1200, 2)

    print("Product data is valid")

except ValueError as error:

    print("Validation Error:", error)
```

Output:

```text
Product data is valid
```

---

# 2️⃣7️⃣ Complete Day 17 Business Program

```python
products = [
    {"Name": "Dog Food", "Price": 1200, "Quantity": 2},
    {"Name": "Cat Food", "Price": 900, "Quantity": 3},
    {"Name": "Treats", "Price": 300, "Quantity": 5},
    {"Name": "Bones", "Price": 500, "Quantity": 4}
]


def calculate_revenue(product):

    try:

        price = product["Price"]
        quantity = product["Quantity"]

        return price * quantity

    except KeyError as error:

        print("Missing key:", error)

        return 0


total_revenue = 0


for product in products:

    try:

        revenue = calculate_revenue(product)

        total_revenue += revenue

        print(
            product["Name"],
            "Revenue:",
            revenue
        )

    except Exception as error:

        print("Error:", error)


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

# 2️⃣8️⃣ Why Exception Handling Matters in Data Engineering

Data Engineering involves processing large amounts of data.

Real-world data can contain problems:

```text
Missing values
Invalid values
Wrong data types
Missing columns
Corrupted records
Unexpected input
```

For example:

```python
product = {
    "Name": "Dog Food",
    "Price": "1200",
    "Quantity": 2
}
```

Here `Price` is stored as a string.

We may need to convert it:

```python
try:

    price = float(product["Price"])
    quantity = int(product["Quantity"])

    revenue = price * quantity

    print(revenue)

except ValueError:
    print("Invalid product data")
```

This is the beginning of **robust data processing**.

---

# 2️⃣9️⃣ Data Engineering Flow

Exception handling becomes important in pipelines:

```text
Raw Data
   ↓
Read Data
   ↓
Validate Data
   ↓
Try Processing
   ↓
Handle Errors
   ↓
Transform Data
   ↓
Store Data
```

For example:

```text
CSV
 ↓
Python
 ↓
Validate
 ↓
Exception Handling
 ↓
Clean Data
 ↓
Database
```

Later, this will become important when working with:

- CSV
- JSON
- APIs
- Pandas
- SQL
- ETL pipelines
- Data pipelines

---

# 3️⃣0️⃣ Important Exceptions to Remember

| Exception | Meaning |
|---|---|
| `ValueError` | Invalid value |
| `TypeError` | Wrong data type/operation |
| `ZeroDivisionError` | Division by zero |
| `KeyError` | Dictionary key not found |
| `IndexError` | List index not found |
| `FileNotFoundError` | File does not exist |

---

# 3️⃣1️⃣ Example — `IndexError`

```python
products = ["Dog Food", "Cat Food", "Treats"]

try:

    print(products[5])

except IndexError:

    print("Product index does not exist")
```

Output:

```text
Product index does not exist
```

---

# 3️⃣2️⃣ Example — `TypeError`

```python
price = 1200
quantity = "2"

try:

    total = price * quantity

    print(total)

except TypeError:

    print("Invalid data type")
```

Exception handling helps us identify unexpected data types.

---

# 3️⃣3️⃣ Best Practices

### ✅ Handle specific exceptions

Prefer:

```python
except ValueError:
```

instead of:

```python
except:
```

---

### ✅ Keep `try` blocks small

Better:

```python
try:
    price = int(input("Enter price: "))

except ValueError:
    print("Invalid price")
```

Instead of putting the entire program inside `try`.

---

### ✅ Give useful error messages

Good:

```python
print("Price must be a valid number")
```

Not very useful:

```python
print("Error")
```

---

### ✅ Validate business data

For example:

```python
if price < 0:
    raise ValueError("Price cannot be negative")
```

---

# 3️⃣4️⃣ Common Mistakes

### ❌ Mistake 1 — Wrong Exception Name

Wrong:

```python
except Valueerror:
```

Correct:

```python
except ValueError:
```

Python exception names are case-sensitive.

---

### ❌ Mistake 2 — Using `except` for Everything

Avoid:

```python
except:
    print("Error")
```

when you know the expected exception.

Prefer:

```python
except ValueError:
    print("Invalid number")
```

---

### ❌ Mistake 3 — Forgetting `try`

Wrong:

```python
except ValueError:
    print("Invalid")
```

Correct:

```python
try:
    number = int("abc")

except ValueError:
    print("Invalid")
```

---

### ❌ Mistake 4 — Incorrect Indentation

Python depends on indentation.

Correct:

```python
try:
    number = int("abc")

except ValueError:
    print("Invalid number")
```

---

# 3️⃣5️⃣ Day 17 Practice Tasks

## 🟢 Task 1 — Safe Number Input

Ask the user for a number.

Handle:

```text
ValueError
```

---

## 🟢 Task 2 — Safe Division

Create:

```python
def divide(a, b):
```

Handle:

```text
ZeroDivisionError
```

---

## 🟢 Task 3 — Product Price

Ask the user for a product price.

Handle invalid input.

---

## 🟡 Task 4 — Product Quantity

Ask the user for quantity.

Make sure the value is a valid integer.

---

## 🟡 Task 5 — Dictionary Key

Create a product dictionary.

Try to access a missing key.

Handle:

```text
KeyError
```

---

## 🟡 Task 6 — List Index

Create a product list.

Try to access an invalid index.

Handle:

```text
IndexError
```

---

## 🟠 Task 7 — Product Validation

Create:

```python
def validate_price(price):
```

If price is negative, raise:

```python
ValueError
```

---

## 🟠 Task 8 — Revenue Function

Create:

```python
def calculate_revenue(price, quantity):
```

Handle invalid data.

---

## 🔴 Task 9 — Product Data Validation

For every product:

```text
Check Price
Check Quantity
Calculate Revenue
Handle Errors
```

---

## 🔴 Task 10 — Mini Project

Build a **Safe Product Analysis Program**.

It should:

```text
Read product data
      ↓
Validate data
      ↓
Handle errors
      ↓
Calculate revenue
      ↓
Calculate total revenue
      ↓
Display the report
```

---

# 3️⃣6️⃣ Day 16 vs Day 17

| Day | Main Concept |
|---|---|
| Day 16 | List & Dictionary Comprehensions |
| Day 17 | Exception Handling |

Day 16 focused on:

```text
Transform Data
Filter Data
Create New Collections
```

Day 17 focuses on:

```text
Detect Errors
Handle Errors
Validate Data
Build Reliable Programs
```

---

# 📌 Day 17 Quick Reference

### Basic

```python
try:
    # risky code

except:
    # handle error
```

### Specific Exception

```python
try:
    number = int("abc")

except ValueError:
    print("Invalid number")
```

### Multiple Exceptions

```python
try:
    # code

except ValueError:
    # handle ValueError

except ZeroDivisionError:
    # handle ZeroDivisionError
```

### Else

```python
try:
    # code

except ValueError:
    # error

else:
    # success
```

### Finally

```python
try:
    # code

except:
    # error

finally:
    # always executes
```

### Raise

```python
raise ValueError("Invalid value")
```

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
```

---

# 🚀 Next Step — Day 18

The next topic is:

## 📂 File Handling

We will learn how Python can work with real files.

```text
Python
   ↓
File Handling
   ↓
Read Files
   ↓
Write Files
   ↓
CSV
   ↓
JSON
   ↓
Data Processing
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