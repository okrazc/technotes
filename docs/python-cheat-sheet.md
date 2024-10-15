# Python CheatSheet: Dictionaries and Sets

Package/Method	Description	Code Example
Creating a Dictionary	A dictionary is a built-in data type that represents a collection of key-value pairs. Dictionaries are enclosed in curly braces {}.	Example:
1.	1
2.	2
1.	dict_name = {} #Creates an empty dictionary
2.	person = { "name": "John",  "age": 30, "city": "New York"}
Copied!
Accessing Values	You can access the values in a dictionary using their corresponding keys.	Syntax:
1.	1
1.	Value = dict_name["key_name"]
Copied!
Example:
1.	1
2.	2
1.	name = person["name"]
2.	age = person["age"]
Copied!
Add or modify	Inserts a new key-value pair into the dictionary. If the key already exists, the value will be updated; otherwise, a new entry is created.	Syntax:
1.	1
1.	dict_name[key] = value
Copied!
Example:
1.	1
2.	2
1.	person["Country"] = "USA" # A new entry will be created.
2.	person["city"] = "Chicago"  # Update the existing value for the same key
Copied!
del	Removes the specified key-value pair from the dictionary. Raises a KeyError if the key does not exist.	Syntax:
1.	1
1.	del dict_name[key]
Copied!
Example:
1.	1
1.	del person["Country"]
Copied!
update()	The update() method merges the provided dictionary into the existing dictionary, adding or updating key-value pairs.	Syntax:
1.	1
1.	dict_name.update({key: value})
Copied!
Example:
1.	1
1.	person.update({"Profession": "Doctor"})
Copied!
clear()	The clear() method empties the dictionary, removing all key-value pairs within it. After this operation, the dictionary is still accessible and can be used further.	Syntax:
1.	1
1.	dict_name.clear()
Copied!
Example:
1.	1
1.	grades.clear()
Copied!
key existence	You can check for the existence of a key in a dictionary using the in keyword	Example:
1.	1
2.	2
1.	if "name" in person:
2.	    print("Name exists in the dictionary.")
Copied!
copy()	Creates a shallow copy of the dictionary. The new dictionary contains the same key-value pairs as the original, but they remain distinct objects in memory.	Syntax:
1.	1
1.	new_dict = dict_name.copy()
Copied!
Example:
1.	1
2.	2
1.	new_person = person.copy()
2.	new_person = dict(person) # another way to create a copy of dictionary
Copied!
keys()	Retrieves all keys from the dictionary and converts them into a list. Useful for iterating or processing keys using list methods.	Syntax:
1.	1
1.	keys_list = list(dict_name.keys())
Copied!
Example:
1.	1
1.	person_keys = list(person.keys())
Copied!
values()	Extracts all values from the dictionary and converts them into a list. This list can be used for further processing or analysis.	Syntax:
1.	1
1.	values_list = list(dict_name.values())
Copied!
Example:
1.	1
1.	person_values = list(person.values())
Copied!
items()	Retrieves all key-value pairs as tuples and converts them into a list of tuples. Each tuple consists of a key and its corresponding value.	Syntax:
1.	1
1.	items_list = list(dict_name.items())
Copied!
Example:
1.	1
1.	info = list(person.items())
Copied!
