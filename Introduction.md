Python is a high-level programming language known for its simple and readable syntax. It has the following features.
- Allows writing programs with fewer lines of code, improving readability.
- Automatically detects variable types at runtime, eliminating the need for explicit declarations.
- Used in web development, data analysis, automation, and many other fields.
- Supports object-oriented, functional, and procedural programming styles.
- Dynamically typed and has automatic garbage collection.

## Comments

Comments in Python are the lines in the code that are ignored by the interpreter during the execution of the program.
- It enhance the readability of the code.
- It can be used to identify functionality or structure the code-base.
- It can help understanding unusual or tricky scenarios handled by the code to prevent accidental removal or changes.
- It can be used to prevent executing any specific part of your code, while making changes or testing.
```Python
# Python program to demonstrate
# multiline comments
print("Multiline comments")

""" Python program to demonstrate
 multiline comments""" # this is also a valid comment as python ignores them
```

## Input and Output

The print() function is used for output in various formats and the input() function enables interaction with users.

> `input()` function

it is used to take user input. By default, it returns the user input in form of a string.
```Python
name = input("Enter your name:")
age = int(input("Enter age:"))
```

> `print()` function

The print() function allows us to display text, variables and expressions on the console.
```Python
print(name)
print(age)
print(name, age)
```
# Variables

In Python, variables are used to store data that can be referenced and manipulated during program execution. A variable is essentially a name that is assigned to a value.
- Unlike Java and many other languages, Python variables do not require explicit declaration of type.
- The type of the variable is inferred based on the value assigned.

To use variables effectively, we must follow Python’s naming rules:
- Variable names can only contain letters, digits and underscores (_).
- A variable name cannot start with a digit.
- Variable names are case-sensitive like myVar and myvar are different.
- Avoid using [Key Words](#KeyWords) like if, else, for as variable names.
```Python
# invalid variable names
1name = "Error"  # Starts with a digit
class = 10       # 'class' is a reserved keyword
user-name = "Doe"  # Contains a hyphen
```
## KeyWords

Keywords in Python are special reserved words that are part of the language itself. They define the rules and structure of Python programs which means you cannot use them as names for your variables, functions, classes or any other identifiers.

```Python
import keyword
print("The list of keywords are : ")
print(keyword.kwlist)

#output:
"""
The list of keywords are:   
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
"""
```
## Operators

> **Arithmetic Operators**

- `+` add
- `-` subtract
- `*` multiply
- `/` divide (float result)
- `//` floor divide
- `%` remainder
- `**` power

 > **Comparison operators**
- `==`, `!=`, `>`, `<`, `>=`, `<=`

> **Logical operators**
- `and`, `or`, `not`