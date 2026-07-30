## Part 1: Python Basics (Q1 - Q10)

---

## Q1. What is Python?

### Answer:

Python is a **high-level, interpreted, general-purpose programming language** known for its simple syntax and readability.

It supports multiple programming paradigms like:

* Object-Oriented Programming (OOP)
* Functional Programming
* Procedural Programming

Python is widely used in:

* Web Development (Django, Flask)
* Data Science
* Artificial Intelligence & Machine Learning
* Automation
* Scripting

### Interview Answer:

> "Python is a high-level interpreted programming language that focuses on code readability and simplicity. It supports OOP and is widely used in web development, automation, data science, and AI applications."

---

# Q2. What are the main features of Python?

### Answer:

Important features of Python:

### 1. Easy Syntax

Python syntax is simple and close to English.

Example:

```python
print("Hello Python")
```

### 2. Interpreted Language

Python code executes line by line using the Python interpreter.

### 3. Dynamically Typed

We don't need to declare variable types.

Example:

```python
x = 10
x = "Hello"
```

### 4. Object-Oriented

Everything in Python is an object.

Example:

```python
num = 10
print(type(num))
```

Output:

```
<class 'int'>
```

### 5. Large Standard Library

Python provides many built-in modules.

Example:

```python
import math
```

---

# Q3. Is Python compiled or interpreted?

### Answer:

Python is mainly an **interpreted language**, but internally Python uses both compilation and interpretation.

Execution process:

```
Python Code (.py)
        |
        ↓
Bytecode (.pyc)
        |
        ↓
Python Virtual Machine (PVM)
        |
        ↓
Output
```

First Python converts source code into bytecode, then PVM executes it.

### Interview Answer:

> "Python is an interpreted language because execution happens through an interpreter. Internally, Python first compiles source code into bytecode and then executes that bytecode using the Python Virtual Machine."

---

# Q4. What is the difference between Python 2 and Python 3?

| Python 2               | Python 3                 |
| ---------------------- | ------------------------ |
| Older version          | Latest version           |
| Print is statement     | Print is function        |
| Supports ASCII default | Supports Unicode default |
| xrange() available     | range() available        |
| No longer maintained   | Actively maintained      |

Example:

Python 2:

```python
print "Hello"
```

Python 3:

```python
print("Hello")
```

---

# Q5. What are Python data types?

### Answer:

Python data types define what type of value a variable stores.

Main categories:

### 1. Numeric Types

```python
int
float
complex
```

Example:

```python
a = 10
b = 10.5
c = 2+3j
```

---

### 2. Sequence Types

```
str
list
tuple
range
```

Example:

```python
name="Python"
numbers=[1,2,3]
```

---

### 3. Mapping Type

Dictionary:

```python
student={
"name":"Ram",
"age":20
}
```

---

### 4. Set Type

```python
set
frozenset
```

Example:

```python
s={1,2,3}
```

---

### 5. Boolean

```python
True
False
```

---

### 6. None Type

```python
None
```

---

# Q6. Difference between list and tuple?

### Answer:

| List                     | Tuple                 |
| ------------------------ | --------------------- |
| Mutable                  | Immutable             |
| Uses []                  | Uses ()               |
| Slower compared to tuple | Faster                |
| More memory              | Less memory           |
| Cannot be dictionary key | Can be dictionary key |

Example:

List:

```python
a=[1,2,3]
a.append(4)
```

Tuple:

```python
b=(1,2,3)
```

Tuple cannot be changed.

### Interview Answer:

> "List is mutable, meaning we can modify its elements. Tuple is immutable, meaning once created it cannot be changed. Tuple is faster and consumes less memory than list."

---

# Q7. What is the difference between mutable and immutable objects?

### Mutable:

Objects whose values can be changed after creation.

Examples:

* list
* dictionary
* set

Example:

```python
lst=[1,2,3]

lst.append(4)

print(lst)
```

Output:

```
[1,2,3,4]
```

---

### Immutable:

Objects whose values cannot be changed.

Examples:

* int
* float
* string
* tuple

Example:

```python
x=10
x=20
```

Here a new object is created.

---

# Q8. What is the difference between == and is operator?

### == (Equality Operator)

Checks values.

Example:

```python
a=[1,2]
b=[1,2]

print(a==b)
```

Output:

```
True
```

---

### is (Identity Operator)

Checks memory location.

Example:

```python
print(a is b)
```

Output:

```
False
```

Because both lists have different memory addresses.

### Interview Answer:

> "== compares values, while is compares object identity or memory location."

---

# Q9. What is a variable in Python?

### Answer:

A variable is a name used to store a value in memory.

Example:

```python
name="Sandhya"
age=22
```

Here:

```
name → stores string value
age → stores integer value
```

Python variables do not require data type declaration.

Example:

```python
x=10
x="Python"
```

---

# Q10. What is dynamic typing in Python?

### Answer:

Dynamic typing means Python automatically decides the data type during runtime.

Example:

```python
x=100

print(type(x))
```

Output:

```
<class 'int'>
```

Later:

```python
x="Hello"

print(type(x))
```

Output:

```
<class 'str'>
```

We don't specify:

```python
int x=100
```

like C or Java.

### Interview Answer:

> "Python is dynamically typed because variable types are determined at runtime, and we don't need to declare the data type explicitly."

---

## Revision Shortcut (Q1-Q10)

