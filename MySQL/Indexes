# Topic 16: Indexes ⭐⭐⭐⭐⭐ (Very Important for Freshers)

> **Interview Reality:**
> If you mention **MySQL**, **Django ORM**, or **Backend Development** on your resume, interviewers often ask:
>
> * What is an Index?
> * Why do we use an Index?
> * Does an Index increase INSERT speed?
> * Which column should be indexed?

---

# 1. What is an Index?

## Definition (Interview Answer)

An **Index** is a database object that **improves the speed of data retrieval (SELECT queries)** by creating a fast lookup structure on one or more columns.

### Short Interview Answer

> "An Index is used to speed up data retrieval from a table. It works similarly to the index of a book, allowing the database to find data without scanning every row."

---

# 2. Why Do We Use an Index?

Suppose an **employees** table contains **10 lakh (1,000,000) records**.

Without an index:

Searching for

```sql
SELECT *
FROM employees
WHERE email='abc@gmail.com';
```

The database may scan every row until it finds the match.

With an index:

The database can quickly locate the required row using the indexed column.

Result:

* Faster search
* Better performance

---

# 3. Real-Life Example

Imagine a **book** with 1,000 pages.

Without an index:

You read page by page to find **"Python"**.

With an index:

You check the index page.

```
Python → Page 320
```

You directly go to page 320.

A database index works in a similar way.

---

# 4. Syntax

## Create Index

```sql
CREATE INDEX idx_email
ON employees(email);
```

---

## Remove Index

```sql
DROP INDEX idx_email
ON employees;
```

---

# 5. Sample Table

| id | name    | email                                         |
| -- | ------- | --------------------------------------------- |
| 1  | Rahul   | [rahul@gmail.com](mailto:rahul@gmail.com)     |
| 2  | Sandhya | [sandhya@gmail.com](mailto:sandhya@gmail.com) |
| 3  | Aman    | [aman@gmail.com](mailto:aman@gmail.com)       |

Searching by email becomes much faster if `email` is indexed.

---

# 6. Advantages of Index ⭐⭐⭐⭐⭐

### Faster SELECT Queries

Searching becomes much faster.

---

### Faster WHERE Clause

```sql
SELECT *
FROM employees
WHERE email='abc@gmail.com';
```

---

### Faster JOIN Operations

```sql
SELECT *
FROM employees e
JOIN departments d
ON e.dept_id = d.dept_id;
```

If `dept_id` is indexed, joins are usually faster.

---

### Faster ORDER BY

```sql
ORDER BY name;
```

Indexes can help with sorting in many cases.

---

### Faster GROUP BY

Grouping may also benefit from indexes depending on the query and index.

---

# 7. Disadvantages of Index ⭐⭐⭐⭐⭐

### Slower INSERT

```sql
INSERT INTO employees ...
```

The index also needs to be updated.

---

### Slower UPDATE

Updating an indexed column requires updating the index.

---

### Slower DELETE

Deleting rows also requires index maintenance.

---

### More Storage

Indexes consume additional disk space.

---

# 8. When Should We Create an Index?

Create an index on columns that are:

✅ Frequently searched

```sql
WHERE email=...
```

---

✅ Used in JOIN

```sql
ON dept_id
```

---

✅ Used in ORDER BY

---

✅ Used in GROUP BY

---

# 9. When Should We NOT Create an Index?

Avoid indexing columns that:

❌ Change very frequently.

---

❌ Have very few unique values (for example, a boolean status with only two values), because such indexes are often less effective.

---

❌ Are in very small tables where a full table scan is already fast.

---

# 10. Primary Key and Index

Interview Question:

**Is a PRIMARY KEY indexed?**

Answer:

**Yes.**

MySQL automatically creates an index for the PRIMARY KEY.

---

# 11. UNIQUE and Index

Interview Question:

**Does UNIQUE create an index?**

Answer:

**Yes.**

A UNIQUE constraint is enforced using a unique index.

---

# 12. Types of Indexes (Fresher Level)

## Primary Index

Automatically created for the PRIMARY KEY.

---

## Unique Index

Created for UNIQUE columns.

---

## Normal (Non-Unique) Index

Created manually.

```sql
CREATE INDEX idx_name
ON employees(name);
```

---

## Composite Index ⭐⭐⭐⭐

Index on multiple columns.

```sql
CREATE INDEX idx_name_city
ON employees(name, city);
```

Useful when queries filter by both columns.

---

