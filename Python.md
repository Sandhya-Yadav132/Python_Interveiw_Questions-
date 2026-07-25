
Roadmap:

### Part 1: Python Foundation
✅ Python Data Types  
- int
- float
- complex
- bool
- str
- list
- tuple
- set
- dict
- None
- bytes
- bytearray
- range

✅ All important methods with practical examples


### Part 2: Control Flow
✅ if  
✅ elif  
✅ else  
✅ for loop  
✅ while loop  
✅ for-else  
✅ nested loops


### Part 3: Functions & Functional Programming
✅ lambda function  
✅ map()  
✅ filter()  
✅ reduce()  
✅ args  
✅ kwargs  
✅ packing and unpacking


### Part 4: Advanced Python
✅ Decorators  
✅ Iterator  
✅ Generator  
✅ List comprehension  
✅ Recursion


### Part 5: Exception Handling
✅ try  
✅ except  
✅ else  
✅ finally  
✅ custom exception  
✅ exception hierarchy


### Part 6: OOP Deep
✅ Class and Object  
✅ Constructor  
✅ Instance variable  
✅ Class variable  
✅ Encapsulation  
✅ Abstraction  
✅ Polymorphism  
- Method overriding
- Method overloading

✅ Class method vs Static method


### Part 7: Python Internals
✅ Memory Management  
✅ Garbage Collector  
✅ Reference Counting  
✅ Mutable vs Immutable  
✅ List vs Tuple memory  
✅ Why tuple faster than list


### Part 8: Advanced Concepts
✅ Time Complexity  
✅ Space Complexity  
✅ Shallow Copy vs Deep Copy  
✅ Monkey Patching  
✅ Module vs Package  
✅ Python 2 vs Python 3


---



# Python Interview Notes

# Topic 1: Python Versions

---

## Q1. What is Python?

### Answer:

Python ek high-level, interpreted, general-purpose programming language hai.

Python ko readable aur simple syntax ke liye design kiya gaya hai.

Python ka use:

* Web Development
* Data Science
* AI/ML
* Automation
* Scripting
* Backend Development

me hota hai.

---

## Q2. What is the difference between Python 2 and Python 3?

### Answer:

Python 3 Python ka improved version hai jo Python 2 ki limitations ko solve karne ke liye introduce kiya gaya tha.

Python 2 ka official support 2020 me end ho gaya.

Ab industry me Python 3 use hota hai.

---

# Python 2 vs Python 3

| Feature          | Python 2                    | Python 3                  |
| ---------------- | --------------------------- | ------------------------- |
| Release          | 2000                        | 2008                      |
| Support          | Ended in 2020               | Active                    |
| Print            | Statement                   | Function                  |
| Division         | Integer division by default | Float division by default |
| Unicode          | Limited support             | Default Unicode           |
| Input            | raw_input()                 | input()                   |
| Range            | List return karta tha       | Iterator-like object      |
| Exception syntax | Different                   | Improved                  |
| Async support    | Not available               | Available                 |

---

# 1. Print Function Difference

## Python 2:

```python
print "Hello"
```

Print ek statement tha.

## Problem:

* Function ki tarah behave nahi karta tha.
* Multiple arguments aur formatting limited thi.

## Python 3:

```python
print("Hello")
```

Print ko function bana diya gaya.

## Advantage:

* Better formatting
* Multiple arguments support
* Consistent syntax

Example:

```python
print("Hello", "Python")
```

Output:

```
Hello Python
```

---

# 2. Division Difference

## Python 2:

```python
5/2
```

Output:

```
2
```

Integer division hoti thi.

### Problem:

Mathematical calculations me unexpected results aa sakte the.

## Python 3:

```python
5/2
```

Output:

```
2.5
```

Agar integer division chahiye:

```python
5//2
```

Output:

```
2
```

---

# 3. Input Difference

## Python 2:

```python
raw_input()
```

String input ke liye.

```python
input()
```

Expression evaluate karta tha.

Example:

User input:

```
2+3
```

Output:

```
5
```

### Problem:

Security issue tha kyunki user input execute ho sakta tha.

---

## Python 3:

```python
input()
```

Always string return karta hai.

Example:

```python
x=input()

print(type(x))
```

Output:

```
<class 'str'>
```

---

# 4. Unicode Difference

## Python 2:

Default:

```
ASCII
```

Unicode ke liye:

```python
unicode()
```

### Problem:

Different languages ke characters handle karne me problem.

---

## Python 3:

Default:

```
Unicode
```

Example:

```python
name="संध्या"
```

Direct support.

---

# 5. String Difference

## Python 2:

Do types:

```
str
unicode
```

## Python 3:

Do types:

```
str
bytes
```

Example:

String:

```python
"hello"
```

Binary:

```python
b"hello"
```

---

# 6. Range vs xrange

## Python 2:

```python
range(1000000)
```

Complete list memory me create karta tha.

### Problem:

Large data ke liye memory consume hoti thi.

Python 2 me solution:

```python
xrange()
```

---

## Python 3:

```python
range(1000000)
```

Lazy object return karta hai.

