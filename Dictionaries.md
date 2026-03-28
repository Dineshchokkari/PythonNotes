A Python dictionary is a data structure that stores information in key-value pairs. While keys must be unique and immutable (like strings or numbers), the values can be of any data type, whether mutable or immutable. This makes dictionaries ideal for accessing data by a specific name rather than a numeric position like in list

```Python
data = { "name": "Jake", "age": 22 }
print(data)
```

## Creating a Dictionary

A dictionary is created by writing key-value pairs inside { }, where each key is connected to a value using colon (:). A dictionary can also be created using the function.
```Python
d1 = {1: 'Geeks', 2: 'For', 3: 'Geeks'}
print(d1)

# using dict() constructor
d2 = dict(a = "Geeks", b = "for", c = "Geeks")
print(d2)
```

## Dictionary Operations

> **Accessing a Key**

A value in a dictionary is accessed by using its key. This can be done either with square brackets [ ] or with the method. Both return the value linked to the given key. Accessing a missing key with [ ] raises a `KeyError`, while get() is safer because it returns None (or a default value) instead of an error.
```Python
d = { "name": "Kat", 1: "Python", (1, 2): [1,2,4] }

# Access using key
print(d["name"])

# Access using get()
print(d.get("name"))
```

> **Adding and Updating Elements**

New items are added to a dictionary using the assignment operator (=) by giving a new key a value. If an existing key is used with the assignment operator, its value is updated with the new one.
```Python
d = {1: 'foo', 2: 'bar', 3: 'baz'}

# Adding a new key-value pair
d["age"] = 22

# Updating an existing value
d[1] = "Python dict"
print(d)
```

> **Deleting Elements**

Dictionary items can be removed using built-in deletion methods that work on keys:
- `del`:  removes an item using its key
- `pop()`: removes the item with the given key and returns its value
- `clear()`: removes all items from the dictionary
- `popitem()`: removes and returns the last inserted key–value pair

```Python
d = {1: 'Geeks', 2: 'For', 3: 'Geeks', 'age':22}

# Using del 
del d["age"]
print(d)

# Using pop() 
val = d.pop(1)
print(val)

# Using popitem()
key, val = d.popitem()
print(f"Key: {key}, Value: {val}")

# Using clear()
d.clear()
print(d)
```

> **Iterating through Dictionary**

A dictionary can be traversed using a for loop to access its keys, values or both key-value pairs by using the built-in methods `keys()`, `values()`, `items()`.

```Python
d = {1: 'Geeks', 2: 'For', 'age':22}

# Iterate over keys
for key in d:
    print(key)

# Iterate over values
for value in d.values():
    print(value)

# Iterate over key-value pairs
for key, value in d.items():
    print(f"{key}: {value}")
```

