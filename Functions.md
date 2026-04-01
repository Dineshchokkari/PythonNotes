Python Functions are a block of statements that does a specific task. The idea is to put some commonly or repeatedly done task together and make a function so that instead of writing the same code again and again for different inputs, we can do the function calls to reuse code contained in it over and over again.

Syntax
```Python
def func_name(arg1, arg2): #defining a function
	# statements
	return # optional
	
func_name(arg1, arg2)
```

Arguments are the values passed inside the parenthesis of the function. A function can have any number of arguments separated by a comma.

> **Positional Arguments**

values are assigned to parameters based on their order in the function call.
```Python
def greet(name, age):
	print(f"My name is {name} and I am {age}")

greet("John", 30) # My name is John and I am 30
greet(30, "John") # My name is 30 and I am John
```

> **Keyword Arguments**

values are passed by explicitly specifying the parameter names, so the order doesn’t matter.
```Python
def greet(name, age):
	print(f"My name is {name} and I am {age}")

greet(name="John", age=30) # My name is John and I am 30
greet(age=30, name="John") # My name is John and I am 30
```


> **Default Arguments**

In Python, functions can have default arguments, which are parameters with predefined values. This means you don’t always need to pass every argument while calling a function.
- If you provide a value, Python uses it.
- If you skip it, the default value is used automatically.

```Python
def greet(name = "John"):
	print("Hi ", name)
	
greet("Jane") # Hi Jane
greet() # Hi John
```

**Note**:
- Non-default parameters must come before default parameters in the function definition.
- Positional arguments must come before keyword arguments when calling a function.
- If using keyword arguments, order does not matter.
- Each parameter must have only one value.
- Keyword name must match exactly with the function definition.
- For positional (non-keyword) arguments, order matters strictly.

> **Variable Arguments using `*args` and `**kwargs`**

In Python, `*args` and `**kwargs` are used to allow functions to accept an arbitrary number of arguments. These features provide great flexibility when designing functions that need to handle a varying number of inputs.

```Python
# *args example
def print_sum(*numbers):
	print(sum(numbers))	
	
print_sum(1, 2, 3, 4, 5, 6, 7, 8) #36
print_sum(1, 2, 3, 4, 5, 6, 7) #28

# **kwargs example
def fun(**kwargs):
    for k, val in kwargs.items():
        print(k, val)

fun(a=1, b=2, c=3)
```

> **Anonymous Functions**

An anonymous function means that a function is without a name. `def` keyword is used to define the normal functions and `lambda` is used to create anonymous functions.
```Python
def c1(x): return x*x*x   
c2 = lambda x : x*x*x  

print(c1(7))
print(c2(7))
```

> **Pass by Reference and Pass by Value**

Variables are references to objects. When we pass them to a function, behavior depends on whether the object is mutable (like lists, dictionaries) or immutable (like integers, strings, tuples).

- **Mutable objects:** Changes inside the function affect the original object.
- **Immutable objects:** The original value remains unchanged.
```Python
def myFun(x):
    x[0] = 20

lst = [10, 11, 12, 13]
myFun(lst) 
print(lst) #[20, 11, 12, 13]

def myFun2(x):
    x = 20

a = 10
myFun2(a)
print(a) # 10
```

Python always passes objects by reference. If the object is changeable (like a list), the function can modify it. If it’s not changeable (like a number or string), the function cannot change it.

> **`return` statement**

A return statement ends a function and sends a value back to the caller. It can return any data type, multiple values (packed into a tuple), or None if no value is given.

```Python
def return_val(num):
	return num # it is not necessary to catch it.
```

> **`yield` statement**

In Python, **yield keyword** is used to create **generators**, which are special types of iterators that allow values to be produced lazily, one at a time, instead of returning them all at once. This makes yield particularly useful for handling large datasets efficiently, as it allows iteration without storing entire sequence in memory.

- **Supports Infinite Sequences:** Lets you define generators that can yield an endless stream of values (e.g., Fibonacci series, real-time data).
- **Enables Coroutine-like Behavior:** Useful in asynchronous programming where a function needs to pause and resume later.
- **Improves Testability:** Makes functions easier to test by breaking execution into predictable steps.
- **Builds Modular Pipelines:** Encourages cleaner architecture by separating data production and consumption stages.
- **Fine-Grained Control Over Iteration:** Lets you customize exactly when and how values are produced, offering more flexibility than regular functions.

```Python
# Syntax
def yield_val():
	yield val
```

**value** is the item that will be produced (yielded) by generator each time you call next() on it.

```Python
# Program to generate numbers sequentially
def fun(m):
    for i in range(m):
        yield i  

# call the generator function
for n in fun(5):
    print(n)
```

**Generator functions** behave like normal functions but use `yield` instead of `return`. They automatically create `__iter__()` and `__next__()` methods, making them `iterable` objects.

```Python
def my_generator():
    yield "Hello world!!"
    yield "This is a Generator function"

g = my_generator()
print(type(g))  # <class 'generator'>
print(next(g))  # "Hello world!!"
print(next(g))  # "This is a Generator function"
```

- **Memory Efficiency:** Since the function doesn’t store the entire result in memory, it is useful for handling large data sets.
- **State Retention:** Variables inside the generator function retain their state between calls.
- **Lazy Evaluation:** Values are generated on demand rather than all at once.