# PART 1: SET DATA TYPE (Deep Interview Notes)

---

# Q1. What is Set in Python?

## Answer:

A **Set** is an **unordered, mutable collection of unique elements**.

Set is represented using curly braces `{}`.

Example:

```python id="a1"
s = {10, 20, 30}

print(s)
print(type(s))
```

Output:

```python
{10,20,30}

<class 'set'>
```

---

# Important Properties of Set

## 1. Unordered

Set does not maintain insertion order.

Example:

```python id="a2"
s = {10,20,30,40}

print(s)
```

Output may be:

```python
{40,10,30,20}
```

Order is not guaranteed.

---

## 2. No Duplicate Values

Set automatically removes duplicate values.

Example:

```python id="a3"
s = {10,20,20,30,30}

print(s)
```

Output:

```python
{10,20,30}
```

---

## 3. Mutable

Set can be modified after creation.

Example:

```python id="a4"
s={10,20,30}

s.add(40)

print(s)
```

Output:

```python
{10,20,30,40}
```

---

## 4. Only Immutable Elements Allowed

A set can contain:

✅ int
✅ float
✅ string
✅ tuple

Cannot contain:

❌ list
❌ dictionary
❌ set

Example:

Valid:

```python id="a5"
s={10,"Python",(1,2)}

print(s)
```

---

Invalid:

```python id="a6"
s={[1,2,3]}
```

Output:

```
TypeError: unhashable type: 'list'
```

---

# Empty Set Creation (Important Interview Question)

Wrong:

```python id="a7"
s={}
```

This creates dictionary.

Check:

```python id="a8"
print(type(s))
```

Output:

```
<class 'dict'>
```

---

Correct:

```python id="a9"
s=set()

print(type(s))
```

Output:

```
<class 'set'>
```

---

# Internal Memory Structure of Set (Very Important)

Set internally uses a **Hash Table**.

Example:

```python
s={10,20,30}
```

Memory representation:

```
             Hash Table

Index       Value

 0            -
 1            20
 2            -
 3            10
 4            30
```

Python does not store values sequentially like list.

It calculates hash value:

```
hash(value) → memory location
```

and stores element there.

---

# Why Set is Faster for Searching?

Example:

List:

```python
numbers=[10,20,30,40,50]

20 in numbers
```

Python checks one by one:

```
10 → 20 → found
```

Time Complexity:

```
O(n)
```

---

Set:

```python
numbers={10,20,30,40,50}

20 in numbers
```

Python:

```
hash(20)
 ↓
direct location
```

Average Time Complexity:

```
O(1)
```

---

# Why Set Removes Duplicates?

Because set uses hashing.

Example:

```python
s={10,10,10}
```

Python calculates:

```
hash(10)
hash(10)
hash(10)
```

Same hash location.

It stores only one value.

Result:

```python
{10}
```

---

# Set Methods

# 1. add()

Adds single element.

Example:

```python
s={1,2,3}

s.add(4)

print(s)
```

Output:

```
{1,2,3,4}
```

Time Complexity:

```
O(1)
```

---

# 2. update()

Adds multiple elements.

Example:

```python
s={1,2}

s.update([3,4,5])

print(s)
```

Output:

```
{1,2,3,4,5}
```

Difference:

| add()               | update()               |
| ------------------- | ---------------------- |
| Adds one element    | Adds multiple elements |
| Takes single object | Takes iterable         |

---

Example:

```python
s={1,2}

s.add([3,4])
```

Error:

```
TypeError
```

Because list is unhashable.

---

But:

```python
s={1,2}

s.update([3,4])
```

Works.

---

# 3. remove()

Removes element.

Example:

```python
s={10,20,30}

s.remove(20)

print(s)
```

Output:

```
{10,30}
```

If element doesn't exist:

```python
s.remove(100)
```

Output:

```
KeyError
```

---

# 4. discard()

Removes element safely.

Example:

```python
s={10,20,30}

s.discard(100)

print(s)
```

Output:

```
{10,20,30}
```

No error.

---

# remove() vs discard()

| remove()                | discard()                  |
| ----------------------- | -------------------------- |
| Element missing → error | Element missing → no error |
| Strict                  | Safe                       |

---

# 5. pop()

