# Topic 14: SQL JOINS ⭐⭐⭐⭐⭐ (Most Important Topic for Freshers)

> **Interview Reality:**
> If you mention **MySQL, Django ORM, or Backend** on your resume, there is a very high chance you'll be asked about **JOINS**.

---

# 1. What is a JOIN?

## Definition (Interview Answer)

A **JOIN** is used to combine rows from **two or more tables** based on a related column.

### Short Interview Answer

> "A JOIN is used to retrieve related data from multiple tables by matching a common column, usually a Primary Key and a Foreign Key."

---

# 2. Why do We Use JOIN?

Suppose you have two tables:

### Employees Table

| emp_id | name    | dept_id |
| ------ | ------- | ------- |
| 1      | Rahul   | 101     |
| 2      | Sandhya | 102     |
| 3      | Aman    | 101     |
| 4      | Priya   | 103     |

---

### Departments Table

| dept_id | department |
| ------- | ---------- |
| 101     | IT         |
| 102     | HR         |
| 103     | Sales      |

The Employees table has only **dept_id**, not the department name.

To display:

| Employee | Department |
| -------- | ---------- |
| Rahul    | IT         |
| Sandhya  | HR         |
| Aman     | IT         |
| Priya    | Sales      |

We use a **JOIN**.

---

# 3. Types of JOINS

There are **5 important joins**:

1. INNER JOIN ⭐⭐⭐⭐⭐
2. LEFT JOIN ⭐⭐⭐⭐⭐
3. RIGHT JOIN ⭐⭐⭐⭐
4. FULL OUTER JOIN ⭐⭐⭐
5. CROSS JOIN ⭐⭐⭐

---

# 4. INNER JOIN ⭐⭐⭐⭐⭐

## Definition

Returns **only the matching rows** from both tables.

### Syntax

```sql
SELECT e.name, d.department
FROM employees e
INNER JOIN departments d
ON e.dept_id = d.dept_id;
```

### Output

| name    | department |
| ------- | ---------- |
| Rahul   | IT         |
| Sandhya | HR         |
| Aman    | IT         |
| Priya   | Sales      |

Only matching records are returned.

---

# 5. LEFT JOIN ⭐⭐⭐⭐⭐

## Definition

Returns:

* All rows from the **left table**
* Matching rows from the **right table**
* If no match exists, returns **NULL**

---

### Example

Employees

| emp_id | name    | dept_id |
| ------ | ------- | ------- |
| 1      | Rahul   | 101     |
| 2      | Sandhya | 102     |
| 3      | Aman    | 101     |
| 4      | Priya   | 105     |

Departments

| dept_id | department |
| ------- | ---------- |
| 101     | IT         |
| 102     | HR         |
| 103     | Sales      |

Query

```sql
SELECT e.name, d.department
FROM employees e
LEFT JOIN departments d
ON e.dept_id = d.dept_id;
```

Output

| name    | department |
| ------- | ---------- |
| Rahul   | IT         |
| Sandhya | HR         |
| Aman    | IT         |
| Priya   | NULL       |

Priya has no matching department.

---

# 6. RIGHT JOIN ⭐⭐⭐⭐

## Definition

Returns:

* All rows from the **right table**
* Matching rows from the **left table**
* If no match exists, returns **NULL**

---

Example

Departments

| dept_id | department |
| ------- | ---------- |
| 101     | IT         |
| 102     | HR         |
| 103     | Sales      |
| 104     | Marketing  |

Employees

| emp_id | name    | dept_id |
| ------ | ------- | ------- |
| 1      | Rahul   | 101     |
| 2      | Sandhya | 102     |

Query

```sql
SELECT e.name, d.department
FROM employees e
RIGHT JOIN departments d
ON e.dept_id = d.dept_id;
```

Output

| name    | department |
| ------- | ---------- |
| Rahul   | IT         |
| Sandhya | HR         |
| NULL    | Sales      |
| NULL    | Marketing  |

---

# 7. FULL OUTER JOIN ⭐⭐⭐

## Definition

Returns:

* All rows from the left table
* All rows from the right table
* Matching rows are merged
* Non-matching rows contain NULL

> **Important:** MySQL **does not support `FULL OUTER JOIN` directly.**

It can be simulated using:

```sql
SELECT ...
FROM A
LEFT JOIN B ON ...

UNION

SELECT ...
FROM A
RIGHT JOIN B ON ...;
```

⭐ This is a favorite interview question.

---

# 8. CROSS JOIN ⭐⭐⭐

## Definition

Returns the **Cartesian Product**.

Every row from the first table is combined with every row from the second table.

Example

2 employees

×

3 departments

=

6 rows

```sql
SELECT *
FROM employees
CROSS JOIN departments;
```

---

# 9. Visual Representation

```text
INNER JOIN
A ∩ B

LEFT JOIN
All A + Matching B

RIGHT JOIN
Matching A + All B

FULL OUTER JOIN
All A + All B

CROSS JOIN
Every A × Every B
```

---

# 10. Primary Key & Foreign Key Relation

Employees