# 13. Clustered vs Non-Clustered (Interview Concept)

Many interviewers ask this conceptually.

| Clustered Index                                         | Non-Clustered Index                 |
| ------------------------------------------------------- | ----------------------------------- |
| Data is stored in index order                           | Separate structure points to data   |
| One per table                                           | Multiple allowed                    |
| In MySQL InnoDB, the PRIMARY KEY is the clustered index | Secondary indexes are non-clustered |

> **Interview Note:** This behavior is specific to storage engines such as **InnoDB**. It's enough for a fresher to know that the PRIMARY KEY determines the clustered index in InnoDB.

---

# 14. Real Project Example

E-commerce website

Search by email

```sql
SELECT *
FROM users
WHERE email='abc@gmail.com';
```

Instead of scanning millions of rows, an index on `email` allows the database to find the user much faster.

---

# 15. Common Interview Questions

### Q1. What is an Index?

Improves search performance.

---

### Q2. Why do we use an Index?

To speed up data retrieval.

---

### Q3. Does an Index improve INSERT?

No.

It generally slows INSERT because the index must also be updated.

---

### Q4. Does an Index improve UPDATE?

Not always. Updates to indexed columns are generally slower.

---

### Q5. Does an Index consume storage?

Yes.

---

### Q6. Is PRIMARY KEY automatically indexed?

Yes.

---

### Q7. Is UNIQUE automatically indexed?

Yes.

---

### Q8. Which queries benefit the most from indexes?

* WHERE
* JOIN
* ORDER BY
* GROUP BY (in many cases)

---

### Q9. Can a table have multiple indexes?

Yes.

---

### Q10. Should every column have an index?

No.

Too many indexes reduce write performance.

---

# 16. Common Mistakes

❌ "Indexes improve every query."

Wrong.

Indexes mainly help **read operations** and not every query can use them.

---

❌ "Indexes don't consume memory or storage."

Wrong.

They require additional storage.

---

❌ "More indexes always mean better performance."

Wrong.

Too many indexes slow INSERT, UPDATE, and DELETE operations.

---

# 17. Best Interview Answer

> "An Index is a database structure that improves the speed of data retrieval. It is commonly created on columns used in WHERE, JOIN, ORDER BY, and GROUP BY clauses. While indexes make SELECT queries faster, they increase storage usage and can slow INSERT, UPDATE, and DELETE operations because the index must be maintained."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What is an Index?

**Answer:** A structure that speeds up data retrieval.

---

### Q2. Why do we use an Index?

**Answer:** To improve SELECT query performance.

---

### Q3. Which SQL operation benefits the most from indexes?

**Answer:** SELECT.

---

### Q4. Which operations become slower because of indexes?

**Answer:** INSERT, UPDATE, DELETE.

---

### Q5. Does an Index consume storage?

**Answer:** Yes.

---

### Q6. Is the PRIMARY KEY automatically indexed?

**Answer:** Yes.

---

### Q7. Is a UNIQUE column automatically indexed?

**Answer:** Yes.

---

### Q8. Can a table have multiple indexes?

**Answer:** Yes.

---

### Q9. Should every column be indexed?

**Answer:** No.

---

### Q10. What is a composite index?

**Answer:** An index created on multiple columns.

---

# ⭐ Must Remember (30-Second Revision)

| Feature          | Index                  |
| ---------------- | ---------------------- |
| Purpose          | Faster data retrieval  |
| Improves         | SELECT                 |
| Slows            | INSERT, UPDATE, DELETE |
| Uses Storage     | Yes                    |
| PRIMARY KEY      | Automatically indexed  |
| UNIQUE           | Automatically indexed  |
| Multiple Indexes | Allowed                |

---

# 🔥 Cross Questions (Frequently Asked)

## Q1. PRIMARY KEY Index vs Normal Index ⭐⭐⭐⭐⭐

| PRIMARY KEY Index         | Normal Index                    |
| ------------------------- | ------------------------------- |
| Created automatically     | Created manually                |
| Unique                    | Can contain duplicate values    |
| Cannot contain NULL       | Can index nullable columns      |
| One PRIMARY KEY per table | Multiple normal indexes allowed |

---

## Q2. Why Not Create an Index on Every Column? ⭐⭐⭐⭐⭐

Because:

* It increases storage usage.
* It slows INSERT operations.
* It slows UPDATE operations.
* It slows DELETE operations.
* Many indexes may not be used by queries.

---

