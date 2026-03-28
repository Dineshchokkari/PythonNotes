In Python, a string is a sequence of characters written inside quotes. It can include letters, numbers, symbols and spaces.
- Python does not have a separate character type.
- A single character is treated as a string of length one.

Strings can be created using either single ('...') or double ("...") quotes. Both behave the same.
```python
s1 = 'Hello'
s2 = "hello"

message = 'it\'s a new world'
message1 = "it's a new world"
```

Use triple quotes ('''...''' ) or ( """...""") for strings that span multiple lines. Newlines are preserved.
```Python
multiline_string = """This is a multi line string
This is line number 2.
This is line number 3."""

multiline_string_2 = '''This is also a multi line string
but with single quotes.'''
```

Strings are indexed sequences. Positive indices start at 0 from the left, negative indices start at -1 from the right. refer to [String Slicing](#Slicing).
```Python
name = 'python'
print(name[0]) #prints p
print(name[-1]) #prints n
```

Strings are immutable, which means that they cannot be changed after they are created. If we need to manipulate strings then we can use methods like concatenation, slicing or formatting to create new strings based on original.
```Python
text = "Hello World"

text[0] = 'b'  #TypeError: 'str' object does not support item assignment

text = 'b' + text[1:]
print(text) #bello world
```
## Slicing

Slicing is a way to extract a portion of a string by specifying the start and end indexes.
In Python, slicing allows us to extract parts of sequences like strings, lists and tuples. While normal slicing uses positive indices, Python also supports negative slicing, which makes it easier to work with elements starting from the end of a sequence.

Python uses negative indices to count elements from the end.
- -1 refers to the last element
- -2 refers to the second-last element
- -3 refers to the third-last element and so on.

This feature is especially useful when you don’t know exact length of a sequence but still want to access elements from the end.

> **Slicing using `:` operator**

This is the most common way to perform slicing.
```
sequence[start:stop:step]
```

- **start:** Starting index of the slice (can be negative or positive).
- **end:** Ending index of the slice (exclusive, not included).
- **step:** Number of steps to move (use -1 to reverse).

```Python
text = "Hello World"

print(text[0:4:1]) # Hell
print(text[-1:-5:-1]) # dlro
```

> **Slicing using `slice()` function**

Python also provides the slice() function to achieve the same result in a more explicit way.
```
slice[start, stop, step]
```

```Python
text = "Hello World"
reverse_text = text[slice(None, None, -1)]
left_slice = text[slice(0, 5, 1)]
right_slice = text[slice(-1, -4, -1)]
print(left_slice) #Hello
print(right_slice) #dlr
print(reverse_text) #dlroW olleH
```

## String Methods

> **`len()`**

this function returns the total number of characters in a string.

> **`replace(oldstr, newstr)`**

replace the `oldstr` with `newstr` in a string and returns a new string due to string immutability.

> **`strip()`**

removes leading and trailing spaces in a given string
- `lstrip()`: removes leading spaces.
- `rstrip()`: removes trailing spaces.

> **`lower()` and `upper()`**

converts the string to lower case and upper case respectively.

## String concatenation

We can join any number of string by the `+` operator.
```Python
firstname = 'Guido van'
lastname = 'Rassum'

fullname = firstname + ' ' + lastname
print(fullname) # Guido van Rassum
```


## String Formatting

String formatting in Python is used to insert variables and expressions into strings in a readable and structured way. It helps create dynamic output and improves the clarity and presentation of text in programs.

> **Formatting with format() string method**

Formatters work by putting in one or more replacement fields and placeholders defined by a pair of curly braces { } into a string and calling the `str.format()`. The value we wish to put into the placeholders and concatenate with the string passed as parameters into the format function.
```python
firstname = "Linus"
lastname = "Torvalds"
print("full name is {} {}".format(firstname, lastname))
```

Index-based insertion
```Python
firstname = "Linus"
lastname = "Torvalds"
print("full name is {1} {0}".format(lastname, firstname))
```


> **f Strings**

Python introduced f-strings (formatted string literals) in version 3.6 to make string formatting and interpolation easier. With f-strings, you can directly embed variables and expressions inside strings using curly braces {}.

```Python
firstname = "Linus"
lastname = "Torvalds"
print(f"full name is {firstname} {lastname}")
```

