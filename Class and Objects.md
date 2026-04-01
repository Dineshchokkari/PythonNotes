
> **Class**

A class in Python is a user-defined template for creating objects. It bundles data and functions together, making it easier to manage and use them. When we create a new class, we define a new type of object. We can then create multiple instances of this object type.

Classes are created using `class` keyword. Attributes are variables defined inside class and represent properties of the class. Attributes can be accessed using dot . operator
```Python
class Dog:
	sound = "bark"
```

> **Object**

An object is a specific instance of a class. It holds its own set of data (instance variables) and can invoke methods defined by its class. Multiple objects can be created from same class, each with its own unique attributes.

```Python
class Dog:
    sound = "bark"

dog1 = Dog() # Creating object from class
print(dog1.sound) # Accessing the class
```

> **Initiate with `__init__()`**

```Python
class Dog:
    species = "Canine"  # Class attribute

    def __init__(self, name, age):
        self.name = name  # Instance attribute
        self.age = age  # Instance attribute

# Creating an object of the Dog class
dog1 = Dog("Buddy", 3)

print(dog1.name)  
print(dog1.species)
```

## `self` Keyword
---
**self** is a fundamental concept when working with **object-oriented programming** (OOP). It represents the instance of the class being used. Whenever we create an object from a class, self refers to the current object instance. It is essential for accessing attributes and methods within the class.

**self** is used as the first parameter in instance methods to refer to the current object. It allows methods within the class to access and modify the object's attributes, making each object independent of others.

When we call a method on an object, self automatically gets passed to the method, referring to the specific instance of the class the method is acting upon. Without self, Python wouldn't know which instance’s attributes or methods to refer to.


> **Usage in Constructor**

`__init()` method is called when a new instance of the class is created. This method serves as the constructor for the class and initializes the object's attributes. The first argument of the __init__ method must always be self, as it allows the method to set instance attributes for the object being created.
```Python
class Subject:
    def __init__(self, attr1, attr2):
        self.attr1 = attr1
        self.attr2 = attr2

obj = Subject('Maths', 'Science')
print(obj.attr1)  
print(obj.attr2)
```

> **Usage in instance Methods**

Any method within the class that operates on an instance of the class must include self as the first parameter. It allows us to access the instance's attributes and other methods.

```Python
class Car:
    def __init__(self, model, color):
        self.model = model
        self.color = color

    def show(self):
        print("Model is", self.model)
        print("Color is", self.color)

# Creating instances of the class
audi = Car("Audi A4", "Blue")
ferrari = Car("Ferrari 488", "Green")

# Calling instance methods
audi.show()  
ferrari.show()
```

## Variables
---
In python, variables defined in a class can either be `class variables` or `instance variables`.
Class variables are shared by all objects of a class, whereas instance variables are unique to each object.
### Class Variables
---
These are variables that are shared across all instances of a class. It is defined at class level, outside any methods. All objects of class share same value for a class variable unless explicitly overridden in an object.

A class variable is a variable that belongs to the class itself rather than to any specific object. All instances of the class share the same copy of this variable.
- Defined inside the class but outside all methods
- Accessed using the class name or an object
- Memory is allocated only once
```Python
class Student:
    school = "ABC School"   # Class variable

s1 = Student()
s2 = Student()

print(s1.school)
print(s2.school)
```

> **Modifying Class Variable**

Class variables can be modified in two ways.
```Python
# Method 1: Modifying via instance (Not Recommended)
class CSStudent:
    stream = 'cse'          # Class variable

    def __init__(self, name, roll):
        self.name = name    # Instance variable
        self.roll = roll    # Instance variable

a.stream = 'ece'
print(a.stream) # ece
print(b.stream) # cse
```

When we change the class variable using an object (`a.stream`), Python does not change the class variable. Instead, it creates a new instance variable only for a. So:
- a gets its own stream = `ece`
- b still uses the original class variable value `cse`