| Question             | Key Point                       |
| -------------------- | ------------------------------- |
| Python               | High-level interpreted language |
| Features             | Simple, OOP, dynamic, libraries |
| Compiled/interpreted | Bytecode + PVM                  |
| Python2 vs Python3   | Print, Unicode, range           |
| Data types           | int, list, dict, set etc.       |
| List vs Tuple        | Mutable vs Immutable            |
| Mutable              | Can change                      |
| Immutable            | Cannot change                   |
| == vs is             | Value vs Memory                 |
| Dynamic typing       | Type decided runtime            |

---


# Part 2: Python Interview Questions (Q11 - Q20)

## Topic: Functions, Arguments, Lambda, Scope, OOP Basics

---

# Q11. What is a function in Python?

### Answer:

A **function is a block of reusable code that performs a specific task**.

Instead of writing the same code multiple times, we create a function and call it whenever required.

### Syntax:

```python
def function_name():
    # code
```

### Example:

```python
def greet():
    print("Hello Python")

greet()
```

Output:

```
Hello Python
```

### Advantages of Functions:

* Code reusability
* Reduces code duplication
* Improves readability
* Easier debugging and maintenance

### Interview Answer:

> "A function is a reusable block of code that performs a specific task. In Python, functions are created using the def keyword."

---

# Q12. What are the different types of functions in Python?

### Answer:

Python functions are mainly divided into four types:

## 1. Built-in Functions

Functions already provided by Python.

Examples:

```python
print()
len()
type()
input()
```

---

## 2. User-defined Functions

Functions created by developers.

Example:

```python
def add(a,b):
    return a+b
```

---

## 3. Lambda Functions

Anonymous functions without a name.

Example:

```python
square=lambda x:x*x

print(square(5))
```

Output:

```
25
```

---

## 4. Recursive Functions

A function that calls itself.

Example:

```python
def count(n):
    if n==0:
        return
    print(n)
    count(n-1)

count(5)
```

Output:

```
5
4
3
2
1
```

---

# Q13. Difference between parameters and arguments?

### Answer:

### Parameter:

The variables written during function definition are called parameters.

Example:

```python
def add(a,b):
    return a+b
```

Here:

```
a and b are parameters
```

---

### Argument:

The actual values passed during function calling are called arguments.

Example:

```python
add(10,20)
```

Here:

```
10 and 20 are arguments
```

### Interview Answer:

> "Parameters are variables defined in the function declaration, while arguments are actual values passed when calling the function."

---

# Q14. What are different types of arguments in Python?

Python supports four types of arguments:

---

## 1. Positional Arguments

Values are passed according to position.

Example:

```python
def student(name,age):
    print(name,age)

student("Ram",20)
```

Output:

```
Ram 20
```

---

## 2. Keyword Arguments

Values are passed using parameter names.

Example:

```python
student(age=20,name="Ram")
```

Order does not matter.

---

## 3. Default Arguments

A parameter has a default value.

Example:

```python
def greet(name="Guest"):
    print(name)

greet()
```

Output:

```
Guest
```

---

## 4. Variable Length Arguments

Used when the number of arguments is unknown.

### *args

Stores multiple positional arguments as tuple.

Example:

```python
def add(*numbers):
    print(numbers)

add(1,2,3,4)
```

Output:

```
(1,2,3,4)
```

---

### **kwargs

Stores multiple keyword arguments as dictionary.

Example:

```python
def info(**data):
    print(data)

info(name="Ram",age=20)
```

Output:

```
{'name':'Ram','age':20}
```

---

# Q15. What is the difference between *args and **kwargs?

### Answer:

| *args                                 | **kwargs                           |
| ------------------------------------- | ---------------------------------- |
| Accepts variable positional arguments | Accepts variable keyword arguments |
| Stores data as tuple                  | Stores data as dictionary          |
| Uses single `*`                       | Uses double `**`                   |

Example:

### *args:

```python
def test(*args):
    print(args)

test(10,20,30)
```

Output:

```
(10,20,30)
```

---

### **kwargs:

```python
def test(**kwargs):
    print(kwargs)

test(name="John",age=25)
```

Output:

```
{'name':'John','age':25}
```

---

# Q16. What is a lambda function in Python?

### Answer:

A lambda function is an **anonymous function (function without a name)** used for small operations.

### Syntax:

```python
lambda arguments : expression
```

Example:

```python
square=lambda x:x*x

print(square(5))
```

Output:

```
25
```

---

### Features of Lambda:

* No function name
* Uses lambda keyword
* Contains only one expression
* Automatically returns value
* Mostly used with:

  * map()
  * filter()
  * reduce()
  * sorted()

---

# Q17. Difference between normal function and lambda function?

| Normal Function                 | Lambda Function             |
| ------------------------------- | --------------------------- |
| Created using def               | Created using lambda        |
| Has a name                      | Usually anonymous           |
| Can contain multiple statements | Only one expression         |
| Uses return keyword             | Automatically returns value |
| Used for large logic            | Used for small operations   |

Example:

Normal function:

```python
def add(a,b):
    return a+b
```

Lambda:

```python
add=lambda a,b:a+b
```

---

# Q18. What are local and global variables?

### Local Variable:

A variable created inside a function.

It can only be accessed inside that function.

Example:

```python
def test():
    x=10
    print(x)

test()
```

---

### Global Variable:

A variable created outside a function.

It can be accessed throughout the program.

Example:

