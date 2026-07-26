# PART 1: TUPLE DATA TYPE (Deep Interview Notes)

---

# Q1. What is Tuple in Python?

## Answer:

A **Tuple** is an **ordered, immutable collection** of elements.

Tuple is similar to a list, but the main difference is:

* List → Mutable (can change)
* Tuple → Immutable (cannot change)

Tuple is represented using parentheses `()`.

Example:

```python
t = (10, 20, 30)

print(type(t))
```

Output:

```python
<class 'tuple'>
```

---

# Creating Tuple

## 1. Normal Tuple

```python
t = (1,2,3,4)

print(t)
```

Output:

```python
(1,2,3,4)
```

---

## 2. Tuple without Parentheses

Python allows tuple packing.

```python
t = 10,20,30

print(t)
```

Output:

```python
(10,20,30)
```

Python automatically creates a tuple.

---

## 3. Single Element Tuple (Important Interview Question)

Wrong:

```python
t = (10)

print(type(t))
```

Output:

```python
<class 'int'>
```

Because parentheses are treated as grouping.

Correct:

```python
t = (10,)

print(type(t))
```

Output:

```python
<class 'tuple'>
```

Comma creates the tuple.

---

# Tuple Properties

---

# 1. Ordered

Elements maintain insertion order.

Example:

```python
t = ("Python","Java","C++")

print(t)
```

Output:

```python
('Python','Java','C++')
```

---

# 2. Immutable

Once created, tuple values cannot be modified.

Example:

```python
t=(10,20,30)

t[1]=100
```

Output:

```
TypeError: 'tuple' object does not support item assignment
```

---

# Why Tuple is Immutable?

Internally tuple stores references just like list.

Example:

```python
t=(10,20,30)
```

Memory:

```
Tuple Object

+----+----+----+
| •  | •  | •  |
+----+----+----+
 |    |    |
 ↓    ↓    ↓
10   20   30
```

But tuple does not allow changing these references.

List:

```
List:
Reference can change
```

Tuple:

```
Tuple:
Reference cannot change
```

---

# 3. Allows Duplicate Values

```python
t=(10,20,20,30)

print(t)
```

Output:

```python
(10,20,20,30)
```

---

# 4. Can Store Different Data Types

```python
t=(10,"Python",5.5,True)

print(t)
```

Output:

```python
(10,'Python',5.5,True)
```

---

# Internal Memory Difference: List vs Tuple

Very Important Interview Topic ⭐

## List

Example:

```python
l=[10,20,30]
```

Memory:

```
List Object

+-----+-----+-----+
| ptr | ptr | ptr |
+-----+-----+-----+

 ↓     ↓     ↓

10    20    30
```

List stores:

1. Data references
2. Extra capacity information
3. Dynamic resizing information

---

## Tuple

Example:

```python
t=(10,20,30)
```

Memory:

```
Tuple Object

+-----+-----+-----+
| ptr | ptr | ptr |
+-----+-----+-----+

 ↓     ↓     ↓

10    20    30
```

Tuple stores:

1. Data references only
2. Fixed size information

---

# Why Tuple is Faster Than List?

Interview Favourite Question ⭐

## Reason 1: No Dynamic Resizing

List can grow:

```python
l=[]
l.append(10)
l.append(20)
```

Python needs extra memory allocation.

Tuple:

```python
t=(10,20)
```

Size is fixed.

No resizing required.

---

## Reason 2: Less Memory Usage

Example:

```python
import sys

l=[1,2,3,4,5]

t=(1,2,3,4,5)


print(sys.getsizeof(l))
print(sys.getsizeof(t))
```

Generally:

```
List size > Tuple size
```

because list maintains extra capacity.

---

## Reason 3: Faster Iteration

Tuple elements are fixed, so Python can access them slightly faster.

Example:

```python
for item in tuple:
    print(item)
```

Python knows:

* Size cannot change
* Structure is fixed

---

# List vs Tuple (Memory Based)

