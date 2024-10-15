
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

---

This cheat sheet provides a quick overview of common dictionary and set operations in Python. Use this as a handy reference for working with these data structures.
```
