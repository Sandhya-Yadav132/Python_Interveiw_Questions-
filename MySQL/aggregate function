# Topic 11: Aggregate Functions ⭐⭐⭐⭐⭐ (Most Important)

> **Interview Reality:**
> Aggregate functions are asked in almost every SQL interview. They are often combined with **GROUP BY** and **HAVING**.

---

# 1. What are Aggregate Functions?

## Definition (Interview Answer)

**Aggregate functions** perform calculations on **multiple rows** and return **a single value**.

### Short Interview Answer

> "Aggregate functions are SQL functions that perform calculations on multiple rows and return a single result."

---

# 2. Why do We Use Aggregate Functions?

Suppose a company has **10,000 employees**.

Instead of calculating manually:

* Total salary
* Average salary
* Highest salary
* Lowest salary
* Total employees

SQL does it using aggregate functions.

---

# 3. Types of Aggregate Functions

There are **5 important aggregate functions**.

* COUNT()
* SUM()
* AVG()
* MIN()
* MAX()

⭐⭐⭐⭐⭐ These five are enough for most fresher interviews.

---

# Sample Table

## employees

| id | name    | department | salary |
| -- | ------- | ---------- | ------ |
| 1  | Rahul   | IT         | 40000  |
| 2  | Sandhya | HR         | 50000  |
| 3  | Aman    | IT         | 45000  |
| 4  | Priya   | Sales      | 60000  |
| 5  | Rohit   | HR         | 55000  |

---

# 1. COUNT()

## Definition

Returns the **number of rows**.

### Syntax

```sql
SELECT COUNT(*)
FROM employees;
```

### Output

```text
5
```

There are **5 employees**.

---

### COUNT(column)

```sql
SELECT COUNT(salary)
FROM employees;
```

Counts **non-NULL** salary values.

---

### COUNT(*)

Counts **all rows**.

---

# 2. SUM()

## Definition

Returns the **total sum** of a numeric column.

### Syntax

```sql
SELECT SUM(salary)
FROM employees;
```

### Output

```text
250000
```

---

# 3. AVG()

## Definition

Returns the **average** value.

### Syntax

```sql
SELECT AVG(salary)
FROM employees;
```

### Output

```text
50000
```

---

# 4. MIN()

## Definition

Returns the **smallest value**.

### Syntax

```sql
SELECT MIN(salary)
FROM employees;
```

### Output

```text
40000
```

---

# 5. MAX()

## Definition

Returns the **largest value**.

### Syntax

```sql
SELECT MAX(salary)
FROM employees;
```

### Output

```text
60000
```

---

# 4. Using WHERE with Aggregate Functions

### Highest salary in IT Department

```sql
SELECT MAX(salary)
FROM employees
WHERE department='IT';
```

Output

```text
45000
```

---

### Average salary in HR

```sql
SELECT AVG(salary)
FROM employees
WHERE department='HR';
```

Output

```text
52500
```

---

# 5. COUNT(*) vs COUNT(column) ⭐⭐⭐⭐⭐

Suppose:

| id | salary |
| -- | ------ |
| 1  | 40000  |
| 2  | NULL   |
| 3  | 50000  |

### COUNT(*)

```sql
SELECT COUNT(*)
FROM employees;
```

Output

```text
3
```

Counts **every row**.

---

### COUNT(salary)

```sql
SELECT COUNT(salary)
FROM employees;
```

Output

```text
2
```

Because **NULL values are ignored**.

---

# 6. Real-Life Example

E-commerce Website

* Total Orders → COUNT()
* Total Revenue → SUM()
* Average Product Price → AVG()
* Highest Price → MAX()
* Lowest Price → MIN()

---

# 7. Common Interview Questions

### Q1. What are aggregate functions?

Functions that perform calculations on multiple rows and return a single value.

---

### Q2. Name five aggregate functions.

* COUNT()
* SUM()
* AVG()
* MIN()
* MAX()

---

### Q3. Which function counts rows?

COUNT()

---

### Q4. Which function returns total salary?

SUM()

---

### Q5. Which function returns average salary?

AVG()

---

### Q6. Which function returns the highest salary?

MAX()

---

### Q7. Which function returns the lowest salary?

MIN()

---

### Q8. Can aggregate functions ignore NULL values?

**Yes.** Most aggregate functions ignore NULL values.

---

### Q9. Can aggregate functions be used with WHERE?

Yes.

---

### Q10. Which aggregate function works with text columns?

COUNT() can count non-NULL text values.

---

# 8. Common Mistakes

❌

Thinking COUNT(column) counts NULL values.

Wrong.

It ignores NULL.

---

❌

Using SUM() on VARCHAR.

Wrong.

SUM() works with numeric columns.

---

❌

Thinking AVG() works on text.

Wrong.

AVG() requires numeric values.

---

# 9. Best Interview Answer

> "Aggregate functions perform calculations on multiple rows and return a single result. The most commonly used aggregate functions are COUNT(), SUM(), AVG(), MIN(), and MAX(). They are used for operations such as counting records, calculating totals, averages, minimum values, and maximum values."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What are aggregate functions?

**Answer:** Functions that calculate values from multiple rows and return one result.

---

### Q2. Name five aggregate functions.

**Answer:** COUNT(), SUM(), AVG(), MIN(), MAX().

---

### Q3. Which function counts rows?

**Answer:** COUNT().

---

### Q4. Which function calculates the total?

**Answer:** SUM().

---

### Q5. Which function calculates the average?

**Answer:** AVG().

---

### Q6. Which function finds the minimum value?

**Answer:** MIN().

---

### Q7. Which function finds the maximum value?

**Answer:** MAX().

---

### Q8. Does COUNT(column) count NULL values?

**Answer:** No.

---

### Q9. Which function is used to count all rows?

**Answer:** COUNT(*).

---

### Q10. Can aggregate functions be used with WHERE?

**Answer:** Yes.

---

# ⭐ Must Remember (30-Second Revision)

| Function  | Purpose                 |
| --------- | ----------------------- |
| `COUNT()` | Counts rows             |
| `SUM()`   | Total of numeric values |
| `AVG()`   | Average value           |
| `MIN()`   | Smallest value          |
| `MAX()`   | Largest value           |

---

# 🔥 Cross Questions (Very Frequently Asked)

## Q1. COUNT(*) vs COUNT(column) ⭐⭐⭐⭐⭐

| COUNT(*)                                          | COUNT(column)                                  |
| ------------------------------------------------- | ---------------------------------------------- |
| Counts all rows                                   | Counts only non-NULL values                    |
| NULL values are included because rows are counted | NULL values are ignored                        |
| Most commonly used                                | Used when counting values in a specific column |

Example:

| id | salary |
| -- | ------ |
| 1  | 40000  |
| 2  | NULL   |
| 3  | 50000  |

```sql
SELECT COUNT(*) FROM employees;
```

**Output:** `3`

```sql
SELECT COUNT(salary) FROM employees;
```

**Output:** `2`

---

## Q2. Can Aggregate Functions Be Used Without GROUP BY?

**Yes.**

Example:

```sql
SELECT AVG(salary)
FROM employees;
```

Returns the average salary of **all employees**.

---