### Advantage:

* Less memory usage
* Faster iteration

---

# 7. Exception Handling Difference

## Python 2:

```python
except Exception, e:
    print e
```

## Python 3:

```python
except Exception as e:
    print(e)
```

### Advantage:

* More readable
* Consistent syntax

---

# 8. Dictionary Difference

## Python 2:

```python
dict.keys()
```

List return karta tha.

## Python 3:

```python
dict.keys()
```

View object return karta hai.

### Advantage:

Memory efficient.

---

# 9. Iterator Changes

Python 3 me:

```python
map()
filter()
zip()
```

iterator return karte hain.

### Why?

Python 2 me ye complete list banate the.

Problem:

Large data ke liye memory waste.

Python 3:

Lazy evaluation use karta hai.

---

# Q3. Why Python 3 replaced Python 2?

### Answer:

Python 2 me kuch limitations thi:

1. Poor Unicode support
2. Memory inefficient functions
3. Inconsistent syntax
4. Security issues in input()
5. Limited modern features

Python 3 ne:

* Better Unicode
* Better memory management
* Modern syntax
* Better performance
* Async support

provide kiya.

---

# Topic 2: Python Latest Version

---

## Q1. What is the latest Python version?

### Answer:

Currently latest stable Python version is:

```
Python 3.14
```

---

## Python Version Timeline

| Version     | Important Feature                      |
| ----------- | -------------------------------------- |
| Python 3.8  | Walrus operator                        |
| Python 3.9  | Dictionary merge operator              |
| Python 3.10 | Match-case                             |
| Python 3.11 | Performance improvement, better errors |
| Python 3.12 | Typing improvements                    |
| Python 3.13 | Interpreter improvements               |
| Python 3.14 | Latest improvements                    |

---

# Topic 3: Python 3.11 Features

---

## Q1. What are the major features introduced in Python 3.11?

### Answer:

Python 3.11 ko "Faster CPython" release kaha gaya.

Major improvements:

1. Performance improvement
2. Better error messages
3. Improved traceback
4. Exception groups
5. Better typing support

---

# 1. Performance Improvement

Python 3.11 previous versions se faster hai.

Reason:

* Optimized interpreter
* Faster bytecode execution
* Better function calls

---

# 2. Better Error Messages

Before:

```
AttributeError
```

Python 3.11:

```
AttributeError:
Did you mean: append?
```

### Advantage:

Developer ko exact mistake samajh aati hai.

---

# 3. Improved Tracebacks

Old:

Error line show hoti thi.

New:

Exact expression highlight hota hai.

---

# 4. Exception Groups

### Problem:

Pehle ek time par mainly ek exception handle hoti thi.

Python 3.11:

Multiple exceptions handle kar sakte hain.

Syntax:

```python
except* Exception:
    pass
```

---

# 5. Typing Improvements

Python 3.11 me:

* Better type hints
* New typing features

---

# Topic 4: CPython

---

## Q1. What is CPython?

### Answer:

CPython Python language ka default implementation hai jo Python code ko execute karta hai.

Ye mainly C language me written hai.

---

## Q2. Difference between Python and CPython?

| Python                        | CPython                    |
| ----------------------------- | -------------------------- |
| Programming language          | Implementation             |
| Rules define karta hai        | Code execute karta hai     |
| Multiple implementations hain | Default implementation hai |
| Syntax provide karta hai      | Runtime provide karta hai  |

---

# Python Implementations

| Implementation | Written In |
| -------------- | ---------- |
| CPython        | C          |
| PyPy           | RPython    |
| Jython         | Java       |
| IronPython     | C#         |

---

# Q3. How Python code executes internally?

Flow:

```
Python Source Code (.py)

        ↓

Compiler

        ↓

Bytecode (.pyc)

        ↓

Python Virtual Machine

        ↓

Machine Execution
```

---

# Q4. What is the role of CPython?

CPython handle karta hai:

### 1. Code Execution

Python code ko bytecode me convert karta hai.

### 2. Memory Management

Handle karta hai:

* Object creation
* Reference counting
* Garbage collection

### 3. Object Management

Python me har cheez object hoti hai.

CPython objects ko memory me manage karta hai.

---

# Q5. What is GIL in CPython?

GIL:

Global Interpreter Lock

Meaning:

Ek time par ek thread Python bytecode execute kar sakta hai.

### Problem:

CPU intensive multithreading slow ho sakti hai.

Example:

Good:

* File operations
* Network requests

Not ideal:

* Heavy calculations

---

# Quick Revision Notes

## Python 2 vs Python 3

* Python 2 support ended in 2020
* Python 3 modern version hai
* print statement → print function
* Integer division problem solved
* Unicode improved
* xrange removed
* range memory efficient hua
* input safer hua
* Better exception syntax
* Async support added

## Python 3.11

* Faster CPython
* Better errors
* Better traceback
* Exception groups
* Typing improvements

## CPython

* Default Python implementation
* Written in C
* Converts code into bytecode
* Runs using PVM
* Handles memory management
* Uses reference counting
* Has GIL