```Python
# Method 2: Modifying via class name (Recommended)
class CSStudent:
    stream = 'cse'          # Class variable

    def __init__(self, name, roll):
        self.name = name    # Instance variable
        self.roll = roll    # Instance variable

CSStudent.stream = 'mech'
print(a.stream) # mech
print(b.stream) # mech
```

### Instance Variables
---
Instance variables are variables that belong to a specific object. Each object maintains its own copy of these variables.
- Defined inside methods (usually `__init__()`)
- Unique for each object
- Changes affect only that particular object
```Python
class Student:
    def __init__(self, name):
        self.name = name   # Instance variable

s1 = Student("Jake")
s2 = Student("Emily")

print(s1.name)
print(s2.name)
```


> **Class Variable vs Instance Variable**

```Python
class CSStudent:
    stream = 'cse'          # Class variable

    def __init__(self, name, roll):
        self.name = name    # Instance variable
        self.roll = roll    # Instance variable

# Creating objects
a = CSStudent('Rose', 1)
b = CSStudent('Nat', 2)

print(a.stream) # cse
print(b.stream) # cse
print(a.name) # Rose
print(b.name) # Nat
```

## Methods
---
Functions defined inside a class are called methods. 
Three important types of methods in Python are `class` methods, `static` methods, and instance `methods`. Each serves a distinct purpose and contributes to the overall flexibility and functionality of object-oriented programming in Python.

### Class Methods
---
Class methods are special types of methods in Python that are bound to a class rather than its instances. They are used when behavior logically belongs to the class but does not always require access to instance-specific data.

It receives the class itself as the first argument, conventionally named `cls`. It can access and modify class-level data and is often used to define factory methods. A factory method is a method that creates and returns an object of the class. It acts as an alternative constructor, allowing objects to be created in different ways.
```Python
from datetime import date

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def from_birth_year(cls, name, year):
        return cls(name, date.today().year - year)

p = Person.from_birth_year("Jake", 2000)
print(p.name)
print(p.age)
```
### Static Methods
---
A utility function is a helper function that performs a task related to the class but does not depend on class-level or instance-level data.

```Python
class Person:
    def __init__(self, age):
        self.age = age

    @staticmethod
    def is_adult(age):
        return age >= 18

print(Person.is_adult(20))
p = Person(16)
print(p.is_adult(p.age))
```

> **Class vs Static Method**

| Feature                 | Class Method                                                                                   | Static Method                                                                                                              |
| ----------------------- | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Decorator Used          | Defined using the `@classmethod `decorator.                                                    | Defined using the `@staticmethod` decorator.                                                                               |
| First Parameter         | Receives the class as the first parameter, conventionally named cls.                           | Does not receive any automatic first parameter like self or cls.                                                           |
| Access to Class Data    | Can access and modify class-level variables because it has access to cls.                      | Cannot access or modify class-level variables unless explicitly passed.                                                    |
| Access to Instance Data | Cannot directly access instance variables unless an object is passed manually.                 | Cannot access instance variables unless they are explicitly passed as arguments.                                           |
| Purpose                 | Commonly used to create factory methods or alternative constructors that return class objects. | Typically used to define utility functions that logically belong to the class but do not depend on class or instance data. |
| Object Creation         | Can create or modify class instances using cls.                                                | Does not create or modify class instances automatically.                                                                   |

>  **Class vs Instance vs Static Methods**

|Type|Decorator|Parameter|Instance Access|Class Access| Use Case                                                                                   |
|---|---|---|---|---|---|
|**Instance**|None needed|`self`|✅|✅| Operations on individual instances.                                                        |
|**Class**|`@classmethod`|`cls`|❌|✅| Factory methods, alternative constructors, or any method that deals with class-level data. |
|**Static**|`@staticmethod`|No `self` or `cls`|❌|❌| Utility methods that don’t need instance or class data                                     