| List                  | Tuple               |
| --------------------- | ------------------- |
| Mutable               | Immutable           |
| Uses more memory      | Uses less memory    |
| Dynamic size          | Fixed size          |
| More methods          | Less methods        |
| Slower                | Faster              |
| More flexible         | More secure         |
| Uses extra allocation | No extra allocation |

---

# Tuple Methods

Tuple has only two methods because it is immutable.

---

# 1. count()

Counts occurrences.

Example:

```python
t=(10,20,20,30)

print(t.count(20))
```

Output:

```
2
```

Time Complexity:

```
O(n)
```

---

# 2. index()

Returns first occurrence index.

Example:

```python
t=(10,20,30)

print(t.index(20))
```

Output:

```
1
```

Time Complexity:

```
O(n)
```

---

# Tuple Slicing

Tuple supports slicing like list.

Example:

```python
t=(10,20,30,40,50)

print(t[1:4])
```

Output:

```
(20,30,40)
```

---

# Tuple Packing and Unpacking

## Packing

Creating tuple from multiple values.

```python
student=("Rahul",22,"Python")
```

Here values are packed into tuple.

---

## Unpacking

Extracting tuple values.

```python
student=("Rahul",22,"Python")

name,age,skill=student

print(name)
print(age)
print(skill)
```

Output:

```
Rahul
22
Python
```

---

# Important Interview Question ⭐

## Q. What happens if number of variables and tuple values are different?

Example:

```python
a,b=(10,20,30)
```

Output:

```
ValueError
```

Because:

```
2 variables
3 values
```

---

# Using * in Unpacking

Python allows collecting remaining values.

Example:

```python
numbers=(1,2,3,4,5)

a,*b=numbers

print(a)
print(b)
```

Output:

```
1
[2,3,4,5]
```

---

# Nested Tuple

Tuple can contain another tuple.

Example:

```python
t=(1,2,(3,4))

print(t[2][0])
```

Output:

```
3
```

---

# Can Tuple Contain Mutable Objects?

Yes.

Example:

```python
t=([1,2,3],10)

t[0].append(4)

print(t)
```

Output:

```
([1,2,3,4],10)
```

Important:

Tuple itself is immutable, but the object inside it can be mutable.

---

# Real-Time Uses of Tuple

## 1. Database Records

Example:

```python
user=("Sandhya",22,"India")
```

A database row is often represented as a tuple because data should not change accidentally.

---

## 2. Returning Multiple Values from Function

Example:

```python
def get_user():

    return "Ram",25,"Delhi"


data=get_user()

print(data)
```

Output:

```
('Ram',25,'Delhi')
```

Python automatically returns tuple.

---

## 3. Dictionary Keys

Tuple can be a dictionary key because it is immutable.

Example:

```python
location={
    (10,20):"Point A"
}

print(location[(10,20)])
```

Output:

```
Point A
```

List cannot be used:

```python
{
[10,20]:"Point A"
}
```

Error:

```
TypeError: unhashable type: list
```

---

# Interview Questions

## Q1. Why tuple is immutable?

Answer:

Tuple immutability provides:

1. Better memory efficiency
2. Faster execution
3. Hashability
4. Data safety

---

## Q2. Why can tuple be used as dictionary key?

Answer:

Dictionary keys must be hashable.

Tuple is immutable, so its hash value remains constant.

Therefore tuple can be used as a key.

---

## Q3. Is tuple completely immutable?

Answer:

No.

Tuple is immutable, but mutable objects inside it can change.

Example:

```python
t=([1,2],3)

t[0].append(4)
```

The list changes, but tuple structure remains the same.

---

# Real Project Example

In Django / DRF:

API response data sometimes behaves like tuple:

```python
(
 {"id":1,"name":"Phone"},
 {"id":2,"name":"Laptop"}
)
```

Database query results can also return tuple-like structures.

---

# Next Topic:

## SET Data Type

Covering:

✅ What is Set
✅ Internal memory structure (Hash Table)
✅ Why set is unordered
✅ Why set removes duplicates
✅ All set methods:

* add()
* update()
* remove()
* discard()
* pop()
* union()
* intersection()
* difference()

✅ Set vs Dictionary memory difference
✅ Real-time examples
✅ Interview questions (hashing based)