```python
x=100

def test():
    print(x)

test()
```

---

### Using global keyword:

```python
x=10

def change():
    global x
    x=20

change()

print(x)
```

Output:

```
20
```

---

# Q19. What is the LEGB rule in Python?

### Answer:

LEGB defines the order in which Python searches for a variable.

LEGB means:

## L → Local

Inside current function

## E → Enclosing

Inside outer function (nested functions)

## G → Global

At module level

## B → Built-in

Python predefined names

Example:

```python
print(len("Python"))
```

Here:

```
len() comes from Built-in scope
```

---

### Interview Answer:

> "Python follows the LEGB rule to resolve variable names. It searches Local, Enclosing, Global, and Built-in scopes in this order."

---

# Q20. What is Object-Oriented Programming (OOP)?

### Answer:

Object-Oriented Programming is a programming approach where programs are designed using **objects and classes**.

An object represents a real-world entity containing:

* Data (attributes)
* Behavior (methods)

Example:

Real-world:

```
Car
```

Attributes:

```
color
model
speed
```

Methods:

```
start()
stop()
drive()
```

Python example:

```python
class Car:

    def start(self):
        print("Car started")

car1=Car()

car1.start()
```

---

## Four main pillars of OOP:

1. Encapsulation
2. Abstraction
3. Inheritance
4. Polymorphism

---

### Interview Answer:

> "OOP is a programming paradigm based on classes and objects. It helps organize code, improve reusability, and represent real-world entities."

---

# Quick Revision (Q11-Q20)

| Question        | Main Point                                |
| --------------- | ----------------------------------------- |
| Function        | Reusable block of code                    |
| Function types  | Built-in, user-defined, lambda, recursive |
| Parameter       | Variable in function definition           |
| Argument        | Value passed during call                  |
| Arguments types | Positional, keyword, default, variable    |
| *args           | Multiple positional values                |
| **kwargs        | Multiple keyword values                   |
| Lambda          | Anonymous one-expression function         |
| Scope           | Local, Global, LEGB                       |
| OOP             | Class + Object based programming          |

---


# Part 3: Python Interview Questions (Q21 - Q30)

## Topic: OOP Concepts (Class, Object, Constructor, Inheritance, Encapsulation, Abstraction, Polymorphism)

---

# Q21. What is a class in Python?

### Answer:

A **class is a blueprint or template used to create objects**.

A class defines:

* Attributes (data/properties)
* Methods (functions/behavior)

Example:

```python
class Student:

    name = "Ram"
    age = 20

    def study(self):
        print("Student is studying")
```

Here:

```
Student → Class
name, age → Attributes
study() → Method
```

### Interview Answer:

> "A class is a blueprint for creating objects. It defines the properties and behaviors that objects will have."

---

# Q22. What is an object in Python?

### Answer:

An **object is an instance of a class**.

When we create an object, memory is allocated for that object.

Example:

```python
class Student:

    def study(self):
        print("Studying")


student1 = Student()

student1.study()
```

Here:

```
Student → Class
student1 → Object
```

### Real-life Example:

Class:

```
Car
```

Objects:

```
BMW
Audi
Tesla
```

All are cars but have different properties.

---

### Interview Answer:

> "An object is an instance of a class that contains data and methods defined by the class."

---

# Q23. What is the difference between class and object?

| Class                            | Object                      |
| -------------------------------- | --------------------------- |
| Blueprint/template               | Instance of class           |
| Logical entity                   | Physical entity             |
| Does not consume memory for data | Occupies memory             |
| Defines attributes and methods   | Uses attributes and methods |

Example:

```python
class Mobile:
    pass


phone1 = Mobile()
phone2 = Mobile()
```

Here:

```
Mobile → Class

phone1, phone2 → Objects
```

---

# Q24. What is the **init**() method in Python?

### Answer:

`__init__()` is a **constructor method** that automatically executes when an object is created.

It is used to initialize object attributes.

Example:

```python
class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age


s1 = Student("Rahul", 21)

print(s1.name)
print(s1.age)
```

Output:

```
Rahul
21
```

---

### Important Points:

* It runs automatically
* It initializes object data
* It is called constructor in Python
* It takes `self` as first parameter

---

# Q25. What is self in Python?

### Answer:

`self` represents the **current object of a class**.

It is used to access:

* Object variables
* Object methods

Example:

```python
class Student:

    def display(self):
        print("Hello")


s1 = Student()

s1.display()
```

Internally Python converts:

```python
s1.display()
```

into:

```python
Student.display(s1)
```

So `self` receives the object.

---

### Interview Answer:

> "self is a reference to the current object. It allows us to access instance variables and methods inside a class."

---

# Q26. What are the types of variables in a class?

Python has mainly three types of variables:

---

## 1. Instance Variables

Variables that belong to individual objects.

Example:

```python
class Student:

    def __init__(self,name):
        self.name=name


s1=Student("Amit")
s2=Student("Rahul")
```

Here:

```
s1.name = Amit
s2.name = Rahul
```

Different objects have different values.

---

## 2. Class Variables

Variables shared by all objects.

Example:

```python
class Student:

    school="ABC School"

    def __init__(self,name):
        self.name=name
```

Here:

```
school is common for all students
```

---

## 3. Local Variables

Variables created inside methods.

Example:

```python
def show():
    x=10
```

`x` exists only inside the method.

---

# Q27. What are the types of methods in Python classes?

Python has three types of methods:

