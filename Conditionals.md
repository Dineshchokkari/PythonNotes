Conditional statements in Python are used to execute certain blocks of code based on specific conditions. These statements help control the flow of a program, making it behave differently in different situations.
# If Condition

If statement is the simplest form of a conditional statement. It executes a block of code if the given condition is true.

```Python
age = 20
if age >= 18:
    print("Eligible to vote.")
```

> **Short Hand If**

```Python
age = 19
if age > 18: print("Eligible to Vote.")
```

## If-else Condition

This allows us to specify a block of code that will execute if the condition(s) associated with an if or elif statement evaluates to False. Else block provides a way to handle all other cases that don't meet the specified conditions

```Python
age = 10
if age <= 12:
    print("Travel for free.")
else:
    print("Pay for ticket.")
```

> **Short Hand If-else**

```Python
marks = 45
res = "Pass" if marks >= 40 else "Fail"
print(f"Result: {res}")
```

## elif Statement

elif statement in Python stands for "else if." It allows us to check multiple conditions, providing a way to execute different blocks of code based on which condition is true. Using elif statements makes our code more readable and efficient by eliminating the need for multiple nested if statements.

```Python
age = 25
if age <= 12:
    print("Child.")
elif age <= 19:
    print("Teenager.")
elif age <= 35:
    print("Young adult.")
else:
    print("Adult.")
```
## Match Case Statement

The  match-case syntax is based on structural pattern matching, which enables matching against data structures like sequences, mappings and even classes, providing more granularity and flexibility in handling various conditions. This feature is particularly useful when dealing with different types of data in a clear and organized manner.

Syntax
```
match subject:  
	case pattern1:  
		# Code block if pattern1 matches  
	case pattern2:  
		# Code block if pattern2 matches  
	case _:  
		# Default case (wildcard) if no other pattern matches
```

> **Match Case Statements with Constants**

Matching constants is one of the simplest uses of the match-case statement. It checks if a variable matches specific constant values and allows for different actions based on the matched constant.
```Python
def greet(person):
    match person:
        case "A":
            print("Hello, A!")
        case "B":
            print("Hello, B!")
        case _:
            print("Hello, stranger!")

greet("A")
greet("B")
```