Removes random element.

Example:

```python
s={10,20,30}

x=s.pop()

print(x)
print(s)
```

Output:

```
10
{20,30}
```

Important:

Because set is unordered, we don't know which element will remove.

---

# 6. clear()

Remove all elements.

```python
s={1,2,3}

s.clear()

print(s)
```

Output:

```
set()
```

---

# Mathematical Set Operations

## 7. Union()

Combines two sets.

Example:

```python
a={1,2,3}

b={3,4,5}

print(a.union(b))
```

Output:

```
{1,2,3,4,5}
```

Operator:

```python
a | b
```

---

# 8. Intersection()

Common elements.

Example:

```python
a={1,2,3}

b={2,3,4}

print(a.intersection(b))
```

Output:

```
{2,3}
```

Operator:

```python
a & b
```

---

# 9. Difference()

Elements present in first set but not second.

Example:

```python
a={1,2,3}

b={2,3,4}

print(a.difference(b))
```

Output:

```
{1}
```

Operator:

```python
a-b
```

---

# 10. Symmetric Difference()

Elements present in either set but not common.

Example:

```python
a={1,2,3}

b={2,3,4}

print(a.symmetric_difference(b))
```

Output:

```
{1,4}
```

Operator:

```python
a ^ b
```

---

# Set vs List (Memory + Performance)

| List                           | Set                            |
| ------------------------------ | ------------------------------ |
| Stores references sequentially | Stores using hash table        |
| Ordered                        | Unordered                      |
| Allows duplicates              | Removes duplicates             |
| Search O(n)                    | Search O(1) average            |
| Index access possible          | No indexing                    |
| Less memory                    | More memory because hash table |

---

# Set vs Dictionary Memory Difference

Both use hashing internally.

## Set:

Stores only values.

Example:

```python
s={10,20,30}
```

Memory:

```
Hash Table

value
 |
10
20
30
```

---

## Dictionary:

Stores key-value pairs.

Example:

```python
d={
"name":"Ram",
"age":20
}
```

Memory:

```
Hash Table

key        value

name  ---> Ram
age   ---> 20
```

Dictionary requires extra memory for values.

---

# Real-Time Uses of Set

## 1. Remove Duplicate Data

Example:

User IDs:

```python
users=[101,102,101,103,102]

unique_users=set(users)

print(unique_users)
```

Output:

```
{101,102,103}
```

---

## 2. Finding Common Data

Example:

Two websites users:

```python
site1={"Ram","Amit","John"}

site2={"John","Amit","Raj"}

common=site1 & site2

print(common)
```

Output:

```
{'John','Amit'}
```

---

## 3. Permission Management

Example:

```python
admin_permission={
"read",
"write",
"delete"
}
```

Fast checking:

```python
"delete" in admin_permission
```

---

## 4. AI / ML Data Processing

Remove duplicate words:

```python
sentence="python python django django"

words=sentence.split()

unique=set(words)

print(unique)
```

Output:

```
{'python','django'}
```

---

# Interview Questions ⭐

## Q1. Why set does not support indexing?

Answer:

Because set elements are stored according to hash values, not sequential positions.

Example:

```python
s={10,20,30}

s[0]
```

Error:

```
TypeError
```

---

## Q2. Why list cannot be stored inside set?

Answer:

Because set requires hashable objects.

List is mutable, so its hash value can change.

Therefore list is unhashable.

---

## Q3. Why searching in set is faster than list?

Answer:

Set uses hash table.

It directly calculates the hash and accesses the memory location.

Average complexity:

```
Set → O(1)

List → O(n)
```

---

## Q4. Can set contain tuple?

Yes, because tuple is immutable.

Example:

```python
s={(1,2),(3,4)}

print(s)
```

Works.

---

# Next Topic:

## Dictionary (`dict`) Data Type

We'll cover:

✅ Dictionary internal memory structure (Hash Table)
✅ How key-value storage works
✅ Why dictionary lookup is O(1)
✅ All dictionary methods:

* get()
* keys()
* values()
* items()
* update()
* pop()
* popitem()
* setdefault()

✅ Dict vs Set memory comparison
✅ Real-world Django/API examples
✅ Interview questions (hashing, mutable keys, ordered dictionary behavior)
