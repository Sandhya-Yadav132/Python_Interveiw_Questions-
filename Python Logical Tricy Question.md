# Python Tricky Interview Questions & Answers (Fresher Level)

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



# Phase 2.2 Part 2: Advanced Python Tricky Interview Questions (Fresher Level)

## Easy Language + Interview Style Answers

---

# Q16. How does a decorator work internally in Python?

### Answer:

A decorator is a function that takes another function as input and returns a modified function.

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
    print("Hello Python")


hello()
```

Output:

```
Before function
Hello Python
After function
```

---

Internally:

When Python sees:

```python
@decorator
def hello():
```

It converts it into:

```python
hello = decorator(hello)
```

So the original function is passed to the decorator.

---

### Interview Answer:

> "A decorator internally works by passing a function as an argument to another function and returning a new function with additional behavior."

---

# Q17. What are first-class functions in Python?

### Answer:

A language supports first-class functions when functions can be treated like normal objects.

In Python, functions can be:

* Stored in variables
* Passed as arguments
* Returned from another function

---

Example 1: Store function in variable

```python
def greet():
    return "Hello"


message = greet

print(message())
```

Output:

```
Hello
```

---

Example 2: Pass function as argument

```python
def welcome(func):
    print(func())


def hello():
    return "Hi"


welcome(hello)
```

---

### Interview Answer:

> "In Python, functions are first-class objects because they can be assigned to variables, passed as arguments, and returned from other functions."

---

# Q18. What is closure in Python?

### Answer:

A closure is a function that remembers variables from its outer function even after the outer function has finished execution.

Example:

```python
def outer():

    message = "Python"

    def inner():
        print(message)

    return inner


func = outer()

func()
```

Output:

```
Python
```

Here:

* `outer()` finished execution
* But `inner()` still remembers `message`

---

### Real use cases:

* Decorators
* Data hiding
* Creating function factories

---

### Interview Answer:

> "A closure is a nested function that remembers and accesses variables from its enclosing function even after the outer function execution is completed."

---

# Q19. What is the difference between `__init__()` and `__new__()`?

### Answer:

Both are related to object creation.

---

## **new**()

Responsible for creating the object.

It runs first.

Example:

```python
class Student:

    def __new__(cls):
        print("Creating object")
        return super().__new__(cls)


    def __init__(self):
        print("Initializing object")


s = Student()
```

Output:

```
Creating object
Initializing object
```

---

## **init**()

Responsible for initializing object data.

Example:

```python
class Student:

    def __init__(self,name):
        self.name=name
```

---

Difference:

| **new**()      | **init**()             |
| -------------- | ---------------------- |
| Creates object | Initializes object     |
| Runs first     | Runs after **new**     |
| Returns object | Does not return object |

---

### Interview Answer:

> "**new** creates the object, while **init** initializes the object's attributes."

---

# Q20. What is the difference between `__str__()` and `__repr__()`?

### Answer:

Both are used to represent objects as strings.

---

## **str**()

Used for user-friendly output.

Example:

```python
class Student:

    def __str__(self):
        return "Student Object"


s = Student()

print(s)
```

Output:

```
Student Object
```

---

## **repr**()

Used for developer/debugging representation.

Example:

```python
class Student:

    def __repr__(self):
        return "Student(name='Ram')"
```

---

Difference:

| **str**                 | **repr**                |
| ----------------------- | ----------------------- |
| User readable           | Developer readable      |
| Informal representation | Official representation |
| Used by print()         | Used by repr()          |

---

### Interview Answer:

> "**str** provides a readable representation for users, while **repr** provides a detailed representation mainly for debugging."

---

# Q21. What is GIL in Python?

### Answer:

GIL stands for **Global Interpreter Lock**.

It is a lock in CPython that allows only one thread to execute Python bytecode at a time.

---

Example:

Multiple threads:

```
Thread 1
Thread 2
Thread 3
```

GIL:

```
Only one thread executes Python code
at a particular time
```

---

Why GIL exists?

Because Python memory management is not completely thread-safe.

---

Important:

GIL affects:

❌ CPU-bound tasks

Example:

* Heavy calculations
* Image processing

But not much:

✅ I/O-bound tasks

Example:

* API calls
* File reading
* Network requests

---

### Interview Answer:

> "GIL is a lock in CPython that allows only one thread to execute Python bytecode at a time. It prevents memory management issues but limits CPU-bound multithreading."

---

# Q22. What is namespace in Python?

### Answer:

A namespace is a container that stores names and their corresponding objects.

Example:

```python
x = 10
name = "Python"
```

Namespace stores:

```
x → 10

