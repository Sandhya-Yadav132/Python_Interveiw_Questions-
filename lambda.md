## Lambda Function

**Definition**

> **A lambda function is a single-line anonymous function that is created using the `lambda` keyword.**

**Key Points**

* Uses the `lambda` keyword and contains only one expression.
* Returns the result automatically (no `return` keyword) and can accept zero or more arguments.
* Best for small, temporary functions; commonly used with `map()`, `filter()`, `reduce()`, and `sorted()`.

Bahut achha question. Interviewer ye bhi puch sakta hai.

**"Can accept zero or more arguments"** ka matlab hai ki lambda function me **0, 1, 2, 3... jitne chahe parameters le sakte ho.**

### 1. Zero Arguments

```python
greet = lambda: "Hello"

print(greet())
```

**Output**

```
Hello
```

Yahan lambda ne **koi argument accept nahi kiya**.

---

### 2. One Argument

```python
square = lambda x: x * x

print(square(5))
```

**Output**

```
25
```

Yahan **1 argument (`x`)** accept kiya.

---

### 3. Two Arguments

```python
add = lambda a, b: a + b

print(add(10, 20))
```

**Output**

```
30
```

Yahan **2 arguments** accept kiye.

---

### 4. Multiple Arguments

```python
total = lambda a, b, c, d: a + b + c + d

print(total(1, 2, 3, 4))
```

**Output**

```
10
```

Yahan **4 arguments** accept kiye.

---

### 5. Variable Number of Arguments (`*args`)

```python
total = lambda *args: sum(args)

print(total(1, 2, 3, 4, 5))
```

**Output**

```
15
```

Yahan jitne arguments doge, sab `args` tuple me aa jayenge.

---

### 6. Keyword Arguments (`**kwargs`)

```python
show = lambda **kwargs: kwargs

print(show(name="Sandhya", age=22))
```

**Output**

```python
{'name': 'Sandhya', 'age': 22}
```

---

## Interview Answer

**Q. Can a lambda function accept multiple arguments?**

> **Yes. A lambda function can accept zero, one, or multiple arguments, just like a normal function defined with `def`. It can also use `*args` and `**kwargs`.**

### Dhyan dene wali baat

**Arguments ki koi limit nahi hai, lekin expression ki limit hai.**

✔️ Multiple arguments allowed.

```python
lambda a, b, c: a + b + c
```

❌ Multiple statements allowed nahi.

```python
lambda x:
    print(x)
    return x
```

**Yaad rakhne ka shortcut:**

* ✅ **Parameters** → Unlimited (0 or more)
* ❌ **Expressions** → Only **1**


Ye topic interview me bahut important hai. Interviewer aksar ye sequence follow karta hai:

> **What is lambda?**
> **Why use lambda?**
> **Why not use def?**
> **Show me lambda with map(), filter(), reduce().**

Main isi order me explain karta hoon.

---

# Why do we use lambda with map(), filter(), reduce()?

In functions ko **ek function** chahiye hota hai.

Agar function sirf ek baar use hona hai, to alag se `def` likhna unnecessary ho jata hai.

Isliye lambda use karte hain.

---

# 1. map()

## Purpose

**Applies the same operation to every element of an iterable.**

---

## Syntax

```python
map(function, iterable)
```

Returns a **map object**.

---

## Using `def`

```python
def square(x):
    return x * x

numbers = [1, 2, 3, 4]

result = map(square, numbers)

print(list(result))
```

**Output**

```python
[1, 4, 9, 16]
```

---

## Using `lambda`

```python
numbers = [1, 2, 3, 4]

result = map(lambda x: x * x, numbers)

print(list(result))
```

**Output**

```python
[1, 4, 9, 16]
```

---

## Why lambda?

Without lambda:

```python
def square(x):
    return x*x
```

Ye function sirf ek baar use hua.

To alag function banane ki zarurat nahi.

Direct

```python
lambda x:x*x
```

Likho aur kaam khatam.

---

## When should you use `def`?

Agar function

* baar-baar use hoga
* bada hai
* multiple statements hain

to `def` use karo.

---

# 2. filter()

## Purpose

**Selects only those elements that satisfy a condition.**

---

## Syntax

```python
filter(function, iterable)
```

Function should return **True** or **False**.

Returns a **filter object**.

---

## Using `def`

```python
def even(num):
    return num % 2 == 0

numbers = [1,2,3,4,5,6]

result = filter(even, numbers)

print(list(result))
```

Output

```python
[2,4,6]
```

---

## Using lambda

```python
numbers = [1,2,3,4,5,6]

result = filter(lambda x:x%2==0, numbers)

print(list(result))
```

Output

```python
[2,4,6]
```

---

## Why lambda?

Condition sirf ek line ki hai.

Separate function ki zarurat nahi.

---

# 3. reduce()

> **Note:** `reduce()` built-in nahi hai. Ise `functools` module se import karna padta hai.

```python
from functools import reduce
```

---

## Purpose

**Combines all elements into a single value by repeatedly applying a function.**

---

## Syntax

```python
reduce(function, iterable)
```

Function must accept **2 arguments**.

---

## Using `def`

```python
from functools import reduce

def add(a,b):
    return a+b

numbers=[1,2,3,4]

result=reduce(add,numbers)

print(result)
```

Output

```python
10
```

---

## Using lambda

```python
from functools import reduce

numbers=[1,2,3,4]

result=reduce(lambda a,b:a+b,numbers)

print(result)
```

Output

```python
10
```

---

# Why lambda?

Again,

Ye function sirf reduce ke andar hi use hua.

Isliye alag `def` likhne ki zarurat nahi.

---

# Difference

| Feature          | map()          | filter()        | reduce()                 |
| ---------------- | -------------- | --------------- | ------------------------ |
| Purpose          | Transform data | Filter data     | Reduce data to one value |
| Returns          | map object     | filter object   | Single value             |
| Function Returns | Any value      | True/False      | Combined value           |
| Output Size      | Same as input  | Same or smaller | One value                |

---

# Interview Question

### Q. Why do people mostly use lambda with map(), filter(), and reduce() instead of `def`?

**Answer:**

> **Because the required function is usually small and used only once. Lambda makes the code concise by avoiding a separate function definition. If the same function is needed in multiple places or contains multiple statements, `def` is a better choice.**

---

# When to use what?

### Use `lambda` ✅

* One-line logic
* Temporary function
* Used only once
* With `map()`, `filter()`, `reduce()`, `sorted()`

---

### Use `def` ✅

* Function will be reused
* Multiple statements are needed
* Better readability
* Easier debugging
* Complex business logic

---

## Easy Trick to Remember

| Function     | Think As                  |
| ------------ | ------------------------- |
| **map()**    | **Modify every item**     |
| **filter()** | **Keep selected items**   |
| **reduce()** | **Make one final result** |

Example on `[1, 2, 3, 4]`:

* `map(x → x*2)` → `[2, 4, 6, 8]`
* `filter(x → even)` → `[2, 4]`
* `reduce(a,b → a+b)` → `10`

Ye teen examples interview me sabse common hote hain aur concept ko turant clear kar dete hain.

