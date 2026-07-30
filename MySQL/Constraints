# Topic 15: Constraints ⭐⭐⭐⭐⭐ (Most Important for Freshers)

> **Interview Reality:**
> Almost every SQL interviewer asks:
>
> * What are constraints?
> * What is the difference between PRIMARY KEY and UNIQUE?
> * PRIMARY KEY vs FOREIGN KEY?
> * NOT NULL vs NULL?
> * AUTO_INCREMENT?

This is one of the **highest-priority MySQL topics**.

---

# 1. What are Constraints?

## Definition (Interview Answer)

**Constraints** are rules applied to table columns to ensure the **accuracy, validity, and integrity** of data.

### Short Interview Answer

> "Constraints are rules that enforce valid and consistent data in a database."

---

# 2. Why do We Use Constraints?

Without constraints, users could insert invalid data.

Example:

| id | name  | email                                 |
| -- | ----- | ------------------------------------- |
| 1  | Rahul | [abc@gmail.com](mailto:abc@gmail.com) |
| 1  | Aman  | [abc@gmail.com](mailto:abc@gmail.com) |

Problems:

* Duplicate ID
* Duplicate email
* Missing values
* Invalid references

Constraints prevent these issues.

---

# 3. Types of Constraints

There are **7 important constraints**.

| Constraint     | Purpose                               |
| -------------- | ------------------------------------- |
| PRIMARY KEY    | Uniquely identifies each row          |
| FOREIGN KEY    | Creates relationship between tables   |
| NOT NULL       | Prevents NULL values                  |
| UNIQUE         | Prevents duplicate values             |
| DEFAULT        | Assigns a default value               |
| CHECK          | Restricts values based on a condition |
| AUTO_INCREMENT | Automatically generates numbers       |

⭐⭐⭐⭐⭐ Learn all seven.

---

# 4. PRIMARY KEY ⭐⭐⭐⭐⭐

## Definition

A **PRIMARY KEY** uniquely identifies each record in a table.

### Rules

* Must be unique.
* Cannot be `NULL`.
* One primary key per table (it may consist of multiple columns as a composite key).

---

### Example

```sql
CREATE TABLE students(
    id INT PRIMARY KEY,
    name VARCHAR(50)
);
```

Valid

| id | name    |
| -- | ------- |
| 1  | Rahul   |
| 2  | Sandhya |

Invalid

| id | name  |
| -- | ----- |
| 1  | Rahul |
| 1  | Aman  |

Duplicate ID is not allowed.

---

# 5. FOREIGN KEY ⭐⭐⭐⭐⭐

## Definition

A **FOREIGN KEY** is a column that references the **PRIMARY KEY** of another table.

It maintains relationships between tables.

---

### Example

Departments

| dept_id | department |
| ------- | ---------- |
| 101     | IT         |
| 102     | HR         |

Employees

| emp_id | name  | dept_id |
| ------ | ----- | ------- |
| 1      | Rahul | 101     |

```sql
CREATE TABLE departments(
    dept_id INT PRIMARY KEY,
    department VARCHAR(30)
);

CREATE TABLE employees(
    emp_id INT PRIMARY KEY,
    name VARCHAR(50),
    dept_id INT,
    FOREIGN KEY(dept_id)
    REFERENCES departments(dept_id)
);
```

---

# 6. NOT NULL ⭐⭐⭐⭐

## Definition

A **NOT NULL** constraint ensures a column **must always have a value**.

### Example

```sql
CREATE TABLE students(
    id INT,
    name VARCHAR(50) NOT NULL
);
```

Valid

```text
Rahul
```

Invalid

```text
NULL
```

---

# 7. UNIQUE ⭐⭐⭐⭐⭐

## Definition

A **UNIQUE** constraint prevents duplicate values.

Unlike a PRIMARY KEY, a UNIQUE column can generally contain `NULL` values (MySQL allows multiple `NULL`s).

---

### Example

```sql
CREATE TABLE students(
    email VARCHAR(100) UNIQUE
);
```

Valid

```text
a@gmail.com
b@gmail.com
```

Invalid

```text
a@gmail.com
a@gmail.com
```

---

# 8. DEFAULT ⭐⭐⭐

## Definition

The **DEFAULT** constraint automatically assigns a value if none is provided.

---

### Example

```sql
CREATE TABLE students(
    city VARCHAR(30)
    DEFAULT 'Bhopal'
);
```

Insert

```sql
INSERT INTO students(name)
VALUES('Rahul');
```

Output

| name  | city   |
| ----- | ------ |
| Rahul | Bhopal |

---

# 9. CHECK ⭐⭐⭐

## Definition

The **CHECK** constraint ensures values satisfy a condition.

---

### Example

```sql
CREATE TABLE students(
    age INT
    CHECK(age >= 18)
);
```

Valid

```text
20
25
```

Invalid

```text
15
```

> **Interview Note:** Older MySQL versions ignored `CHECK` constraints. Modern MySQL versions enforce them.

---

