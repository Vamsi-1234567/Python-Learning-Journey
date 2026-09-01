# 📅 Day 04 — Operators & Calculations

Welcome to **Day 04 of my Python Learning Journey** 🐍🚀

Day 04 lo nenu Python lo **operators** use chesi different mathematical calculations cheyadam nerchukunnanu.

Day 01 lo Python Basics, Day 02 lo Variables & Data Types, Day 03 lo Input & Type Conversion nerchukunna taruvata, Day 04 lo aa concepts ni use chesi **calculations and simple business logic** practice chesanu.

---

# 🎯 Day 04 Learning Goal

The main goal of Day 04 was to understand:

- ➕ Addition
- ➖ Subtraction
- ✖️ Multiplication
- ➗ Division
- `%` Modulus
- 🧮 Mathematical calculations
- 📦 Variables with calculations
- 💰 Real-world business calculations

---

# 📚 Topics Learned

- Arithmetic Operators
- Addition `+`
- Subtraction `-`
- Multiplication `*`
- Division `/`
- Modulus `%`
- Performing calculations
- Storing calculation results
- Using operators with variables
- Business logic
- Revenue calculation

---

# 1. 🧮 What is an Operator?

Operator ante values or variables meeda operation perform cheyadaniki use chese symbol.

Example:

```python
price = 500
quantity = 3

total = price * quantity
```

Ikkada:

```text
price
  ↓
500

quantity
  ↓
3

*
↓
Multiplication

500 × 3
   ↓
1500
```

Python lo operators calculations and data processing ki very important.

---

# 2. ➕ Addition Operator `+`

`+` operator two or more values ni add cheyadaniki use chestam.

Example:

```python
price1 = 500
price2 = 300

total = price1 + price2

print(total)
```

### 📊 Output

```text
800
```

### 🧠 Explanation

```text
500 + 300
   ↓
800
```

Addition business lo multiple prices or amounts ni combine cheyadaniki use cheyachu.

---

# 3. ➖ Subtraction Operator `-`

`-` operator oka value nundi another value subtract cheyadaniki use chestam.

Example:

```python
price = 1200
discount = 200

final_price = price - discount

print(final_price)
```

### 📊 Output

```text
1000
```

### 🧠 Explanation

```text
1200 - 200
    ↓
1000
```

Business example lo discount calculate cheyadaniki subtraction use cheyachu.

---

# 4. ✖️ Multiplication Operator `*`

`*` operator values ni multiply cheyadaniki use chestam.

Example:

```python
price = 500
quantity = 3

total = price * quantity

print(total)
```

### 📊 Output

```text
1500
```

### 🧠 Explanation

```text
500 × 3
  ↓
1500
```

Product billing and revenue calculations lo multiplication chala important.

---

# 5. ➗ Division Operator `/`

`/` operator division perform cheyadaniki use chestam.

Example:

```python
total = 1000
quantity = 4

price = total / quantity

print(price)
```

### 📊 Output

```text
250.0
```

### 🧠 Explanation

```text
1000 ÷ 4
    ↓
250.0
```

Python `/` operator division result ni normally float ga return chestundi.

---

# 6. `%` Modulus Operator

`%` operator division taruvata **remainder** ni return chestundi.

Example:

```python
number = 10
remainder = number % 3

print(remainder)
```

### 📊 Output

```text
1
```

Because:

```text
10 ÷ 3

Quotient = 3
Remainder = 1
```

So:

```python
10 % 3
```

Result:

```text
1
```

---

# 🧠 Modulus Simple Explanation

Example:

```python
10 % 2
```

Output:

```text
0
```

Because 10 is completely divisible by 2.

Another example:

```python
10 % 3
```

Output:

```text
1
```

Because 10 divided by 3 leaves remainder 1.

---

# 📊 Arithmetic Operators

| Operator | Name | Example | Result |
|---|---|---|---:|
| `+` | Addition | `10 + 5` | `15` |
| `-` | Subtraction | `10 - 5` | `5` |
| `*` | Multiplication | `10 * 5` | `50` |
| `/` | Division | `10 / 5` | `2.0` |
| `%` | Modulus | `10 % 3` | `1` |

---

# 7. 📦 Operators with Variables

Operators ni direct values tho matrame kakunda variables tho kuda use cheyachu.

Example:

```python
price = 500
quantity = 3

total = price * quantity

print(total)
```

Output:

```text
1500
```

Flow:

```text
price = 500
quantity = 3

      ↓

price * quantity

      ↓

500 * 3

      ↓

1500
```

---

# 8. 🧮 Multiple Calculations

Oka program lo multiple operators use cheyachu.

Example:

```python
price = 1000
discount = 100
quantity = 2

final_price = price - discount
total = final_price * quantity

print("Final Price:", final_price)
print("Total:", total)
```

### 📊 Output

```text
Final Price: 900
Total: 1800
```

Flow:

```text
Price
 ↓
1000

Discount
 ↓
100

1000 - 100
 ↓
900

900 × 2
 ↓
1800
```

