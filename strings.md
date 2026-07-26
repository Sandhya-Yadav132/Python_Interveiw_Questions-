# PART 1: PYTHON DATA TYPES (CONTINUED)

# Q5. String Data Type (`str`)

## Answer:

A **String** is a sequence of characters enclosed inside:

* Single quotes `' '`
* Double quotes `" "`
* Triple quotes `''' '''` or `""" """`

Example:

```python
name = "Python"

print(type(name))
```

Output:

```python
<class 'str'>
```

---

## Important Properties of String

### 1. String is Immutable

Once a string object is created, it cannot be modified.

Example:

```python
name = "Python"

name = name + " Programming"

print(name)
```

Output:

```
Python Programming
```

Here a new string object is created.

Original `"Python"` is not changed.

---

## String Indexing

Every character has an index.

Example:

```python
language = "Python"

print(language[0])
print(language[-1])
```

Output:

```
P
n
```

Index:

```
 P   y   t   h   o   n
 0   1   2   3   4   5

-6  -5  -4  -3  -2  -1
```

---

# String Methods

## 1. upper()

Converts string into uppercase.

Example:

```python
name = "python"

print(name.upper())
```

Output:

```
PYTHON
```

---

## 2. lower()

Converts string into lowercase.

```python
name = "PYTHON"

print(name.lower())
```

Output:

```
python
```

---

## 3. capitalize()

First character becomes uppercase.

```python
text = "python programming"

print(text.capitalize())
```

Output:

```
Python programming
```

---

## 4. title()

First letter of every word becomes uppercase.

```python
text = "python programming"

print(text.title())
```

Output:

```
Python Programming
```

---

## 5. swapcase()

Changes uppercase to lowercase and vice versa.

```python
text = "PyThOn"

print(text.swapcase())
```

Output:

```
pYtHoN
```

---

# Searching Methods

## 6. find()

Returns index of first occurrence.

If value is not found:

```
-1
```

Example:

```python
text = "python programming"

print(text.find("pro"))
```

Output:

```
7
```

---

## 7. index()

Same as find(), but gives error if value not found.

```python
text = "python"

print(text.index("x"))
```

Output:

```
ValueError
```

---

## Difference Between find() and index()

| find()                            | index()                   |
| --------------------------------- | ------------------------- |
| Returns -1 if not found           | Raises ValueError         |
| Safer                             | Strict                    |
| Used when searching optional data | Used when data must exist |

---

# Checking Methods

## 8. isalpha()

Checks only alphabets.

```python
name="Python"

print(name.isalpha())
```

Output:

```
True
```

---

## 9. isdigit()

Checks digits only.

```python
number="123"

print(number.isdigit())
```

Output:

```
True
```

---

## 10. isalnum()

Checks alphabet + numbers.

```python
value="Python123"

print(value.isalnum())
```

Output:

```
True
```

---

## 11. isspace()

Checks spaces.

```python
x="   "

print(x.isspace())
```

Output:

```
True
```

---

# Modification Methods

## 12. replace()

Replace old value with new value.

Example:

```python
text="I like Java"

new=text.replace("Java","Python")

print(new)
```

Output:

```
I like Python
```

Real Example:

Password masking:

```python
password="123456"

print(password.replace("123","***"))
```

Output:

```
***456
```

---

## 13. strip()

Removes spaces from both sides.

```python
name="   Python   "

print(name.strip())
```

Output:

```
Python
```

---

## 14. lstrip()

Remove left spaces.

```python
text="   Hello"

print(text.lstrip())
```

---

## 15. rstrip()

Remove right spaces.

```python
text="Hello   "

print(text.rstrip())
```

---

# Split and Join

## 16. split()

Converts string into list.

Example:

```python
data="Python Django AI"

result=data.split()

print(result)
```

Output:

```
['Python','Django','AI']
```

Real Example:

CSV Data Processing:

```python
record="Ram,25,Delhi"

print(record.split(","))
```

Output:

```
['Ram','25','Delhi']
```

---

## 17. join()

Joins list elements into string.

Example:

```python
words=['Python','Django']

result=" ".join(words)

print(result)
```

Output:

```
Python Django
```

---

# String Formatting

## 18. format()

```python
name="Sandhya"
age=22

print("My name is {} and age is {}".format(name,age))
```

Output:

```
My name is Sandhya and age is 22
```

---

## 19. f-string (Python 3.6+)

Most recommended.

```python
name="Sandhya"
age=22

print(f"My name is {name} and age is {age}")
```

---

# String Slicing

Syntax:

```python
string[start:end:step]
```

Example:

```python
text="Python"

print(text[0:3])
```

Output:

```
Pyt
```

Reverse:

```python
text="Python"

print(text[::-1])
```

Output:

```
nohtyP
```

---

# Practical Interview Program

## Reverse a String

### Method 1: Slicing

```python
text="Python"

reverse=text[::-1]

print(reverse)
```

Output:

```
nohtyP
```

---

### Method 2: Loop

```python
text="Python"

result=""

for char in text:
    result=char+result

print(result)
```

Output:

```
nohtyP
```

---

# Interview Cross Questions

## Q1. Why String is immutable in Python?

Answer:

String immutability provides:

1. Security
2. Memory optimization
3. Hashing support
4. Faster dictionary lookup

Example:

Dictionary keys must be immutable:

```python
data={
"Python":100
}
```

String can be used as key because it cannot change.

---

## Q2. Difference between mutable and immutable?

| Mutable                     | Immutable                |
| --------------------------- | ------------------------ |
| Can change after creation   | Cannot change            |
| Same memory object modified | New object created       |
| Example: list, dict, set    | Example: int, str, tuple |

---

## Q3. Why string concatenation inside loop is expensive?

Example:

```python
result=""

for i in range(10000):
    result += str(i)
```

Because every concatenation creates a new string object.

Better:

```python
data=[]

for i in range(10000):
    data.append(str(i))

result="".join(data)
```

Time complexity improves.

---

## Real-Time Uses of String

### Web Development

URL handling:

```python
url="https://example.com/product"
```

### AI/ML

Text preprocessing:

```python
sentence.lower()
sentence.split()
```

### Data Processing

CSV parsing:

```python
line.split(",")
```

---

# Next Topic:

## List Data Type

Covering:

✅ List internal memory
✅ Mutable behavior
✅ All important list methods
✅ append vs extend vs insert
✅ remove vs pop vs del
✅ shallow copy relation
✅ list comprehension
✅ real-time examples
✅ interview questions

(Next part continues)
