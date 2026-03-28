Loops in Python are used to repeat actions efficiently. The main types are For loops (counting through items) and While loops (based on conditions).

## For Loop

for loops are used for iterating over sequences like lists, tuples, strings and ranges.
- A for loop allows you to apply the same operation to every item within the loop.
- Using a for loop avoids the need to manually manage the index.
- A for loop can iterate over any iterable object, such as a dictionary, list or custom iterator.

```Python
s = ["Geeks", "for", "Geeks"]

# using for loop with list of strings
for i in s:
    print(i)
```

The `range()` is commonly used with for loops to generate a sequence of numbers. It can take one, two or three arguments:
- range(stop Generates numbers from 0 to stop-1.
- range(start, stop Generates numbers from start to stop-1.
- range(start, stop, step Generates numbers from start to stop-1, incrementing by step.

Loop control statements change execution from their normal sequence. When execution leaves a scope, all automatic objects that were created in that scope are destroyed. Python supports the following control statements.

> **enumerate()**

`enumerate()` function is used with the for loop to iterate over an iterable while also keeping track of index of each item. 

## While Loop

While Loop is used to execute a block of statements repeatedly until a given condition is satisfied. When the condition becomes false, the line immediately after the loop in the program is executed.

Syntax
```
while condition:
	statement(s)
```

The while loop will continue running the code block as long as the condition evaluates to True. Each time the loop executes, the condition is checked again. If it is True, the loop continues; if it is False, the loop terminates, and the program moves to the next statement after the loop.

When execution leaves a scope, all automatic objects that were created in that scope are destroyed.

> **continue** statement

The continue statement in Python is a loop control statement that skips the rest of the code inside the loop for the current iteration and moves to the next iteration immediately.

> **break** statement

The break statement in Python is used to exit or "break" out of a loop (either for or while loop) prematurely, before the loop has iterated through all its items or reached its condition. When the break statement is executed, the program immediately exits the loop, and the control moves to the next line of code after the loop.

> **pass** statement

when no action is needed but a block is still required, pass statement acts as a placeholder to keep the code syntactically valid.