---

## 1. Instance Method

Works with object data.

Uses:

```python
self
```

Example:

```python
class Student:

    def show(self):
        print("Instance method")
```

---

## 2. Class Method

Works with class-level data.

Uses:

```python
cls
```

Decorator:

```python
@classmethod
```

Example:

```python
class Student:

    school="ABC"

    @classmethod
    def display(cls):
        print(cls.school)
```

---

## 3. Static Method

Independent method that does not access class/object data.

Decorator:

```python
@staticmethod
```

Example:

```python
class Math:

    @staticmethod
    def add(a,b):
        return a+b
```

---

# Q28. Difference between instance method, class method, and static method?

| Instance Method        | Class Method              | Static Method             |
| ---------------------- | ------------------------- | ------------------------- |
| Uses self              | Uses cls                  | No self/cls               |
| Works with object data | Works with class data     | Utility function          |
| Called using object    | Called using class/object | Called using class/object |

Example:

```python
class Demo:

    x=100

    def instance(self):
        pass

    @classmethod
    def class_method(cls):
        pass

    @staticmethod
    def static_method():
        pass
```

---

# Q29. What is inheritance in Python?

### Answer:

Inheritance allows one class to acquire properties and methods of another class.

It promotes:

* Code reusability
* Less duplication
* Better organization

Example:

```python
class Animal:

    def sound(self):
        print("Animal sound")


class Dog(Animal):

    def bark(self):
        print("Barking")


dog=Dog()

dog.sound()
dog.bark()
```

Output:

```
Animal sound
Barking
```

Here:

```
Animal → Parent Class

Dog → Child Class
```

---

# Q30. What are different types of inheritance in Python?

Python supports five types of inheritance:

---

## 1. Single Inheritance

One parent → One child

```
A
|
B
```

Example:

```python
class A:
    pass

class B(A):
    pass
```

---

## 2. Multiple Inheritance

Multiple parents → One child

```
A   B
 \ /
  C
```

Example:

```python
class A:
    pass

class B:
    pass

class C(A,B):
    pass
```

---

## 3. Multilevel Inheritance

Grandparent → Parent → Child

```
A
|
B
|
C
```

---

## 4. Hierarchical Inheritance

One parent → Multiple children

```
    A
   / \
  B   C
```

---

## 5. Hybrid Inheritance

Combination of multiple inheritance types.

---

# Quick Revision (Q21-Q30)

| Question             | Key Point                                          |
| -------------------- | -------------------------------------------------- |
| Class                | Blueprint                                          |
| Object               | Instance of class                                  |
| Class vs Object      | Template vs Real entity                            |
| **init**             | Constructor                                        |
| self                 | Current object reference                           |
| Variables            | Instance, Class, Local                             |
| Methods              | Instance, Class, Static                            |
| Inheritance          | Reusing parent code                                |
| Types of inheritance | Single, Multiple, Multilevel, Hierarchical, Hybrid |

---


# Part 4: Python Interview Questions (Q31 - Q40)

## Topic: Encapsulation, Abstraction, Polymorphism, Decorators, Iterator, Generator, Exception Handling

---

# Q31. What is encapsulation in Python?

### Answer:

**Encapsulation means wrapping data (variables) and methods into a single unit (class) and controlling access to data.**

The main purpose is:

* Data security
* Prevent direct modification
* Better code organization

Example:

```python id="x4m0df"
class BankAccount:

    def __init__(self, balance):
        self.__balance = balance

    def get_balance(self):
        return self.__balance


account = BankAccount(5000)

print(account.get_balance())
```

Output:

```
5000
```

Here:

```python id="1y4p4k"
__balance
```

is a private variable.

Direct access:

```python id="i9m4xy"
account.__balance
```

will not work.

---

### Types of access modifiers in Python:

## 1. Public

Accessible everywhere.

Example:

```python
self.name
```

---

## 2. Protected

Starts with single underscore `_`

Example:

```python
self._salary
```

Conventionally used inside class and subclasses.

---

## 3. Private

Starts with double underscore `__`

Example:

```python
self.__balance
```

Only accessible inside class.

---

### Interview Answer:

> "Encapsulation is the process of binding data and methods together inside a class and restricting direct access to data using access modifiers."

---

# Q32. What is abstraction in Python?

### Answer:

**Abstraction means hiding internal implementation details and showing only essential information to the user.**

Real-life example:

ATM machine:

You only use:

* Withdraw
* Deposit
* Check balance

You don't know the internal banking process.

---

In Python, abstraction is achieved using:

```python
ABC
abstractmethod
```

from the `abc` module.

Example:

```python
from abc import ABC, abstractmethod


class Vehicle(ABC):

    @abstractmethod
    def start(self):
        pass


class Car(Vehicle):

    def start(self):
        print("Car starts with key")


car = Car()

car.start()
```

Output:

```
Car starts with key
```

---

Important rules:

1. Abstract class cannot create an object.

```python
Vehicle()
```

Not allowed.

2. Child class must implement abstract methods.

3. Abstract methods only define a structure, not implementation.

---

### Interview Answer:

> "Abstraction hides implementation details and exposes only necessary functionality. In Python, it is implemented using abstract classes and abstract methods."

---

# Q33. Difference between encapsulation and abstraction?

