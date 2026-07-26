# PART 1: LIST DATA TYPE (Deep Interview Notes)

---

# Q1. What is a List in Python?

## Answer

A **List** is an **ordered, mutable** collection that can store **multiple values of different data types**.

Lists are enclosed in square brackets `[]`.

Example:

```python
l = [10, 20, 30, "Python", 5.5, True]

print(l)
```

Output

```python
[10, 20, 30, 'Python', 5.5, True]
```

Here list stores different data types together.

---

# Properties of List

### 1. Ordered

Elements maintain insertion order.

```python
l = [100, 200, 300]

print(l)
```

Output

```python
[100, 200, 300]
```

Order never changes unless we modify it.

---

### 2. Mutable

List can be modified after creation.

```python
l = [10,20,30]

l[1]=100

print(l)
```

Output

```python
[10,100,30]
```

Unlike strings, no new object is created.

---

### 3. Allows Duplicate Values

```python
l=[10,20,20,20]

print(l)
```

Output

```python
[10,20,20,20]
```

---

### 4. Dynamic Size

List grows and shrinks automatically.

```python
l=[]

l.append(10)
l.append(20)
l.append(30)

print(l)
```

Output

```python
[10,20,30]
```

---

# Internal Memory Structure (Very Important)

Suppose

```python
l=[10,20,30]
```

Many beginners think list stores values directly.

Actually **it stores references (addresses)** to objects.

```
List Object

+-----+-----+-----+
|  •  |  •  |  •  |
+-----+-----+-----+
   |      |      |
   ↓      ↓      ↓
  10     20     30
```

The integers exist as separate objects in memory.

The list only stores pointers (references) to them.

---

## Why does Python do this?

Because one object can be shared.

Example

```python
x=100

l1=[x]
l2=[x]
```

Memory

```
        100
       /   \
      ↓     ↓
     l1    l2
```

Only one integer object exists.

This saves memory.

---

# How List Grows Internally

Suppose

```python
l=[]
```

Initially

```
Capacity = 0
```

Append one element

```python
l.append(10)
```

Python allocates extra memory.

```
Capacity = 4 (approximately)
```

Append more

```python
l.append(20)
l.append(30)
l.append(40)
```

Still enough capacity.

When capacity becomes full,

Python reallocates.

```
Old Capacity = 4

↓

New Capacity ≈ 8
```

This is called **Overallocation**.

### Why?

If Python increased capacity by only 1 every time:

```
1
2
3
4
5
6
...
```

it would need to copy the list on every append, making it slow.

Instead it allocates extra space in advance.

---

# Why is append() O(1)?

Because most of the time there is already free space.

```
[10][20][30][ ]
```

Adding 40:

```
[10][20][30][40]
```

No copying.

Rarely, when the list is full:

```
[10][20][30][40]
```

Python allocates a bigger array and copies elements.

That one append is O(n), but because it happens infrequently, the **average (amortized)** cost of `append()` is **O(1)**.

---

# List Indexing

```python
l=["A","B","C","D"]
```

```
 A   B   C   D
 0   1   2   3

-4 -3 -2 -1
```

Example

```python
print(l[0])
print(l[-1])
```

Output

```python
A
D
```

---

# List Slicing

Syntax

```python
list[start:end:step]
```

Example

```python
l=[10,20,30,40,50]

print(l[1:4])
```

Output

```python
[20,30,40]
```

Reverse

```python
print(l[::-1])
```

Output

```python
[50,40,30,20,10]
```

---

# Important List Methods

# 1. append()

Adds **one element** at the end.

```python
l=[10,20]

l.append(30)

print(l)
```

Output

```python
[10,20,30]
```

Time Complexity

```
O(1)
```

Real Example

Shopping Cart

```python
cart=[]

cart.append("Laptop")
cart.append("Mouse")

print(cart)
```

Output

```python
['Laptop','Mouse']
```

---

# 2. extend()

Adds multiple elements.

```python
l=[10,20]

l.extend([30,40,50])

print(l)
```

Output

```python
[10,20,30,40,50]
```

Time Complexity

```
O(k)
```

where **k = number of inserted elements**.

---

# append() vs extend()

```python
l=[1,2]

l.append([3,4])

print(l)
```

Output

```python
[1,2,[3,4]]
```

Because append adds the whole list as **one object**.

---

