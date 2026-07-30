# Topic 20: Normalization ⭐⭐⭐⭐⭐ (Last Important Theory Topic for Freshers)

> **Interview Reality:**
>
> Normalization is one of the **top 10 SQL interview questions**.
>
> Freshers are usually asked:
>
> * What is Normalization?
> * Why do we use it?
> * What are 1NF, 2NF, and 3NF?

You **do not** need BCNF, 4NF, or 5NF for a fresher interview.

---

# 1. What is Normalization?

## Definition (Interview Answer)

**Normalization** is the process of organizing data into multiple related tables to **reduce data redundancy (duplicate data)** and **improve data consistency**.

### Short Interview Answer

> "Normalization is the process of organizing data to remove redundancy and improve data integrity."

---

# 2. Why Do We Use Normalization?

Suppose you have this table:

| Student_ID | Student_Name | Course | Teacher |
| ---------- | ------------ | ------ | ------- |
| 1          | Rahul        | Python | Amit    |
| 2          | Sandhya      | Python | Amit    |
| 3          | Aman         | Python | Amit    |

Problem:

The teacher name **"Amit"** is repeated in every row.

This is called **data redundancy**.

---

# 3. After Normalization

## Students Table

| Student_ID | Student_Name | Course_ID |
| ---------- | ------------ | --------- |
| 1          | Rahul        | 101       |
| 2          | Sandhya      | 101       |
| 3          | Aman         | 101       |

---

## Courses Table

| Course_ID | Course | Teacher |
| --------- | ------ | ------- |
| 101       | Python | Amit    |

Now the teacher name is stored only once.

Advantages:

* Less duplicate data
* Less storage
* Easy updates

---

# 4. First Normal Form (1NF) ⭐⭐⭐⭐⭐

## Rule

Each column should contain **only one value**.

No multiple values in one cell.

---

### Wrong

| Student | Languages    |
| ------- | ------------ |
| Rahul   | Python, Java |

One cell contains two values.

---

### Correct

| Student | Language |
| ------- | -------- |
| Rahul   | Python   |
| Rahul   | Java     |

Now each cell contains only one value.

---

# 5. Second Normal Form (2NF) ⭐⭐⭐⭐

## Rule

* Table must already be in **1NF**.
* Every non-key column should depend on the **entire Primary Key**, not just part of it.

### Fresher-Friendly Understanding

Store information in the table where it logically belongs.

Example:

Instead of storing **Teacher Name** repeatedly with every student, store teacher details in a separate table.

---

# 6. Third Normal Form (3NF) ⭐⭐⭐⭐

## Rule

* Table must already be in **2NF**.
* Non-key columns should depend **only on the Primary Key**, not on another non-key column.

### Example

### Wrong

| Emp_ID | Emp_Name | Dept_ID | Dept_Name |
| ------ | -------- | ------- | --------- |
| 1      | Rahul    | 101     | IT        |
| 2      | Sandhya  | 102     | HR        |

Here:

`Dept_Name` depends on `Dept_ID`, not directly on `Emp_ID`.

---

### Correct

## Employees

| Emp_ID | Emp_Name | Dept_ID |
| ------ | -------- | ------- |
| 1      | Rahul    | 101     |
| 2      | Sandhya  | 102     |

---

## Departments

| Dept_ID | Dept_Name |
| ------- | --------- |
| 101     | IT        |
| 102     | HR        |

---

# 7. Real-Life Example

### E-commerce Website

Instead of storing customer information in every order:

❌ Orders Table

| Order_ID | Customer_Name | Customer_Email |
| -------- | ------------- | -------------- |

Customer data is repeated.

---

✔ Customers Table

| Customer_ID | Name | Email |
| ----------- | ---- | ----- |

✔ Orders Table

| Order_ID | Customer_ID |
| -------- | ----------- |

Much better design.

---

# 8. Advantages of Normalization

* Reduces duplicate data
* Saves storage
* Improves consistency
* Makes updates easier
* Prevents insert, update, and delete anomalies

---

# 9. Disadvantages

* More tables
* More JOIN operations
* Slightly more complex queries

> **Interview Note:** In real projects, databases are often normalized, but sometimes selective **denormalization** is used for performance.

---

# 10. Common Interview Questions

### Q1. What is Normalization?

Process of reducing data redundancy.

---

### Q2. Why do we use Normalization?

To reduce duplicate data and improve consistency.

---

### Q3. What is 1NF?

One value per cell.

---

### Q4. What is 2NF?

Remove partial dependency.

(Fresher answer: Store related data in the correct table.)

---

### Q5. What is 3NF?

Remove transitive dependency.

(Fresher answer: Non-key columns should depend only on the Primary Key.)

---

### Q6. Which normal forms should a fresher know?

1NF

2NF

3NF

---

# 11. Best Interview Answer

> "Normalization is the process of organizing data into multiple related tables to reduce redundancy and improve consistency. The first three normal forms are most important for freshers: 1NF ensures atomic values, 2NF removes partial dependency, and 3NF removes transitive dependency."

---

# 📌 Interview Cheat Sheet

### Q1. What is Normalization?

**Answer:** Organizing data to reduce redundancy.

---

### Q2. Why do we use it?

**Answer:** To avoid duplicate data and improve consistency.

---

### Q3. What is 1NF?

**Answer:** One value in each cell.

---

### Q4. What is 2NF?

**Answer:** Remove partial dependency.

---

### Q5. What is 3NF?

**Answer:** Remove transitive dependency.

---

### Q6. Which normal forms are enough for freshers?

**Answer:** 1NF, 2NF, and 3NF.

---

# ⭐ Must Remember (30-Second Revision)

| Normal Form | Easy Meaning                                          |
| ----------- | ----------------------------------------------------- |
| **1NF**     | One value per cell                                    |
| **2NF**     | Every non-key column depends on the whole Primary Key |
| **3NF**     | Non-key columns depend only on the Primary Key        |

---

# 🔥 Most Asked Cross Questions

## Primary Key vs Foreign Key

| Primary Key               | Foreign Key                               |
| ------------------------- | ----------------------------------------- |
| Uniquely identifies a row | References a Primary Key in another table |
| Unique                    | Can have duplicate values                 |
| Cannot be NULL            | May be NULL                               |
| Parent table              | Child table                               |

---

## Normalization vs Denormalization

| Normalization          | Denormalization                       |
| ---------------------- | ------------------------------------- |
| Reduces duplicate data | Intentionally adds some duplication   |
| More tables            | Fewer tables                          |
| Better data integrity  | Better read performance in some cases |
| More JOINs             | Fewer JOINs                           |

For a fresher interview, it's enough to know that **normalization focuses on reducing redundancy**, while **denormalization is sometimes used to improve performance**.

---
