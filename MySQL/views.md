Perfect. We'll now cover **only the remaining important fresher topics**.

---

# Topic 17: Views ⭐⭐⭐⭐ (Basic Fresher Level)

> **Interview Reality:**
> Interviewers usually ask:
>
> * What is a View?
> * Why do we use it?
> * Is data stored in a View?

---

# 1. What is a View?

## Definition (Interview Answer)

A **View** is a **virtual table** created from one or more existing tables using a SQL query.

### Short Interview Answer

> "A View is a virtual table that stores a SQL query, not the actual data."

---

# 2. Why do We Use Views?

Suppose the **employees** table contains:

| id | name    | salary | password |
| -- | ------- | ------ | -------- |
| 1  | Rahul   | 40000  | abc123   |
| 2  | Sandhya | 50000  | xyz789   |

A normal employee should not see the **password** column.

Create a view:

```sql
CREATE VIEW employee_view AS
SELECT id, name, salary
FROM employees;
```

Now,

```sql
SELECT * FROM employee_view;
```

Output:

| id | name    | salary |
| -- | ------- | ------ |
| 1  | Rahul   | 40000  |
| 2  | Sandhya | 50000  |

Only required columns are visible.

---

# 3. Syntax

## Create View

```sql
CREATE VIEW employee_view AS
SELECT id, name
FROM employees;
```

---

## View Data

```sql
SELECT *
FROM employee_view;
```

---

## Delete View

```sql
DROP VIEW employee_view;
```

---

# 4. Does a View Store Data?

**No.**

It stores only the SQL query.

Whenever you query the view, MySQL fetches fresh data from the original table.

---

# 5. Real-Life Example

Suppose your company has:

**Employee Table**

* Name
* Salary
* Password
* Bank Account

The HR department needs all columns.

The Reception department only needs:

* Name
* Department

Create a View to hide sensitive information.

---

# 6. Advantages

* Hides sensitive columns
* Simplifies complex queries
* Improves security
* Reuse the same query

---

# 7. Disadvantages

* Doesn't improve performance by itself
* Depends on the original table
* Some views are not updatable

---

# 8. Common Interview Questions

### Q1. What is a View?

A virtual table.

---

### Q2. Does a View store data?

No.

---

### Q3. Can we query a View?

Yes.

```sql
SELECT * FROM employee_view;
```

---

### Q4. Can we delete a View?

Yes.

```sql
DROP VIEW employee_view;
```

---

### Q5. Why do we use Views?

Security and query simplification.

---

# 📌 Interview Cheat Sheet

### Q1. What is a View?

**Answer:** A virtual table.

---

### Q2. Does it store actual data?

**Answer:** No.

---

### Q3. Which command creates a View?

**Answer:** `CREATE VIEW`.

---

### Q4. Which command removes a View?

**Answer:** `DROP VIEW`.

---

### Q5. Why are Views used?

**Answer:** To simplify queries and restrict access to sensitive data.

---

# ⭐ Must Remember (30-Second Revision)

| View          | Description   |
| ------------- | ------------- |
| Type          | Virtual Table |
| Stores Data?  | ❌ No          |
| Stores Query? | ✅ Yes         |
| Created By    | `CREATE VIEW` |
| Deleted By    | `DROP VIEW`   |

---

 one of the most frequently asked theory questions in Python/Django backend interviews.
