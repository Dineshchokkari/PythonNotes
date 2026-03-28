In Python, numbers are a core data-type essential for performing arithmetic operations and calculations. It supports three types of numbers, including integers, floating-point numbers and complex numbers.
```Python
a = 4 # integer
b = 4.5 # float
c = 4j # complex number

print(type(a)) # <class 'int'>
print(type(b)) # <class 'float'>
print(type(c)) # <class 'complex'>
```

> **Integer**

It includes `-ve`, `+ve` numbers and zero.
```Python
pos_int = 5
neg_int = -13
zero = 0
```

```Python
# Addition
res = 5 + 3    # Output: 8

# Subtraction
res = 10 - 4   # Output: 6

# Multiplication
res = 7 * 6    # Output: 42

# Division
res = 15 / 4   # Output: 3.75

# Floor Division
res = 15 // 4  # Output: 3

# Modulus (%)
res = 15 % 4   # Output: 3 (because 15 divided by 4 gives remainder 3)

# Exponentiation (**)
res = 2 ** 3   # Output: 8 (because 2 raised to the power of 3 is 8)

# Absolute Value (abs)
res = abs(-10) # Output: 10 (absolute value of -10)

# Round (round)
res = round(3.14159, 2)  # Output: 3.14 (rounds to 2 decimal places)
```

> **Float**

It is specified by a decimal point. Optionally, the character e or E followed by a positive or negative integer may be appended to specify scientific notation. . Some examples of numbers that are represented as floats are 0.5 and -7.823457.

They can be created directly by entering a number with a decimal point, or by using operations such as division on integers. Extra zeros present at the number's end are ignored automatically.
```Python
a = 3.14      # A positive float
b = -0.99     # A negative float
c = 0.0       # A float value that represents zero
```

```Python
# Addition (float)
res = 3.5 + 2.2   # Output: 5.7

# Subtraction (float)
res = 7.8 - 4.3   # Output: 3.5

# Multiplication (float)
res = 5.5 * 2.0   # Output: 11.0

# Division (float)
res = 9.0 / 4.5   # Output: 2.0

# Floor Division (float)
res = 9.0 // 4.5  # Output: 2.0 (it returns the truncated quotient)

# Modulus (%) (float)
res = 9.0 % 4.5   # Output: 0.0 (remainder when divided)

# Exponentiation (float)
res = 2.5 ** 2    # Output: 6.25 (2.5 raised to the power of 2)

# Absolute Value (float)
res = abs(-7.4)   # Output: 7.4 (absolute value)

# Round (float)
res = round(3.14159, 2)  # Output: 3.14 (rounds to 2 decimal places)
```

> **Complex**

A complex number is a number that consists of real and imaginary parts. For example, 2 + 3j is a complex number where 2 is the real component, and 3 multiplied by j is an imaginary part.

```Python
# Addition (complex)
res = (3 + 4j) + (1 + 2j)   # Output: (4 + 6j)

# Subtraction (complex)
res = (5 + 6j) - (2 + 3j)   # Output: (3 + 3j)

# Multiplication (complex)
res = (2 + 3j) * (1 + 4j)   # Output: (-10 + 11j)

# Division (complex)
res = (8 + 6j) / (2 + 3j)   # Output: (2.0 + 0.0j)

# Exponentiation (complex)
res = (1 + 1j) ** 2    # Output: (0 + 2j) (raises the complex number to the power of 2)

# Absolute Value (complex)
res = abs(3 + 4j)   # Output: 5.0 (absolute value of a complex number, which is sqrt(3^2 + 4^2))

# Conjugate of a complex number
res = (3 + 4j).conjugate()   # Output: (3 - 4j) (negates the imaginary part)

# Real and Imaginary parts of a complex number
real = (3 + 4j).real   # Output: 3.0
imag = (3 + 4j).imag   # Output: 4.0
```

We can also use built-in functions like int(), float() to convert the data types.