| emp_id | name  | dept_id |
| ------ | ----- | ------- |
| 1      | Rahul | 101     |

Departments

| dept_id (PK) | department |
| ------------ | ---------- |
| 101          | IT         |

Relationship

```text
Departments.dept_id (Primary Key)
            │
            │
            ▼
Employees.dept_id (Foreign Key)
```

Most joins use a **Primary Key ↔ Foreign Key** relationship.

---

# 11. Real Project Example

### E-commerce

**Customers**

| customer_id | name    |
| ----------- | ------- |
| 1           | Sandhya |

**Orders**

| order_id | customer_id |
| -------- | ----------- |
| 101      | 1           |

To display:

```text
Sandhya → Order 101
```

Query

```sql
SELECT c.name, o.order_id
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id;
```

---

# 12. Common Interview Questions

### Q1. What is JOIN?

Used to combine data from multiple tables.

---

### Q2. Which JOIN returns only matching rows?

**INNER JOIN**

---

### Q3. Which JOIN returns all rows from the left table?

**LEFT JOIN**

---

### Q4. Which JOIN returns all rows from the right table?

**RIGHT JOIN**

---

### Q5. Which JOIN returns every possible combination?

**CROSS JOIN**

---

### Q6. Does MySQL support FULL OUTER JOIN?

**No.**

It must be simulated using `LEFT JOIN + UNION + RIGHT JOIN`.

---

### Q7. Which key is commonly used in JOIN?

**Primary Key** and **Foreign Key**.

---

### Q8. What is the purpose of the ON clause?

It specifies the condition used to match rows between tables.

---

### Q9. Can we join more than two tables?

**Yes.**

---

### Q10. What happens if you omit the ON clause in an INNER/LEFT/RIGHT JOIN?

It usually results in an error or unintended behavior, depending on the join type and SQL dialect. (`CROSS JOIN` intentionally has no `ON` condition.)

---

# 13. Common Mistakes

❌ Forgetting the `ON` condition.

```sql
SELECT *
FROM employees
JOIN departments;
```

This is incomplete for an `INNER JOIN`.

✔ Correct

```sql
SELECT *
FROM employees
JOIN departments
ON employees.dept_id = departments.dept_id;
```

---

❌ Thinking `LEFT JOIN` returns only matching rows.

Wrong.

It returns **all rows from the left table**, even when there is no match.

---

❌ Saying MySQL supports `FULL OUTER JOIN`.

Wrong.

It doesn't.

---

# 14. Best Interview Answer

> "A JOIN combines data from multiple tables using a related column, typically a Primary Key and a Foreign Key. The most common joins are INNER JOIN, LEFT JOIN, RIGHT JOIN, CROSS JOIN, and FULL OUTER JOIN (which is not directly supported in MySQL)."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What is a JOIN?

**Answer:** Used to combine data from multiple related tables.

---

### Q2. Which JOIN returns only matching rows?

**Answer:** INNER JOIN.

---

### Q3. Which JOIN returns all rows from the left table?

**Answer:** LEFT JOIN.

---

### Q4. Which JOIN returns all rows from the right table?

**Answer:** RIGHT JOIN.

---

### Q5. Which JOIN returns every possible combination?

**Answer:** CROSS JOIN.

---

### Q6. Does MySQL support FULL OUTER JOIN?

**Answer:** No.

---

### Q7. Which clause specifies the matching condition?

**Answer:** `ON`.

---

### Q8. Which keys are commonly used for joins?

**Answer:** Primary Key and Foreign Key.

---

### Q9. Can we join three or more tables?

**Answer:** Yes.

---

### Q10. Which JOIN is used most frequently in real projects?

**Answer:** INNER JOIN and LEFT JOIN.

---

# ⭐ Must Remember (30-Second Revision)

| JOIN            | Returns                                                     |
| --------------- | ----------------------------------------------------------- |
| INNER JOIN      | Only matching rows                                          |
| LEFT JOIN       | All left rows + matching right rows                         |
| RIGHT JOIN      | All right rows + matching left rows                         |
| FULL OUTER JOIN | All rows from both tables (not directly supported in MySQL) |
| CROSS JOIN      | Cartesian product (every combination)                       |

---

# 🔥 Cross Questions (Very Frequently Asked)

## Q1. INNER JOIN vs LEFT JOIN ⭐⭐⭐⭐⭐

| INNER JOIN                              | LEFT JOIN                                                             |
| --------------------------------------- | --------------------------------------------------------------------- |
| Returns only matching rows              | Returns all rows from the left table and matching rows from the right |
| Unmatched rows are excluded             | Unmatched right-side values become `NULL`                             |
| Most common for retrieving related data | Common when you need all records from the left table                  |

---

## Q2. Primary Key vs Foreign Key ⭐⭐⭐⭐⭐

| Primary Key                  | Foreign Key                                 |
| ---------------------------- | ------------------------------------------- |
| Uniquely identifies each row | References the Primary Key of another table |
| Must be unique               | Can contain duplicate values                |
| Cannot be `NULL` (typically) | May be `NULL` unless restricted             |
| One per table (typically)    | A table can have multiple foreign keys      |

---