---

# 9. 💰 Business Logic — Revenue

Day 04 lo important business calculation:

```text
Revenue = Price × Quantity
```

Python:

```python
price = 500
quantity = 3

revenue = price * quantity

print("Revenue:", revenue)
```

### 📊 Output

```text
Revenue: 1500
```

### 🧠 Explanation

Product price:

```text
₹500
```

Quantity:

```text
3
```

Revenue:

```text
₹500 × 3
   ↓
₹1500
```

---

# 🐾 Real-World Pet Shop Example

Life Care Pet Zone lo customer 3 products purchase chestunnadu anukundam.

```python
price = 500
quantity = 3

total = price * quantity

print("Product Price:", price)
print("Quantity:", quantity)
print("Total:", total)
```

### 📊 Output

```text
Product Price: 500
Quantity: 3
Total: 1500
```

---

# 💻 Day 04 Complete Example

```python
product = "Dog Food"
price = 500
quantity = 3

total = price * quantity

print("Product:", product)
print("Price:", price)
print("Quantity:", quantity)
print("Total:", total)
```

### 📊 Output

```text
Product: Dog Food
Price: 500
Quantity: 3
Total: 1500
```

---

# 🔍 Understanding the Complete Example

## Step 1 — Product

```python
product = "Dog Food"
```

Product name ni variable lo store chesam.

---

## Step 2 — Price

```python
price = 500
```

Product price ni store chesam.

---

## Step 3 — Quantity

```python
quantity = 3
```

Customer enni products konnado store chesam.

---

## Step 4 — Calculate Total

```python
total = price * quantity
```

Calculation:

```text
500 × 3
  ↓
1500
```

---

## Step 5 — Display Result

```python
print("Total:", total)
```

Output:

```text
Total: 1500
```

---

# 💻 Day 04 Example — Addition

```python
dog_food = 1200
cat_food = 900

total = dog_food + cat_food

print("Total Price:", total)
```

### 📊 Output

```text
Total Price: 2100
```

---

# 💻 Day 04 Example — Subtraction

```python
price = 1200
discount = 200

final_price = price - discount

print("Final Price:", final_price)
```

### 📊 Output

```text
Final Price: 1000
```

---

# 💻 Day 04 Example — Multiplication

```python
price = 300
quantity = 5

total = price * quantity

print("Total:", total)
```

### 📊 Output

```text
Total: 1500
```

---

# 💻 Day 04 Example — Division

```python
total = 1500
quantity = 5

price = total / quantity

print("Price:", price)
```

### 📊 Output

```text
Price: 300.0
```

---

# 💻 Day 04 Example — Modulus

```python
number = 15

remainder = number % 4

print("Remainder:", remainder)
```

### 📊 Output

```text
Remainder: 3
```

---

# 🧩 Combining Operators

Multiple operators ni same program lo use cheyachu.

Example:

```python
price = 1000
discount = 100
quantity = 2

discounted_price = price - discount
total = discounted_price * quantity

print("Original Price:", price)
print("Discount:", discount)
print("Discounted Price:", discounted_price)
print("Quantity:", quantity)
print("Total:", total)
```

### 📊 Output

```text
Original Price: 1000
Discount: 100
Discounted Price: 900
Quantity: 2
Total: 1800
```

---

# 🧠 Calculation Flow

```text
Original Price
      ↓
Discount
      ↓
Subtraction
      ↓
Final Price
      ↓
Quantity
      ↓
Multiplication
      ↓
Total Amount
```

---

# 🎯 Day 04 Practice Tasks

## Practice Task 1 — Addition

```python
a = 100
b = 200

result = a + b

print(result)
```

### Output

```text
300
```

---

## Practice Task 2 — Subtraction

```python
a = 500
b = 200

result = a - b

print(result)
```

### Output

```text
300
```

---

## Practice Task 3 — Multiplication

```python
price = 500
quantity = 4

total = price * quantity

print(total)
```

### Output

```text
2000
```

---

## Practice Task 4 — Division

```python
total = 2000
quantity = 4

price = total / quantity

print(price)
```

### Output

```text
500.0
```

---

## Practice Task 5 — Modulus

```python
number = 20

remainder = number % 3

print(remainder)
```

### Output

```text
2
```

---

# 🧪 Day 04 Practice Program

```python
# Life Care Pet Zone
# Product Sales Calculation

product = "Dog Food"
price = 1200
quantity = 2

total = price * quantity

print("-------------------------")
print("Life Care Pet Zone")
print("-------------------------")

print("Product:", product)
print("Price:", price)
print("Quantity:", quantity)
print("Total Revenue:", total)
```

### 📊 Output

```text
-------------------------
Life Care Pet Zone
-------------------------
Product: Dog Food
Price: 1200
Quantity: 2
Total Revenue: 2400
```

---

# 💡 Business Applications

Arithmetic operators real-world applications lo chala important.

### 🛒 Sales

```text
Price × Quantity
       ↓
Total Sales
```