name → "Python"
```

---

Types of namespaces:

### 1. Built-in Namespace

Contains Python predefined names.

Example:

```
print()
len()
```

---

### 2. Global Namespace

Created at program level.

Example:

```python
x=10
```

---

### 3. Local Namespace

Created inside functions.

Example:

```python
def test():
    y=20
```

---

### Interview Answer:

> "A namespace is a mapping between names and objects. It helps Python avoid naming conflicts."

---

# Q23. What is the difference between local, global, and nonlocal variables?

### Answer:

## Local

Created inside function.

```python
def test():
    x=10
```

Accessible only inside function.

---

## Global

Created outside function.

```python
x=100
```

Accessible throughout program.

---

## Nonlocal

Used in nested functions.

Example:

```python
def outer():

    x=10

    def inner():

        nonlocal x
        x=20

    inner()

    print(x)


outer()
```

Output:

```
20
```

---

### Interview Answer:

> "Local variables belong to current function, global variables belong to the module level, and nonlocal variables are used to modify variables from an enclosing function."

---

# Q24. What happens when we import a module in Python?

### Answer:

When we write:

```python
import math
```

Python:

1. Searches module
2. Loads module code
3. Creates module object
4. Executes module code
5. Stores it in memory

---

Python stores imported modules in:

```python
sys.modules
```

Example:

```python
import sys

print(sys.modules)
```

---

### Interview Answer:

> "When importing a module, Python searches for it, loads and executes it, then stores it in sys.modules to avoid loading it again."

---

# Q25. What is `__name__ == "__main__"` in Python?

### Answer:

It checks whether a Python file is executed directly or imported.

Example:

```python
def test():
    print("Testing")


if __name__ == "__main__":
    test()
```

---

If file runs directly:

```
Testing
```

If imported:

```
test() will not execute automatically
```

---

Why use it?

* Controls program execution
* Makes code reusable

---

### Interview Answer:

> "The **name** == '**main**' condition ensures that specific code runs only when the file is executed directly, not when it is imported."

---

# Q26. What is the difference between `pass`, `continue`, and `break`?

### Answer:

## pass

Does nothing.

Used as a placeholder.

Example:

```python
if True:
    pass
```

---

## continue

Skips current iteration.

Example:

```python
for i in range(5):

    if i==2:
        continue

    print(i)
```

Output:

```
0
1
3
4
```

---

## break

Stops the loop completely.

Example:

```python
for i in range(5):

    if i==3:
        break

    print(i)
```

Output:

```
0
1
2
```

---

# Q27. What is the difference between `remove()`, `pop()`, and `del`?

### Answer:

## remove()

Removes by value.

```python
numbers=[1,2,3]

numbers.remove(2)
```

Result:

```
[1,3]
```

---

## pop()

Removes by index and returns value.

```python
numbers.pop(1)
```

Returns:

```
2
```

---

## del

Deletes object or index.

```python
del numbers[0]
```

---

Difference:

| Method   | Removes               |
| -------- | --------------------- |
| remove() | Value                 |
| pop()    | Index + returns value |
| del      | Index/object          |

---

# Q28. What is Python's MRO in multiple inheritance?

### Answer:

MRO (Method Resolution Order) decides which class method Python calls first.

Example:

```python
class A:
    def show(self):
        print("A")


class B(A):
    pass


class C(B):
    pass


obj=C()

obj.show()
```

Search order:

```
C → B → A → object
```

Check:

```python
print(C.mro())
```

---

### Interview Answer:

> "MRO defines the order in which Python searches parent classes for methods and attributes."

---

# Q29. What is the difference between `sort()` and `sorted()`?

### Answer:

## sort()

* Works only with lists
* Changes original list

Example:

```python
a=[3,1,2]

a.sort()

print(a)
```

Output:

```
[1,2,3]
```

---

## sorted()

* Works with any iterable
* Returns a new list

Example:

```python
a=(3,1,2)

b=sorted(a)

print(b)
```

Output:

```
[1,2,3]
```

---

### Interview Answer:

> "sort() modifies the original list, while sorted() returns a new sorted list without changing the original data."

---

# Q30. What is the difference between `isinstance()` and `type()`?

### Answer:

## type()

Checks exact type.

Example:

```python
class Animal:
    pass

class Dog(Animal):
    pass


d=Dog()

print(type(d)==Dog)
```

---

## isinstance()

Checks inheritance also.

Example:

```python
print(isinstance(d,Animal))
```

Output:

```
True
```

---

### Interview Answer:

> "type() checks the exact class of an object, while isinstance() also considers inheritance relationships."

---

