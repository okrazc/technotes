
# Python Dictionaries and Sets Cheat Sheet

## Dictionaries

### Creating a Dictionary
A dictionary is a collection of key-value pairs, enclosed in curly braces `{}`.

**Example:**
```python
dict_name = {}  # Creates an empty dictionary
person = { "name": "John", "age": 30, "city": "New York" }
```

### Accessing Values
Access values in a dictionary using their corresponding keys.

**Syntax:**
```python
value = dict_name["key_name"]
```

**Example:**
```python
name = person["name"]
age = person["age"]
```

### Adding or Modifying Entries
Insert or update a key-value pair. If the key exists, the value is updated; otherwise, a new entry is created.

**Syntax:**
```python
dict_name[key] = value
```

**Example:**
```python
person["country"] = "USA"  # New entry
person["city"] = "Chicago"  # Update existing value
```

### Deleting Entries
Remove a key-value pair using `del`. Raises `KeyError` if the key does not exist.

**Syntax:**
```python
del dict_name[key]
```

**Example:**
```python
del person["country"]
```

### Merging Dictionaries with `update()`
Merges another dictionary into the current one, adding or updating key-value pairs.

**Syntax:**
```python
dict_name.update({key: value})
```

**Example:**
```python
person.update({"profession": "Doctor"})
```

### Clearing a Dictionary
Remove all key-value pairs with `clear()`. The dictionary remains usable.

**Syntax:**
```python
dict_name.clear()
```

**Example:**
```python
person.clear()
```

### Checking for Key Existence
Check if a key is present in the dictionary using the `in` keyword.

**Example:**
```python
if "name" in person:
    print("Name exists.")
```

### Copying a Dictionary
Create a shallow copy of a dictionary using `copy()`.

**Syntax:**
```python
new_dict = dict_name.copy()
```

**Example:**
```python
new_person = person.copy()
```

### Retrieving Keys
Get all keys in a dictionary as a list.

**Syntax:**
```python
keys_list = list(dict_name.keys())
```

**Example:**
```python
person_keys = list(person.keys())
```

### Retrieving Values
Get all values from a dictionary as a list.

**Syntax:**
```python
values_list = list(dict_name.values())
```

**Example:**
```python
person_values = list(person.values())
```

### Retrieving Key-Value Pairs
Get all key-value pairs as a list of tuples.

**Syntax:**
```python
items_list = list(dict_name.items())
```

**Example:**
```python
info = list(person.items())
```

---

## Sets

### Defining a Set
A set is an unordered collection of unique elements, enclosed in curly braces `{}`.

**Example:**
```python
fruits = {"apple", "banana", "orange"}
```

### Adding Elements to a Set
Add elements to a set with `add()`. Duplicates are automatically removed.

**Syntax:**
```python
set_name.add(element)
```

**Example:**
```python
fruits.add("mango")
```

### Removing Elements from a Set
- **`discard()`**: Removes the element if present, does nothing if not.
- **`remove()`**: Removes the element, raises `KeyError` if not found.

**Syntax (discard):**
```python
set_name.discard(element)
```

**Syntax (remove):**
```python
set_name.remove(element)
```

**Example:**
```python
fruits.discard("apple")
fruits.remove("banana")
```

### Clearing a Set
Remove all elements from the set with `clear()`.

**Syntax:**
```python
set_name.clear()
```

**Example:**
```python
fruits.clear()
```

### Copying a Set
Create a shallow copy of a set with `copy()`.

**Syntax:**
```python
new_set = set_name.copy()
```

**Example:**
```python
new_fruits = fruits.copy()
```

### Set Operations
Perform operations like union, intersection, difference, and symmetric difference between sets.

**Syntax:**
```python
union_set = set1.union(set2)
intersection_set = set1.intersection(set2)
difference_set = set1.difference(set2)
sym_diff_set = set1.symmetric_difference(set2)
```

**Example:**
```python
combined = fruits.union(colors)
common = fruits.intersection(colors)
unique_to_fruits = fruits.difference(colors)
sym_diff = fruits.symmetric_difference(colors)
```

### Checking Subsets and Supersets
- **`issubset()`**: Check if all elements of the current set are in another set.
- **`issuperset()`**: Check if the current set contains all elements of another set.

**Syntax:**
```python
is_subset = set1.issubset(set2)
is_superset = set1.issuperset(set2)
```

**Example:**
```python
is_subset = fruits.issubset(colors)
is_superset = colors.issuperset(fruits)
```

### Removing and Returning Elements
- **`pop()`**: Removes and returns an arbitrary element from the set.

**Syntax:**
```python
removed_element = set_name.pop()
```

**Example:**
```python
removed_fruit = fruits.pop()
```

### Updating a Set
Add elements from an iterable to a set using `update()`. Duplicates are ignored.

**Syntax:**
```python
set_name.update(iterable)
```

**Example:**
```python
fruits.update(["kiwi", "grape"])
```
To improve and expand the content on **Comparison Operators in Python** with better formatting and additional details, I will break down each section, enhance clarity, add explanations where needed, and ensure proper code formatting. Here's an enhanced version of your content suitable for use in GitHub markdown or similar documentation:

```markdown
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