| Encapsulation                    | Abstraction                     |
| -------------------------------- | ------------------------------- |
| Hides data                       | Hides implementation details    |
| Focuses on data security         | Focuses on complexity reduction |
| Achieved using private variables | Achieved using abstract classes |
| Example: Bank account balance    | Example: ATM operation          |

### Simple Difference:

**Encapsulation → How to protect data?**

**Abstraction → How to hide complexity?**

---

# Q34. What is polymorphism in Python?

### Answer:

Polymorphism means:

> "One name, multiple forms."

It allows the same method or operator to behave differently in different situations.

Types:

1. Method Overriding
2. Method Overloading (Python handles differently)

---

## Example of Method Overriding:

```python
class Animal:

    def sound(self):
        print("Animal sound")


class Dog(Animal):

    def sound(self):
        print("Bark")


dog = Dog()

dog.sound()
```

Output:

```
Bark
```

Child class changes parent method behavior.

---

### Interview Answer:

> "Polymorphism allows the same interface to perform different operations depending on the object."

---

# Q35. Does Python support method overloading?

### Answer:

Python does **not support traditional method overloading** like Java or C++.

Example (not possible):

```python
class Calculator:

    def add(self,a,b):
        pass

    def add(self,a,b,c):
        pass
```

The second method replaces the first one.

---

Python achieves similar behavior using:

## 1. Default arguments

```python
class Calculator:

    def add(self,a,b,c=0):
        return a+b+c


obj=Calculator()

print(obj.add(10,20))
print(obj.add(10,20,30))
```

Output:

```
30
60
```

---

## 2. *args

```python
def add(*numbers):

    return sum(numbers)
```

---

### Interview Answer:

> "Python does not support method overloading directly. We achieve similar functionality using default arguments and variable-length arguments."

---

# Q36. What is a decorator in Python?

### Answer:

A decorator is a function that **takes another function as input and extends its behavior without modifying the original function.**

Decorators use:

* Higher-order functions
* Closures

Example:

```python
def decorator(func):

    def wrapper():
        print("Before function")
        func()
        print("After function")

    return wrapper


@decorator
def hello():
    print("Hello")


hello()
```

Output:

```
Before function
Hello
After function
```

---

Real-world uses:

* Authentication
* Logging
* Performance measurement
* Permission checking

Examples in Django:

```python
@login_required
```

---

### Interview Answer:

> "A decorator is a function that modifies or extends another function's behavior without changing its code."

---

# Q37. What is an iterator in Python?

### Answer:

An iterator is an object that allows us to traverse elements one by one.

It implements:

```python
__iter__()
__next__()
```

Example:

```python
numbers=[10,20,30]

iterator=iter(numbers)

print(next(iterator))
print(next(iterator))
```

Output:

```
10
20
```

---

When elements finish:

```python
next(iterator)
```

raises:

```
StopIteration
```

---

### Interview Answer:

> "An iterator is an object that allows sequential access to elements using the iter() and next() methods."

---

# Q38. What is a generator in Python?

### Answer:

A generator is a special type of iterator that generates values one at a time using the `yield` keyword.

Example:

```python
def numbers():

    yield 1
    yield 2
    yield 3


for num in numbers():
    print(num)
```

Output:

```
1
2
3
```

---

Advantages:

* Memory efficient
* Lazy evaluation
* Suitable for large data

Example:

Reading a huge file:

Instead of loading the whole file into memory, generator reads line by line.

---

### Difference:

| Iterator                       | Generator             |
| ------------------------------ | --------------------- |
| Created using class            | Created using yield   |
| Requires **iter** and **next** | Automatically created |
| More code                      | Less code             |
| Less memory efficient          | More memory efficient |

---

# Q39. What is exception handling in Python?

### Answer:

Exception handling is used to handle runtime errors and prevent program termination.

Python uses:

* try
* except
* else
* finally

Example:

```python
try:

    a=10
    b=0

    print(a/b)

except ZeroDivisionError:

    print("Cannot divide by zero")
```

Output:

```
Cannot divide by zero
```

---

## finally block:

Always executes.

Example:

```python
try:
    print(10/2)

finally:
    print("Execution completed")
```

Output:

```
5
Execution completed
```

---

### Interview Answer:

> "Exception handling is a mechanism to handle runtime errors gracefully using try, except, else, and finally blocks."

---

# Q40. Difference between error and exception?

| Error                    | Exception                  |
| ------------------------ | -------------------------- |
| Usually serious problem  | Runtime problem            |
| Cannot always be handled | Can be handled             |
| Example: Syntax error    | Example: ZeroDivisionError |

Examples:

### Error:

```python
print("Hello"
```

Missing bracket causes SyntaxError.

---

### Exception:

```python
10/0
```

Causes:

```
ZeroDivisionError
```

---

# Quick Revision (Q31-Q40)

| Question                     | Main Point                       |
| ---------------------------- | -------------------------------- |
| Encapsulation                | Data hiding                      |
| Abstraction                  | Hide implementation              |
| Encapsulation vs Abstraction | Security vs Complexity reduction |
| Polymorphism                 | One name multiple forms          |
| Overloading                  | Not directly supported           |
| Decorator                    | Modify function behavior         |
| Iterator                     | One-by-one traversal             |
| Generator                    | Iterator using yield             |
| Exception Handling           | Handle runtime errors            |
| Error vs Exception           | Compile issue vs runtime issue   |

---

# Part 5: Python Interview Questions (Q41 - Q50)