# 10. AUTO_INCREMENT ⭐⭐⭐⭐⭐

## Definition

`AUTO_INCREMENT` automatically generates sequential numbers.

---

### Example

```sql
CREATE TABLE students(
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50)
);
```

Insert

```sql
INSERT INTO students(name)
VALUES('Rahul');
```

Output

| id | name  |
| -- | ----- |
| 1  | Rahul |

Next insert

```sql
INSERT INTO students(name)
VALUES('Sandhya');
```

Output

| id | name    |
| -- | ------- |
| 2  | Sandhya |

No need to manually enter IDs.

---

# 11. Real Project Example

### E-commerce

**Users Table**

```text
user_id → PRIMARY KEY
email → UNIQUE
name → NOT NULL
status → DEFAULT 'Active'
```

**Orders Table**

```text
order_id → PRIMARY KEY
user_id → FOREIGN KEY
```

---

# 12. Common Interview Questions

### Q1. What are constraints?

Rules that ensure valid and consistent data.

---

### Q2. Which constraint uniquely identifies a row?

PRIMARY KEY

---

### Q3. Which constraint creates relationships?

FOREIGN KEY

---

### Q4. Which constraint prevents NULL values?

NOT NULL

---

### Q5. Which constraint prevents duplicate values?

UNIQUE

---

### Q6. Which constraint automatically generates IDs?

AUTO_INCREMENT

---

### Q7. Which constraint assigns a default value?

DEFAULT

---

### Q8. Which constraint validates a condition?

CHECK

---

### Q9. Can a table have multiple PRIMARY KEY constraints?

**No.** A table can have only one PRIMARY KEY constraint, though it can be a composite (multi-column) key.

---

### Q10. Can a table have multiple UNIQUE constraints?

Yes.

---

# 13. Common Mistakes

❌ PRIMARY KEY allows NULL.

Wrong.

✔ PRIMARY KEY never allows NULL.

---

❌ UNIQUE and PRIMARY KEY are the same.

Wrong.

PRIMARY KEY:

* Unique
* No NULL

UNIQUE:

* Unique
* NULL handling differs (MySQL allows multiple NULLs).

---

❌ FOREIGN KEY must always be unique.

Wrong.

A FOREIGN KEY column can contain duplicate values because many rows can reference the same parent row.

---

# 14. Best Interview Answer

> "Constraints are rules applied to table columns to maintain data integrity. The most common constraints are PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, DEFAULT, CHECK, and AUTO_INCREMENT. They ensure that data remains accurate, valid, and consistent."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What are constraints?

**Answer:** Rules that ensure valid and consistent data.

---

### Q2. Which constraint uniquely identifies a row?

**Answer:** PRIMARY KEY.

---

### Q3. Which constraint creates table relationships?

**Answer:** FOREIGN KEY.

---

### Q4. Which constraint prevents NULL values?

**Answer:** NOT NULL.

---

### Q5. Which constraint prevents duplicate values?

**Answer:** UNIQUE.

---

### Q6. Which constraint assigns a default value?

**Answer:** DEFAULT.

---

### Q7. Which constraint validates values?

**Answer:** CHECK.

---

### Q8. Which constraint automatically generates IDs?

**Answer:** AUTO_INCREMENT.

---

### Q9. Can a table have more than one PRIMARY KEY?

**Answer:** No (except a composite primary key, which is still one PRIMARY KEY constraint).

---

### Q10. Can a table have multiple UNIQUE constraints?

**Answer:** Yes.

---

# ⭐ Must Remember (30-Second Revision)

| Constraint     | Purpose                     |
| -------------- | --------------------------- |
| PRIMARY KEY    | Unique + Not NULL           |
| FOREIGN KEY    | Relationship between tables |
| NOT NULL       | Value required              |
| UNIQUE         | No duplicate values         |
| DEFAULT        | Automatic default value     |
| CHECK          | Validates data              |
| AUTO_INCREMENT | Generates IDs automatically |

---

# 🔥 Cross Questions (Most Frequently Asked)

## Q1. PRIMARY KEY vs UNIQUE ⭐⭐⭐⭐⭐

| PRIMARY KEY                               | UNIQUE                                          |
| ----------------------------------------- | ----------------------------------------------- |
| Uniquely identifies each row              | Prevents duplicate values                       |
| Cannot contain NULL                       | In MySQL, can contain multiple NULL values      |
| Only one PRIMARY KEY constraint per table | Multiple UNIQUE constraints allowed             |
| Commonly used for table identity          | Commonly used for fields like email or username |

---

## Q2. PRIMARY KEY vs FOREIGN KEY ⭐⭐⭐⭐⭐

| PRIMARY KEY                       | FOREIGN KEY                                               |
| --------------------------------- | --------------------------------------------------------- |
| Identifies a row in its own table | References a PRIMARY KEY (or UNIQUE key) in another table |
| Must be unique                    | Can have duplicate values                                 |
| Cannot be NULL                    | May be NULL unless restricted                             |
| Parent table                      | Child table                                               |

---

