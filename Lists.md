In Python, a list is a built-in data structure that can hold an ordered collection of items. Unlike arrays in some languages, Python lists are very flexible:

- Can contain duplicate items
- **Mutable:** items can be modified, replaced, or removed
- **Ordered:** maintains the order in which items are added
- **Index-based:** items are accessed using their position (starting from 0)
- Can store mixed data types (integers, strings, `booleans`, even other lists)

## Creating a List

> **Using `[]` brackets**

```Python
a = [1, 2, 3, 4, 5] # List of integers
b = ['apple', 'banana', 'cherry'] # List of strings
c = [1, 'hello', 3.14, True] # Mixed data types

print(a)
print(b)
print(c)
```

> **Using `list()` constructor**

We can also create a list by passing an iterable (like a [[Tuple]], [[Strings]] or another list) to the function.
```Python
char_list = list('apple')
print(char_list) # ['a', 'p', 'p', 'l', 'e']

fruits = list(('apple', 'banana', 'mango'))
print(fruits) #['apple', 'banana', 'mango']
```

## List Operations


> **Accessing a List Element**

Elements in a list are accessed using indexing. Python indexes start at 0, so `a[0]` gives the first element. Negative indexes allow access from the end
```Python
a = [10, 20, 30, 40, 50]
print(a[0])    
print(a[-1])
print(a[1:4])   # elements from index 1 to 3
```

> **Adding Elements to List**

We can add elements to a list using the following methods:

- `append()`: Adds an element at the end of the list.
- `extend()`: Adds multiple elements to the end of the list.
- `insert()`: Adds an element at a specific position.
- `clear()`: removes all items.
```Python
a = []

a.append(10)  
print("After append(10):", a)  

a.insert(0, 5)
print("After insert(0, 5):", a) 

a.extend([15, 20, 25])  
print("After extend([15, 20, 25]):", a) 

a.clear()
print("After clear():", a)
```

> **Updating Elements into List**

Since lists are mutable, we can update elements by accessing them via their index.

```Python
a = [10, 20, 30, 40, 50]
a[1] = 25 
print(a)
```

> **Removing Elements from a List**

We can remove elements from a list using:
- `remove()`: Removes the first occurrence of an element.
- `pop()`: Removes the element at a specific index or the last element if no index is specified.
- `del`:  Deletes an element at a specified index.

```Python
a = [10, 20, 30, 40, 50]

a.remove(30)  
print("After remove(30):", a)

popped_val = a.pop(1)  
print("Popped element:", popped_val)
print("After pop(1):", a) 

del a[0]  
print("After del a[0]:", a)
```

> **Iterating Over Loops**

We can iterate over lists using [[Loops]].
We can also iterate using `in` operator.
```Python
fruits = ['apple', 'banana', 'mango']

for fruit in fruits:
	print(fruit)
```


## Nested Lists

A nested list is a list within another list, which is useful for representing matrices or tables. We can access nested elements by chaining indexes.

```Python
matrix = [ [1, 2, 3],
           [4, 5, 6],
           [7, 8, 9] ]
print(matrix[1][2])
```

## List Comprehension

List comprehension is a concise way to create new lists by applying an expression to each item in an existing iterable (like a list, tuple or range). It helps you write clean, readable and efficient code compared to traditional loops.

Syntax
```
[expression for item in iterable if condition]
```

Why Use List Comprehension?
- Cleaner code: Combines looping, filtering and transformation in one line.
- More readable: Avoids verbose loops and temporary variables.
- Faster execution Often faster than equivalent for-loops.