```python
l=[1,2]

l.extend([3,4])

print(l)
```

Output

```python
[1,2,3,4]
```

Because extend inserts each element separately.

---

### Interview Question ⭐

Why does `append([1,2])` create a nested list?

Because **append() always adds exactly one object**, regardless of its type.

---

# 3. insert()

Insert element at a specific position.

```python
l=[10,20,30]

l.insert(1,100)

print(l)
```

Output

```python
[10,100,20,30]
```

Time Complexity

```
O(n)
```

### Why?

Because existing elements must shift right.

Before

```
10 20 30
```

Insert at index 1

```
10 100 20 30
```

20 and 30 are shifted.

---

# 4. remove()

Removes first matching value.

```python
l=[10,20,30]

l.remove(20)

print(l)
```

Output

```python
[10,30]
```

Time Complexity

```
O(n)
```

Python first searches for the value, then shifts elements.

---

# 5. pop()

Removes by index and returns the removed element.

```python
l=[10,20,30]

x=l.pop()

print(x)

print(l)
```

Output

```python
30
[10,20]
```

Last element removal

```
O(1)
```

Removing from middle

```
O(n)
```

because shifting is required.

---

# remove() vs pop()

| remove()                     | pop()                         |
| ---------------------------- | ----------------------------- |
| Removes by value             | Removes by index              |
| Doesn't return removed value | Returns removed value         |
| O(n)                         | O(1) for last, O(n) otherwise |

---

# 6. clear()

Deletes all elements.

```python
l=[10,20,30]

l.clear()

print(l)
```

Output

```python
[]
```

---

# 7. copy()

Creates a shallow copy.

```python
l1=[10,20]

l2=l1.copy()

print(l2)
```

Output

```python
[10,20]
```

We'll study **shallow copy vs deep copy** in detail later.

---

# 8. count()

Counts occurrences.

```python
l=[1,2,2,2,3]

print(l.count(2))
```

Output

```python
3
```

Time Complexity

```
O(n)
```

---

# 9. index()

Returns first occurrence index.

```python
l=[10,20,30]

print(l.index(20))
```

Output

```python
1
```

If not found:

```python
ValueError
```

---

# 10. reverse()

Reverses the list in-place.

```python
l=[1,2,3]

l.reverse()

print(l)
```

Output

```python
[3,2,1]
```

Time Complexity

```
O(n)
```

---

# 11. sort()

Sorts the original list.

```python
l=[5,2,8,1]

l.sort()

print(l)
```

Output

```python
[1,2,5,8]
```

Descending

```python
l.sort(reverse=True)
```

Time Complexity

```
O(n log n)
```

Python uses **Timsort**, which is optimized for real-world data.

---

# Real-Time Uses of List

## 1. Shopping Cart

```python
cart=[]

cart.append("Laptop")
cart.append("Keyboard")

print(cart)
```

Output

```python
['Laptop', 'Keyboard']
```

---

## 2. Student Attendance

```python
attendance=[]

attendance.append("Rahul")
attendance.append("Priya")

print(attendance)
```

---

## 3. API Response

```python
products = [
    {"name":"Phone"},
    {"name":"Laptop"},
    {"name":"Mouse"}
]

print(products[0]["name"])
```

Output

```python
Phone
```

This is very common in Django REST Framework APIs.

---

# Interview Questions ⭐

### Q1. Why is a list mutable?

**Answer:**

A list stores **references** to objects. Python allows the list object to update, insert, or remove these references without creating a new list object. Therefore, its contents can change while the list object itself remains the same.

---

### Q2. Why is `append()` faster than `insert()`?

**Answer:**

* `append()` usually adds the new element at the end without moving existing elements, so its average complexity is **O(1)**.
* `insert()` may need to shift many elements to make space, so its complexity is **O(n)**.

---

### Q3. Why can a list store different data types?

**Answer:**

Because a list stores **references to Python objects**, not raw values. Since every value in Python is an object, the list can hold references to objects of different types (integers, strings, floats, custom objects, etc.).

---

## Next Part

We'll cover **Tuple (`tuple`)** in the same depth:

* Internal memory structure
* Why tuple is immutable
* Why tuple is faster than list
* Memory comparison (`list` vs `tuple`)
* All tuple methods
* Packing and unpacking
* Real-world uses
* Interview questions (deep level)