### 💰 Revenue

```text
Price × Quantity
       ↓
Revenue
```

### 🏷️ Discount

```text
Original Price - Discount
          ↓
Final Price
```

### 📦 Stock

```text
Available Stock - Sold Quantity
             ↓
Remaining Stock
```

### 🧮 Average

```text
Total Amount ÷ Quantity
          ↓
Average
```

---

# 🔍 Operator Quick Reference

```python
# Addition
a + b

# Subtraction
a - b

# Multiplication
a * b

# Division
a / b

# Modulus
a % b
```

---

# 🧠 Important Concepts to Remember

## ➕ Addition

```python
10 + 5
```

Result:

```text
15
```

---

## ➖ Subtraction

```python
10 - 5
```

Result:

```text
5
```

---

## ✖️ Multiplication

```python
10 * 5
```

Result:

```text
50
```

---

## ➗ Division

```python
10 / 5
```

Result:

```text
2.0
```

---

## `%` Modulus

```python
10 % 3
```

Result:

```text
1
```

---

# ❌ Common Beginner Mistakes

## Mistake 1 — Using `x` for Multiplication

Incorrect:

```python
total = price x quantity
```

Correct:

```python
total = price * quantity
```

Python lo multiplication kosam `*` use chestam.

---

## Mistake 2 — Confusing `/` and `%`

Division:

```python
10 / 3
```

Result:

```text
3.3333333333333335
```

Modulus:

```python
10 % 3
```

Result:

```text
1
```

Difference:

```text
/ → Division Result

% → Remainder
```

---

## Mistake 3 — Wrong Variable Name

Example:

```python
price = 500
quantity = 3

total = price * quantities
```

Ikkada `quantities` variable create cheyaledu.

Correct:

```python
total = price * quantity
```

Variable names exactly match avvali.

---

# 🧠 What I Understood in Day 04

Day 04 lo nenu Python arithmetic operators ni practice chesanu.

I learned how to perform:

```text
Addition
Subtraction
Multiplication
Division
Modulus
```

I also learned how to store calculation results inside variables.

Most importantly, mathematical operators ni real-world business problems tho connect cheyadam practice chesanu.

Example:

```text
Price × Quantity
      ↓
Revenue
```

---

# 💭 My Day 04 Learning

Day 04 na Python learning journey lo calculations and business logic ki important step.

Day 01 lo basics, Day 02 lo data types, Day 03 lo user input and type conversion nerchukunna taruvata, Day 04 lo aa concepts ni use chesi mathematical calculations practice chesanu.

`+`, `-`, `*`, `/`, `%` operators ni use chesi different calculations chesanu.

Pet Shop / Life Care Pet Zone examples tho product price, quantity, total amount, discount and revenue lanti calculations practice chesanu.

Simple calculations future lo large data processing and Data Engineering tasks ki foundation ga work chestayi.

---

# 📝 What I Learned — Day 04

I learned how Python arithmetic operators are used to perform mathematical calculations.

I learned:

```text
+ → Addition
- → Subtraction
* → Multiplication
/ → Division
% → Modulus
```

I also learned how operators can be combined with variables to create useful calculations.

For example:

```python
price = 500
quantity = 3

total = price * quantity
```

Output:

```text
1500
```

This helped me understand how Python can be used to solve simple real-world business problems.

---

# 🏆 Day 04 Achievement

By completing Day 04, I learned:

- ✅ Arithmetic Operators
- ✅ Addition `+`
- ✅ Subtraction `-`
- ✅ Multiplication `*`
- ✅ Division `/`
- ✅ Modulus `%`
- ✅ Mathematical calculations
- ✅ Operators with variables
- ✅ Storing calculation results
- ✅ Revenue calculation
- ✅ Discount calculation
- ✅ Product total calculation
- ✅ Basic business logic
- ✅ Real-world Pet Shop examples

---

# 🎯 Day 04 Summary

```text
Day 04
   ↓
Arithmetic Operators
   ↓
Addition
   ↓
Subtraction
   ↓
Multiplication
   ↓
Division
   ↓
Modulus
   ↓
Calculations
   ↓
Business Logic
   ↓
Revenue Calculation
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
   ↓
Day 04
Operators & Calculations
   ↓
Day 05
Conditions & Decision Making
```

---

# 🚀 Next Step

## 📅 Day 05 — Conditions & Decision Making

In Day 05, I will learn how Python makes decisions using:

- `if`
- `elif`
- `else`
- Comparison operators
- `>`
- `<`
- `>=`
- `<=`
- `==`
- `!=`

I will use these concepts to create decision-making programs and real-world business logic.

---

# 🐍 Python Learning Journey

**Day 04 → Completed ✅**

> **Learn → Practice → Make Mistakes → Understand → Improve.** 🚀

---

# 👨‍💻 Developed By

**Durga Vamsi**

📌 **Project:** Python Learning Journey

📅 **Progress:** Day 01 → Day 04

🎯 **Goal:** Python → Data Engineering