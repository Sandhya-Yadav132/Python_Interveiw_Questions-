# PART 1: DICTIONARY DATA TYPE (`dict`) — Deep Interview Notes

---

# Q1. What is Dictionary in Python?

## Answer:

A **Dictionary** is a **mutable, unordered (conceptually), collection of key-value pairs**.

It stores data in the form:

```
key : value
```

Dictionary is created using curly braces `{}`.

Example:

```python
student = {
    "name": "Sandhya",
    "age": 22,
    "course": "MCA"
}

print(student)
```

Output:

```python
{
'name': 'Sandhya',
'age': 22,
'course': 'MCA'
}
```

---

# Dictionary Properties

---

## 1. Stores Data as Key-Value Pair

Example:

```python
employee = {
    "id":101,
    "name":"Rahul"
}
```

Here:

```
id     → key
101    → value

name   → key
Rahul  → value
```

---

# 2. Keys Must Be Unique

Example:

```python
data = {
    "name":"Ram",
    "name":"Shyam"
}

print(data)
```

Output:

```python
{
'name':'Shyam'
}
```

The latest value replaces the previous value.

---

# 3. Keys Must Be Immutable

Valid keys:

```python
{
10:"number",
"python":"language",
(1,2):"tuple"
}
```

Invalid:

```python
{
[1,2]:"list"
}
```

Output:

```
TypeError: unhashable type: 'list'
```

---

# Why Dictionary Keys Need To Be Immutable?

Dictionary internally uses **hashing**.

Example:

```python
student = {
    "name":"Ram"
}
```

Python calculates:

```
hash("name")
        |
        ↓
memory location
```

If key changes, hash value changes.

Then Python cannot find the stored value.

Therefore keys must be immutable.

---

# Dictionary Internal Memory Structure (Very Important ⭐)

Dictionary uses a **Hash Table** internally.

Example:

```python
student = {
    "name":"Ram",
    "age":20
}
```

Memory:

```
              Hash Table


Index       Key          Value

  0
  1        "age"  -----> 20
  2
  3        "name" -----> Ram
```

Process:

```
key
 |
 ↓
hash(key)
 |
 ↓
calculate index
 |
 ↓
store value
```

---

# Why Dictionary Lookup is Fast?

Example:

```python
student["name"]
```

Python does not search every key.

It does:

```
"name"
  |
hash()
  |
direct location
  |
Ram
```

Average Complexity:

```
Access → O(1)
Search → O(1)
Insert → O(1)
Delete → O(1)
```

---

# Creating Dictionary

## 1. Normal Method

```python
person = {
    "name":"Amit",
    "age":25
}
```

---

## 2. Using dict()

```python
person = dict(
    name="Amit",
    age=25
)

print(person)
```

Output:

```python
{
'name':'Amit',
'age':25
}
```

---

# Accessing Dictionary Values

## Method 1: Using Key

```python
student = {
    "name":"Rahul",
    "age":20
}

print(student["name"])
```

Output:

```
Rahul
```

Problem:

If key does not exist:

```python
student["city"]
```

Output:

```
KeyError
```

---

# Method 2: get()

Safer method.

```python
student = {
    "name":"Rahul"
}

print(student.get("city"))
```

Output:

```
None
```

Custom default:

```python
print(student.get("city","Not Found"))
```

Output:

```
Not Found
```

---

# Difference Between [] and get()

| []                          | get()                       |
| --------------------------- | --------------------------- |
| Key missing → KeyError      | Key missing → None          |
| Less safe                   | Safer                       |
| Used when key is guaranteed | Used when key may not exist |

---

# Dictionary Methods

# 1. keys()

Returns all keys.

Example:

```python
student = {
    "name":"Ram",
    "age":20
}

print(student.keys())
```

Output:

```
dict_keys(['name','age'])
```

Convert into list:

```python
print(list(student.keys()))
```

Output:

```
['name','age']
```

---

# 2. values()

Returns all values.

```python
print(student.values())
```

Output:

```
dict_values(['Ram',20])
```

---

# 3. items()

Returns key-value pairs as tuples.

```python
print(student.items())
```

Output:

```
dict_items([
('name','Ram'),
('age',20)
])
```

---

## Real Use of items()

Dictionary looping:

```python
student={
    "name":"Ram",
    "age":20
}

for key,value in student.items():
    print(key,value)
```

Output:

```
name Ram
age 20
```

---

# 4. update()

Adds or updates values.

Example:

```python
student={
    "name":"Ram",
    "age":20
}


student.update({
    "age":21,
    "city":"Delhi"
})


print(student)
```

Output:

```
{
'name':'Ram',
'age':21,
'city':'Delhi'
}
```

---

# 5. pop()

Removes key and returns value.

Example:

```python
student={
    "name":"Ram",
    "age":20
}


x=student.pop("age")

print(x)
print(student)
```

Output:

```
20

{'name':'Ram'}
```

---

# 6. popitem()

Removes last inserted key-value pair.

Example:

```python
student={
    "name":"Ram",
    "age":20,
    "city":"Delhi"
}


student.popitem()

print(student)
```

Output:

```
{
'name':'Ram',
'age':20
}
```

---

# 7. setdefault()

Returns value of key.

If key does not exist, creates it.

Example:

```python
student={
    "name":"Ram"
}


student.setdefault("age",20)


print(student)
```

Output:

```
{
'name':'Ram',
'age':20
}
```

---

# Difference: get() vs setdefault()

| get()                      | setdefault()                   |
| -------------------------- | ------------------------------ |
| Only retrieves value       | Retrieves + inserts if missing |
| Does not modify dictionary | Can modify dictionary          |

---

# 8. clear()

Removes all elements.

```python
student.clear()

print(student)
```

Output:

```
{}
```

---

# Dictionary Copy

## Shallow Copy

```python
d1={
"a":[1,2]
}

d2=d1.copy()

d2["a"].append(3)

print(d1)
```

Output:

```
{
'a':[1,2,3]
}
```

Because nested list reference is shared.

(Deep copy will be covered separately.)

---

# Dictionary vs Set Memory Difference

Both use:

```
Hash Table
```

## Set:

Stores only values.

Example:

```python
s={10,20,30}
```

Memory:

```
Hash Table

10
20
30
```

---

## Dictionary:

Stores key + value.

Example:

```python
d={
"name":"Ram"
}
```

Memory:

```
Hash Table

Key        Value

name  ---> Ram
```

Dictionary needs more memory because it stores:

* key
* value
* hash information

---

# Dictionary vs List Memory

| List                       | Dictionary                        |
| -------------------------- | --------------------------------- |
| Stores values sequentially | Stores key-value using hash table |
| Search O(n)                | Search O(1) average               |
| Less memory                | More memory                       |
| Index based access         | Key based access                  |

---

# Real-Time Uses of Dictionary

## 1. User Profile (Web Application)

```python
user={
    "id":101,
    "username":"sandhya",
    "email":"abc@gmail.com"
}
```

Used in:

* Django models
* API responses
* JSON data

---

## 2. API Response

Example:

```python
response={
    "status":"success",
    "data":{
        "product":"Laptop",
        "price":50000
    }
}
```

Very common in REST APIs.

---

## 3. Counting Frequency

Example:

```python
text="python"

count={}

for ch in text:
    if ch in count:
        count[ch]+=1
    else:
        count[ch]=1

print(count)
```

Output:

```
{
'p':1,
'y':1,
't':1,
'h':1,
'o':1,
'n':1
}
```

---

## 4. Caching Data

Example:

```python
cache={}

cache["user_101"]="Ram"
```

Fast retrieval:

```python
cache["user_101"]
```

---

# Interview Questions ⭐

## Q1. Why dictionary lookup is O(1)?

Answer:

Dictionary uses a hash table. Python calculates the hash of the key and directly accesses the memory location instead of searching all elements.

---

## Q2. Can we use list as dictionary key?

Answer:

No.

Reason:

List is mutable and unhashable.

Example:

```python
{
[1,2]:"data"
}
```

Error:

```
TypeError: unhashable type: 'list'
```

---

## Q3. Are dictionaries ordered in Python?

Answer:

Before Python 3.7:

```
Order was not guaranteed
```

Python 3.7+:

```
Insertion order is preserved officially.
```

Example:

```python
d={
"a":1,
"b":2,
"c":3
}

print(d)
```

Output:

```
{'a':1,'b':2,'c':3}
```

---

## Q4. Why dictionary is faster than list?

Answer:

Because:

List:

```
Linear search
O(n)
```

Dictionary:

```
Hash lookup
O(1)
```

---

# Next Topic:

## Remaining Python Built-in Data Types

We'll cover:

1. `range`
2. `bytes`
3. `bytearray`
4. `memoryview`
5. `NoneType`

Then:

➡️ Lambda Function
➡️ map()
➡️ filter()
➡️ reduce()
➡️ Practical interview programs.