## Topic: Memory Management, Copy, Comprehension, Modules, Packages, Recursion, Virtual Environment, Coding Basics

---

# Q41. How does Python manage memory?

### Answer:

Python uses **automatic memory management**. Developers do not need to manually allocate or release memory.

Python manages memory using:

1. **Private Heap**
2. **Python Memory Manager**
3. **Garbage Collector**

---

## 1. Private Heap

All Python objects and data are stored in a private heap.

Example:

```python id="x8q1e2"
a = [1,2,3]
```

The list object is stored in memory heap.

---

## 2. Python Memory Manager

It manages allocation of memory for Python objects.

---

## 3. Garbage Collector

It removes unused objects from memory.

Example:

```python id="2t6s9p"
a = [1,2,3]

del a
```

After deletion, memory can be released by garbage collector.

---

### Interview Answer:

> "Python manages memory automatically using a private heap, memory manager, and garbage collector. The garbage collector removes unused objects and frees memory."

---

# Q42. What is garbage collection in Python?

### Answer:

Garbage collection is the process of automatically removing objects that are no longer referenced by the program.

Python mainly uses:

* Reference counting
* Generational garbage collection

---

## Reference Counting:

Python keeps track of how many references point to an object.

Example:

```python id="z4km2n"
a=[1,2,3]

b=a
```

Here:

```
a → list object
b → same list object
```

Reference count = 2

If:

```python id="f4b7cy"
del a
del b
```

Reference count becomes 0.

The object is removed.

---

### Interview Answer:

> "Garbage collection automatically identifies and removes unused objects from memory to prevent memory leaks."

---

# Q43. What is the difference between shallow copy and deep copy?

### Answer:

Both are used to create copies of objects.

Python provides:

```python id="6c7o9v"
copy module
```

---

# Shallow Copy

Creates a new object but keeps references to nested objects.

Example:

```python id="v7r5pf"
import copy

a=[[1,2],[3,4]]

b=copy.copy(a)

b[0][0]=100

print(a)
```

Output:

```
[[100,2],[3,4]]
```

Because inner lists are shared.

---

# Deep Copy

Creates a completely independent copy including nested objects.

Example:

```python id="4p7j6n"
import copy

a=[[1,2],[3,4]]

b=copy.deepcopy(a)

b[0][0]=100

print(a)
```

Output:

```
[[1,2],[3,4]]
```

Original object is unchanged.

---

### Difference:

| Shallow Copy             | Deep Copy                  |
| ------------------------ | -------------------------- |
| Copies outer object only | Copies complete object     |
| Nested objects shared    | Nested objects independent |
| Faster                   | Slower                     |
| Uses copy()              | Uses deepcopy()            |

---

# Q44. What is list comprehension in Python?

### Answer:

List comprehension is a short and efficient way to create lists.

Normal way:

```python id="q3l9zf"
numbers=[]

for i in range(5):
    numbers.append(i)

print(numbers)
```

Output:

```
[0,1,2,3,4]
```

---

Using list comprehension:

```python id="t4f8cn"
numbers=[i for i in range(5)]

print(numbers)
```

Output:

```
[0,1,2,3,4]
```

---

With condition:

```python id="4kzq8m"
even=[i for i in range(10) if i%2==0]

print(even)
```

Output:

```
[0,2,4,6,8]
```

---

### Interview Answer:

> "List comprehension is a concise way to create lists using a single line of code. It improves readability and reduces code length."

---

# Q45. What are map(), filter(), and reduce() functions?

### Answer:

These are functional programming functions used to process collections.

---

# 1. map()

Used to apply a function to every element.

Syntax:

```python id="6r2v7k"
map(function, iterable)
```

Example:

```python id="m4u8z3"
numbers=[1,2,3,4]

result=list(map(lambda x:x*2,numbers))

print(result)
```

Output:

```
[2,4,6,8]
```

---

# 2. filter()

Used to select elements based on a condition.

Example:

```python id="6z2t4j"
numbers=[1,2,3,4,5]

result=list(filter(lambda x:x%2==0,numbers))

print(result)
```

Output:

```
[2,4]
```

---

# 3. reduce()

Used to reduce a sequence into a single value.

It comes from:

```python id="7f9q1s"
functools module
```

Example:

```python id="5r7qk1"
from functools import reduce

numbers=[1,2,3,4]

result=reduce(lambda x,y:x+y,numbers)

print(result)
```

Output:

```
10
```

---

# Q46. What is recursion in Python?

### Answer:

Recursion is a technique where a function calls itself.

Example:

```python id="g0w4hj"
def factorial(n):

    if n==1:
        return 1

    return n * factorial(n-1)


print(factorial(5))
```

Output:

```
120
```

---

How it works:

```
factorial(5)
5 * factorial(4)
5 * 4 * factorial(3)
...
```

---

Important point:

Every recursive function needs:

1. Base condition
2. Recursive call

Without a base condition:

```python id="p4w6ye"
RecursionError
```

will occur.

---

### Interview Answer:

> "Recursion is a process where a function calls itself until a stopping condition is reached."

---

# Q47. What is a module in Python?

### Answer:

A module is a Python file containing:

* Functions
* Variables
* Classes

A module helps organize and reuse code.

Example:

File:

```
calculator.py
```

Contains:

```python id="9k0x8s"
def add(a,b):
    return a+b
```

Using module:

```python id="j4h4wr"
import calculator

calculator.add(10,20)
```

---

Types:

### 1. Built-in Modules

Provided by Python.

Examples:

```python id="0t7z0v"
math
os
datetime
random
```

---

### 2. User-defined Modules

Created by developers.

---

# Q48. What is the difference between module and package?

### Answer:

| Module             | Package                   |
| ------------------ | ------------------------- |
| Single Python file | Collection of modules     |
| Extension `.py`    | Folder containing modules |
| Smaller unit       | Larger structure          |

Example:

Module:

```
math.py
```

Package:

```
mypackage/
    module1.py
    module2.py
```

---

### Interview Answer:

> "A module is a single Python file containing code, while a package is a collection of multiple modules organized in a directory."

---

# Q49. What is a virtual environment in Python?

### Answer:

A virtual environment creates an isolated Python environment for a project.

It allows different projects to have different package versions.

Example:

Project A:

```
Django 4.2
```

Project B:

```
Django 5.0
```

Both can run separately.

---

Creating environment:

```bash id="0w1x0u"
python -m venv myenv
```

Activate:

Windows:

```bash id="09p3hz"
myenv\Scripts\activate
```

Linux:

```bash id="2i6y9k"
source myenv/bin/activate
```

---

### Interview Answer:

> "A virtual environment is an isolated environment that manages project-specific dependencies without affecting the global Python installation."

---

# Q50. Write a Python program to reverse a string.

### Answer:

## Method 1: Using slicing

```python id="n0t3lw"
text="Python"

reverse=text[::-1]

print(reverse)
```

Output:

```
nohtyP
```

---

## Method 2: Without built-in function

```python id="7z2r0y"
text="Python"

reverse=""

for char in text:
    reverse=char+reverse

print(reverse)
```

Output:

```
nohtyP
```

---

### Interview Explanation:

> "I used a loop to traverse each character and added every character at the beginning of a new string, which reverses the order."

---

# Final Revision (Q41-Q50)

| Question            | Key Point               |
| ------------------- | ----------------------- |
| Memory Management   | Heap + Manager + GC     |
| Garbage Collection  | Removes unused objects  |
| Shallow Copy        | Shares nested objects   |
| Deep Copy           | Independent copy        |
| List Comprehension  | Short list creation     |
| map()               | Transform elements      |
| filter()            | Select elements         |
| reduce()            | Single result           |
| Recursion           | Function calling itself |
| Module              | Single Python file      |
| Package             | Collection of modules   |
| Virtual Environment | Isolated dependencies   |
| String Reverse      | Common coding question  |

---

# Phase 2.2: Python Tricky Interview Questions & Answers (Fresher Level)

## Easy Language + Interview Explanation

These questions are frequently asked because they check whether you understand Python internally, not just syntax.

---

# Q1. Why are tuples faster than lists in Python?

### Answer:

Tuple is faster than list because **tuple is immutable** (cannot be changed), while list is mutable (can be changed).

Because tuple values cannot change:

* Python stores tuple data more efficiently.
* It requires less memory.
* Python can optimize tuple operations.

Example:

```python
list1 = [1,2,3]

tuple1 = (1,2,3)
```

List:

```text
Can add/remove/update elements
```

Tuple:

```text
Cannot modify elements
```

### Interview Answer:

> "Tuples are faster than lists because they are immutable, require less memory, and Python can optimize their storage. Lists are mutable, so they require extra memory for modification operations."

---

# Q2. Why are strings immutable in Python?

### Answer:

Strings cannot be changed after creation.

Example:

```python
name = "Python"

name = name + " Developer"

print(name)
```

Output:

```
Python Developer
```

Here Python did not modify the original string.

It created a new string object.

---

### Why immutable?

1. Security
2. Better memory optimization
3. String can be used as dictionary keys
4. Faster access

Example:

```python
data = {
    "name": "Python"
}
```

Dictionary keys must be immutable.

---

### Interview Answer:

> "Strings are immutable in Python because changing an existing string can affect memory optimization and security. Any modification creates a new string object."

---

# Q3. Is everything an object in Python?

### Answer:

Yes, almost everything in Python is an object.

Examples:

```python
x = 10

name = "Python"

numbers = [1,2,3]
```

Check:

```python
print(type(x))
```

Output:

```
<class 'int'>
```

Integer itself is an object.

Functions are also objects.

Example:

```python
def hello():
    pass

print(type(hello))
```

Output:

```
<class 'function'>
```

---

### Interview Answer:

> "In Python, everything is treated as an object including numbers, strings, functions, and classes."

---

# Q4. What happens internally when we create a variable?

### Answer:

When we write:

```python
x = 10
```

Python does not store 10 directly inside x.

Process:

```
Value 10 created in memory
        |
        ↓
Object created
        |
        ↓
Variable x points to that object
```

Example:

```python
a = 10
b = 10
```

Both variables may point to the same object because Python optimizes small integers.

---

### Interview Answer:

> "A variable in Python is a reference that points to an object stored in memory. Python variables do not store values directly."

---

# Q5. Difference between copy() and deepcopy()?

### Answer:

Both create copies of objects.

## copy()

Creates a shallow copy.

Example:

```python
import copy

a = [[1,2],[3,4]]

b = copy.copy(a)
```

Outer object is copied, but inner objects are shared.

---

## deepcopy()

Creates a completely independent copy.

Example:

```python
b = copy.deepcopy(a)
```

Changes in b do not affect a.

---

### Interview Answer:

> "Shallow copy copies only the outer object, while deep copy creates a completely independent copy including nested objects."

---

# Q6. What is the difference between iterable and iterator?

### Answer:

## Iterable:

An object that can be looped through.

Examples:

```python
list
tuple
string
dictionary
```

Example:

```python
numbers = [1,2,3]

for x in numbers:
    print(x)
```

---

## Iterator:

An object that gives values one by one.

Example:

```python
numbers = [1,2,3]

it = iter(numbers)

print(next(it))
```

Output:

```
1
```

---

### Difference:

| Iterable       | Iterator            |
| -------------- | ------------------- |
| Can be looped  | Gives next value    |
| Has **iter**() | Has **next**()      |
| Example: list  | Example: iter(list) |

---

# Q7. What is the difference between iterator and generator?

### Answer:

Both produce values one by one.

## Iterator:

Created using class.

Example:

```python
class MyIterator:

    def __iter__(self):
        pass

    def __next__(self):
        pass
```

---

## Generator:

Created using `yield`.

Example:

```python
def numbers():
    yield 1
    yield 2
    yield 3
```

---

Difference:

| Iterator                    | Generator                    |
| --------------------------- | ---------------------------- |
| More code                   | Less code                    |
| Uses class                  | Uses yield                   |
| Manually implements methods | Python creates automatically |

---

# Q8. Why do we use generators?

### Answer:

Generators are used for:

* Saving memory
* Handling large data
* Lazy execution

Example:

Normal list:

```python
numbers=[x for x in range(1000000)]
```

All values are stored in memory.

Generator:

```python
def numbers():
    for x in range(1000000):
        yield x
```

Values are generated only when needed.

---

### Interview Answer:

> "Generators are memory-efficient because they generate values one at a time instead of storing all values in memory."

---

# Q9. What is mutable default argument problem in Python?

### Answer:

Using mutable objects as default arguments can create unexpected behavior.

Example:

Wrong:

```python
def add_item(item, mylist=[]):
    mylist.append(item)
    return mylist


print(add_item(1))
print(add_item(2))
```

Output:

```
[1]
[1,2]
```

The same list is reused.

---

Correct way:

```python
def add_item(item, mylist=None):

    if mylist is None:
        mylist=[]

    mylist.append(item)

    return mylist
```

---

### Interview Answer:

> "Default arguments are created only once when the function is defined. Therefore, mutable default arguments like lists can retain old values between function calls."

---

# Q10. How does Python handle memory leaks?

### Answer:

Python reduces memory leaks using:

1. Reference counting
2. Garbage collector

But memory leaks can still happen when:

* Objects are unnecessarily referenced
* Global variables keep large data
* Cache grows continuously

Example:

```python
data=[]

while True:
    data.append("large data")
```

The list keeps increasing memory usage.

---

### Interview Answer:

> "Python automatically manages memory using garbage collection, but memory leaks can still occur due to unnecessary references or objects that are not released."

---

# Q11. What is monkey patching in Python?

### Answer:

Monkey patching means changing or adding code to a class or module during runtime.

Example:

```python
class Dog:

    def sound(self):
        print("Bark")


def new_sound(self):
    print("New Bark")


Dog.sound = new_sound


d = Dog()

d.sound()
```

Output:

```
New Bark
```

---

Uses:

* Testing
* Modifying library behavior temporarily

---

### Interview Answer:

> "Monkey patching allows modifying classes or modules dynamically during runtime."

---

# Q12. What is duck typing in Python?

### Answer:

Duck typing means Python focuses on **behavior instead of object type**.

Example:

```python
class Dog:

    def sound(self):
        print("Bark")


class Cat:

    def sound(self):
        print("Meow")


def make_sound(animal):
    animal.sound()


make_sound(Dog())
make_sound(Cat())
```

Python does not check whether it is Dog or Cat.

It only checks:

"Does it have sound() method?"

---

### Interview Answer:

> "Duck typing means Python determines object capability by available methods rather than its class type."

---

# Q13. What is method resolution order (MRO) in Python?

### Answer:

MRO defines the order in which Python searches for methods in inheritance.

Example:

```python
class A:
    def show(self):
        print("A")


class B(A):
    pass


obj=B()

obj.show()
```

Python searches:

```
B → A → object
```

To check MRO:

```python
print(B.mro())
```

---

### Interview Answer:

> "MRO defines the sequence in which Python searches classes for methods and attributes, especially in multiple inheritance."

---

# Q14. Difference between class method and static method?

### Class Method:

Uses:

```python
@classmethod
```

Works with class data.

Uses:

```python
cls
```

Example:

```python
class Student:

    school="ABC"

    @classmethod
    def show(cls):
        print(cls.school)
```

---

### Static Method:

Uses:

```python
@staticmethod
```

Does not access class/object data.

Example:

```python
class Math:

    @staticmethod
    def add(a,b):
        return a+b
```

---

### Interview Answer:

> "Class methods work with class-level data using cls, while static methods are independent utility methods that do not access class or object data."

---

# Q15. What is the difference between deep copy and assignment?

### Assignment:

```python
a=[1,2,3]

b=a
```

Both variables point to the same object.

```python
b.append(4)

print(a)
```

Output:

```
[1,2,3,4]
```

---

Copy:

```python
b=a.copy()
```

Creates a separate object.

---

### Interview Answer:

> "Assignment creates another reference to the same object, while copy creates a new object."

---

