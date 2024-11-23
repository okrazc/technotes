
# Python Comparison Operators, Branching, and Logical Operators

## Objectives
In this guide, you'll learn about:
- Comparison operators
- Branching
- Logical operators

---

## 1. Comparison Operators

Comparison operators are essential in programming. They help compare values and make decisions based on the results.

### Equality Operator (`==`)
The equality operator `==` checks if two values are equal.

**Example:**
```python
age = 25
if age == 25:
    print("You are 25 years old.")
```
Here, the code checks if the variable `age` is equal to 25 and prints a message accordingly.

### Inequality Operator (`!=`)
The inequality operator `!=` checks if two values are not equal.

**Example:**
```python
if age != 30:
    print("You are not 30 years old.")
```
In this case, the code checks if the variable `age` is not equal to 30 and prints a message accordingly.

### Greater Than and Less Than Operators
You can compare if one value is greater than or less than another using the `>`, `<`, `>=`, or `<=` operators.

**Example:**
```python
if age >= 20:
    print("Yes, the age is greater than or equal to 20.")
```
Here, the code checks if the variable `age` is greater than or equal to 20 and prints a message accordingly.

### Other Comparison Operators:
- **Greater than (`>`)**: Checks if the value on the left is greater than the value on the right.
- **Less than (`<`)**: Checks if the value on the left is less than the value on the right.
- **Greater than or equal to (`>=`)**: Checks if the value on the left is greater than or equal to the value on the right.
- **Less than or equal to (`<=`)**: Checks if the value on the left is less than or equal to the value on the right.

---

## 2. Branching

Branching allows your program to make decisions and execute specific blocks of code based on conditions. Think of it as choosing different paths in your code based on different scenarios.

### `if` Statement
The `if` statement checks a condition and executes the following block of code if the condition is `True`.

**Example:**
```python
age = 20
if age >= 21:
    print("You can enter the bar.")
else:
    print("Sorry, you cannot enter.")
```
Here, if the `age` is 21 or older, the user can enter the bar. Otherwise, they receive a different message.

### `elif` Statement
The `elif` statement allows you to check multiple conditions sequentially. It's like saying "if not this, then maybe this."

**Example:**
```python
age = 18
if age >= 21:
    print("You can enter the bar.")
elif age >= 18:
    print("You can watch a movie.")
else:
    print("Sorry, you cannot do either.")
```
This checks multiple conditions and prints the appropriate message based on the value of `age`.

### Real-life Example: Automated Teller Machine (ATM)
In an ATM, branching is used to make decisions based on user input.

**Example:**
```python
user_choice = "Withdraw Cash"
if user_choice == "Withdraw Cash":
    amount = int(input("Enter the amount to withdraw: "))
    if amount % 10 == 0:
        print(f"Dispensing ${amount}")
    else:
        print("Please enter a multiple of 10.")
else:
    print("Thank you for using the ATM.")
```
Here, the ATM checks the user's choice and processes accordingly.

---

## 3. Logical Operators

Logical operators help combine and manipulate conditions. They include `not`, `and`, and `or`.

### The `not` Operator
The `not` operator negates a condition. It inverts `True` to `False` and vice versa.

**Real-life Example:**
In a smartphone's notification settings, you may only want to receive notifications when your phone is not in "Do Not Disturb" mode.

**Example:**
```python
is_do_not_disturb = True
if not is_do_not_disturb:
    print("New message received")
```

### The `and` Operator
The `and` operator checks if all conditions are `True`. If any condition is `False`, the entire expression becomes `False`.

**Real-life Example:**
In a secure facility, you need both a valid ID card and a matching fingerprint to access a restricted area.

**Example:**
```python
has_valid_id_card = True
has_matching_fingerprint = True
if has_valid_id_card and has_matching_fingerprint:
    print("Access granted.")
```

### The `or` Operator
The `or` operator checks if at least one condition is `True`. If any condition is `True`, the whole expression evaluates to `True`.

**Real-life Example:**
When planning a movie night with friends, you might choose a movie if any of your friends is interested in a particular genre.

**Example:**
```python
friend1_likes_comedy = True
friend2_likes_action = False
friend3_likes_drama = False
if friend1_likes_comedy or friend2_likes_action or friend3_likes_drama:
    print("Choosing a movie for the night.")
```

---

### Summary:
- **Comparison Operators** (`==`, `!=`, `>`, `<`, `>=`, `<=`) help compare values.
- **Branching** (`if`, `elif`, `else`) helps in decision-making based on conditions.
- **Logical Operators** (`not`, `and`, `or`) are used to combine conditions.
```

