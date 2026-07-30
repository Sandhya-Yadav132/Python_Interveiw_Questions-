# Topic 12: GROUP BY ⭐⭐⭐⭐⭐ (One of the Most Important SQL Topics)

> **Interview Reality:**
> `GROUP BY` is one of the most frequently asked SQL topics for freshers. It is almost always combined with **Aggregate Functions** (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`) and **HAVING**.

---

# 1. What is GROUP BY?

## Definition (Interview Answer)

The **GROUP BY** clause is used to **group rows that have the same values in one or more columns**, so that aggregate functions can be applied to each group.

### Short Interview Answer

> "GROUP BY groups rows with the same values into a single group, allowing aggregate functions like COUNT(), SUM(), AVG(), MIN(), and MAX() to calculate results for each group."

---

# 2. Why Do We Use GROUP BY?

Suppose a company has **1,000 employees** working in different departments.

Instead of calculating:

* Total salary of all employees

You want:

* Total salary of **IT**
* Total salary of **HR**
* Total salary of **Sales**

This is where **GROUP BY** is used.

---

# 3. Sample Table

## employees

| id | name    | department | salary |
| -- | ------- | ---------- | ------ |
| 1  | Rahul   | IT         | 40000  |
| 2  | Sandhya | HR         | 50000  |
| 3  | Aman    | IT         | 45000  |
| 4  | Priya   | Sales      | 60000  |
| 5  | Rohit   | HR         | 55000  |

---

# 4. Syntax

```sql
SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name;
```

---

# 5. COUNT() with GROUP BY

### Count Employees in Each Department

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
```

### Output

| department | COUNT(*) |
| ---------- | -------- |
| IT         | 2        |
| HR         | 2        |
| Sales      | 1        |

---

# 6. SUM() with GROUP BY

### Total Salary Department-wise

```sql
SELECT department, SUM(salary)
FROM employees
GROUP BY department;
```

### Output

| department | SUM(salary) |
| ---------- | ----------- |
| IT         | 85000       |
| HR         | 105000      |
| Sales      | 60000       |

---

# 7. AVG() with GROUP BY

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department;
```

### Output

| department | AVG(salary) |
| ---------- | ----------- |
| IT         | 42500       |
| HR         | 52500       |
| Sales      | 60000       |

---

# 8. MAX() with GROUP BY

Highest salary in each department.

```sql
SELECT department, MAX(salary)
FROM employees
GROUP BY department;
```

### Output

| department | MAX(salary) |
| ---------- | ----------- |
| IT         | 45000       |
| HR         | 55000       |
| Sales      | 60000       |

---

# 9. MIN() with GROUP BY

Lowest salary in each department.

```sql
SELECT department, MIN(salary)
FROM employees
GROUP BY department;
```

---

# 10. GROUP BY Multiple Columns

Suppose another column:

| department | city   |
| ---------- | ------ |
| IT         | Delhi  |
| IT         | Bhopal |
| HR         | Delhi  |

```sql
SELECT department, city, COUNT(*)
FROM employees
GROUP BY department, city;
```

Grouping happens based on the combination of **department** and **city**.

---

# 11. WHERE + GROUP BY

Find total salary of employees earning more than 45,000.

```sql
SELECT department, SUM(salary)
FROM employees
WHERE salary > 45000
GROUP BY department;
```

**Execution Order:**

1. WHERE filters rows.
2. GROUP BY creates groups.
3. SUM() calculates the total.

---

# 12. ORDER BY + GROUP BY

Sort departments by total salary.

```sql
SELECT department, SUM(salary) AS total_salary
FROM employees
GROUP BY department
ORDER BY total_salary DESC;
```

### Output

| department | total_salary |
| ---------- | ------------ |
| HR         | 105000       |
| IT         | 85000        |
| Sales      | 60000        |

---

# 13. Real-Life Example

### E-commerce

| Order ID | Category    | Amount |
| -------- | ----------- | ------ |
| 101      | Electronics | 500    |
| 102      | Clothing    | 200    |
| 103      | Electronics | 700    |

Find total sales category-wise.

```sql
SELECT category, SUM(amount)
FROM orders
GROUP BY category;
```

---

# 14. Rules of GROUP BY ⭐⭐⭐⭐⭐

### Rule 1

If you use an aggregate function with a normal column, the normal column should generally be included in the `GROUP BY` clause.

✔ Correct

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
```

---

### Rule 2

You can group by multiple columns.

```sql
GROUP BY department, city;
```

---

### Rule 3

`WHERE` comes **before** `GROUP BY`.

✔ Correct

```sql
SELECT department, COUNT(*)
FROM employees
WHERE salary > 40000
GROUP BY department;
```

---

### Rule 4

`ORDER BY` comes **after** `GROUP BY`.

✔ Correct

```sql
SELECT department, SUM(salary)
FROM employees
GROUP BY department
ORDER BY SUM(salary) DESC;
```

---

# 15. Common Interview Questions

### Q1. What is GROUP BY?

Groups rows having the same values.

---

### Q2. Why do we use GROUP BY?

To perform aggregate calculations for each group.

---

### Q3. Which functions are commonly used with GROUP BY?

* COUNT()
* SUM()
* AVG()
* MIN()
* MAX()

---

### Q4. Can GROUP BY be used without aggregate functions?

**Yes**, but it is uncommon. It returns distinct groups of the grouped columns.

Example:

```sql
SELECT department
FROM employees
GROUP BY department;
```

---

### Q5. Which clause comes first: WHERE or GROUP BY?

**WHERE**.

---

### Q6. Which clause comes after GROUP BY?

**ORDER BY** or **HAVING** (if used).

---

### Q7. Can GROUP BY use multiple columns?

Yes.

---

### Q8. Is GROUP BY used before WHERE?

No.

WHERE comes first.

---

### Q9. What happens if GROUP BY is omitted?

Aggregate functions calculate over the entire result set instead of separate groups.

---

### Q10. Can GROUP BY be combined with ORDER BY?

Yes.

---

# 16. Common Mistakes

❌ Wrong

```sql
SELECT department, salary
FROM employees
GROUP BY department;
```

This is invalid in standard SQL because `salary` is neither grouped nor aggregated. (Some MySQL configurations allow it, but the returned value is not reliable.)

---

✔ Correct

```sql
SELECT department, MAX(salary)
FROM employees
GROUP BY department;
```

---

❌ Wrong Order

```sql
GROUP BY department
WHERE salary > 40000;
```

---

✔ Correct

```sql
WHERE salary > 40000
GROUP BY department;
```

---

# 17. Best Interview Answer

> "GROUP BY is used to group rows with the same values so that aggregate functions can calculate results for each group separately. It is commonly used with COUNT(), SUM(), AVG(), MIN(), and MAX() to generate department-wise, category-wise, or city-wise summaries."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What is GROUP BY?

**Answer:** It groups rows with the same values.

---

### Q2. Why do we use GROUP BY?

**Answer:** To perform aggregate calculations for each group.

---

### Q3. Which functions are commonly used with GROUP BY?

**Answer:** COUNT(), SUM(), AVG(), MIN(), MAX().

---

### Q4. Which clause comes before GROUP BY?

**Answer:** WHERE.

---

### Q5. Which clause comes after GROUP BY?

**Answer:** HAVING or ORDER BY.

---

### Q6. Can GROUP BY use multiple columns?

**Answer:** Yes.

---

### Q7. Is GROUP BY mandatory with aggregate functions?

**Answer:** No. Aggregate functions can be used without GROUP BY when calculating over the entire result set.

---

### Q8. Can ORDER BY be used with GROUP BY?

**Answer:** Yes.

---

### Q9. What does GROUP BY return?

**Answer:** One row for each group.

---

### Q10. Which SQL topic is usually learned after GROUP BY?

**Answer:** HAVING.

---

# ⭐ Must Remember (30-Second Revision)

| Clause     | Purpose                     |
| ---------- | --------------------------- |
| `GROUP BY` | Groups similar rows         |
| `COUNT()`  | Count rows in each group    |
| `SUM()`    | Total of each group         |
| `AVG()`    | Average of each group       |
| `MIN()`    | Minimum value in each group |
| `MAX()`    | Maximum value in each group |

---

# 🔥 Cross Questions (Very Frequently Asked)

## Q1. GROUP BY vs ORDER BY ⭐⭐⭐⭐⭐

| GROUP BY                                     | ORDER BY                                               |
| -------------------------------------------- | ------------------------------------------------------ |
| Creates groups                               | Sorts rows                                             |
| Used with aggregate functions                | Used for sorting results                               |
| Reduces multiple rows into one row per group | Keeps all result rows unless combined with aggregation |

---

## Q2. GROUP BY vs DISTINCT ⭐⭐⭐⭐

| GROUP BY                                 | DISTINCT                                    |
| ---------------------------------------- | ------------------------------------------- |
| Used for grouping and aggregation        | Removes duplicate rows                      |
| Commonly used with COUNT(), SUM(), AVG() | Usually used without aggregate calculations |
| Produces grouped summaries               | Produces unique values                      |

Example:

```sql
SELECT DISTINCT department
FROM employees;
```

```sql
SELECT department
FROM employees
GROUP BY department;
```

Both return unique departments in this case, but `GROUP BY` is intended for grouping and aggregation.

---
 one of the top SQL interview questions for freshers, so we'll cover it in detail next.



# Topic 13: HAVING Clause ⭐⭐⭐⭐⭐ (Very Important)

> **Interview Reality:**
> One of the most common SQL interview questions is:
>
> **"What is the difference between WHERE and HAVING?"**
>
> You should answer this confidently.

---

# 1. What is HAVING?

## Definition (Interview Answer)

The **HAVING** clause is used to **filter groups** created by the `GROUP BY` clause.

Unlike `WHERE`, which filters individual rows, `HAVING` filters grouped results.

### Short Interview Answer

> "HAVING is used to filter grouped data after the GROUP BY clause. It is mainly used with aggregate functions."

---

# 2. Why do We Use HAVING?

Suppose a company has employees in different departments.

You want to display **only those departments whose total salary is greater than 90,000**.

You cannot use `WHERE` because the total salary is calculated **after** grouping.

So we use `HAVING`.

---

# 3. Sample Table

## employees

| id | name    | department | salary |
| -- | ------- | ---------- | ------ |
| 1  | Rahul   | IT         | 40000  |
| 2  | Sandhya | HR         | 50000  |
| 3  | Aman    | IT         | 45000  |
| 4  | Priya   | Sales      | 60000  |
| 5  | Rohit   | HR         | 55000  |

---

# 4. Syntax

```sql
SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

---

# 5. Example 1

### Departments having total salary greater than 90,000

```sql
SELECT department, SUM(salary) AS total_salary
FROM employees
GROUP BY department
HAVING SUM(salary) > 90000;
```

### Output

| department | total_salary |
| ---------- | ------------ |
| HR         | 105000       |

---

# 6. Example 2

### Departments having more than one employee

```sql
SELECT department, COUNT(*) AS total_employees
FROM employees
GROUP BY department
HAVING COUNT(*) > 1;
```

### Output

| department | total_employees |
| ---------- | --------------- |
| IT         | 2               |
| HR         | 2               |

---

# 7. Example 3

### Departments whose average salary is greater than 45,000

```sql
SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 45000;
```

### Output

| department |
| ---------- |
| HR         |
| Sales      |

---

# 8. WHERE + GROUP BY + HAVING

Suppose you want:

* Ignore employees earning less than **45,000**
* Group remaining employees by department
* Show only departments having more than one employee

```sql
SELECT department, COUNT(*)
FROM employees
WHERE salary >= 45000
GROUP BY department
HAVING COUNT(*) > 1;
```

### Execution Order

1. FROM
2. WHERE
3. GROUP BY
4. HAVING
5. SELECT
6. ORDER BY
7. LIMIT

---

# 9. Real-Life Example

### E-commerce

| Category    | Amount |
| ----------- | ------ |
| Electronics | 500    |
| Electronics | 700    |
| Clothing    | 200    |
| Clothing    | 300    |

Find categories where total sales exceed **$800**.

```sql
SELECT category, SUM(amount)
FROM orders
GROUP BY category
HAVING SUM(amount) > 800;
```

---

# 10. Common Interview Questions

### Q1. What is HAVING?

Used to filter grouped data.

---

### Q2. Is HAVING used with GROUP BY?

Yes.

---

### Q3. Can HAVING use aggregate functions?

Yes.

Example:

```sql
HAVING COUNT(*) > 2
```

---

### Q4. Can WHERE use aggregate functions?

Generally **No**.

Aggregate functions are used after grouping, so use `HAVING`.

---

### Q5. Which clause executes first?

`WHERE`

---

### Q6. Which clause filters groups?

`HAVING`

---

### Q7. Which clause filters rows?

`WHERE`

---

### Q8. Can HAVING be used without GROUP BY?

**Yes.**

If there is no `GROUP BY`, the entire result is treated as a single group.

Example:

```sql
SELECT COUNT(*)
FROM employees
HAVING COUNT(*) > 3;
```

---

### Q9. Which clause comes before HAVING?

`GROUP BY`

---

### Q10. Can ORDER BY come after HAVING?

Yes.

---

# 11. Common Mistakes

❌ Wrong

```sql
SELECT department
FROM employees
WHERE COUNT(*) > 1;
```

`COUNT()` cannot be used in `WHERE`.

---

✔ Correct

```sql
SELECT department
FROM employees
GROUP BY department
HAVING COUNT(*) > 1;
```

---

❌ Wrong Order

```sql
HAVING COUNT(*) > 1
GROUP BY department;
```

---

✔ Correct

```sql
GROUP BY department
HAVING COUNT(*) > 1;
```

---

# 12. Best Interview Answer

> "HAVING is used to filter grouped data after the GROUP BY clause. It is commonly used with aggregate functions like COUNT(), SUM(), AVG(), MIN(), and MAX(). Unlike WHERE, which filters individual rows before grouping, HAVING filters groups after grouping."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What is HAVING?

**Answer:** Filters grouped data.

---

### Q2. Which clause is HAVING usually used with?

**Answer:** GROUP BY.

---

### Q3. Which clause filters rows?

**Answer:** WHERE.

---

### Q4. Which clause filters groups?

**Answer:** HAVING.

---

### Q5. Can HAVING use aggregate functions?

**Answer:** Yes.

---

### Q6. Can WHERE use aggregate functions?

**Answer:** Generally no.

---

### Q7. Which clause executes first?

**Answer:** WHERE.

---

### Q8. Which clause comes after GROUP BY?

**Answer:** HAVING.

---

### Q9. Can ORDER BY be used after HAVING?

**Answer:** Yes.

---

### Q10. Can HAVING be used without GROUP BY?

**Answer:** Yes, but it treats the entire result as one group.

---

# ⭐ Must Remember (30-Second Revision)

| WHERE                                    | HAVING                            |
| ---------------------------------------- | --------------------------------- |
| Filters rows                             | Filters groups                    |
| Executes before GROUP BY                 | Executes after GROUP BY           |
| Cannot generally use aggregate functions | Commonly uses aggregate functions |
| Used with SELECT, UPDATE, DELETE         | Mainly used with GROUP BY         |

---

# 🔥 Cross Questions (Most Frequently Asked)

## Q1. WHERE vs HAVING ⭐⭐⭐⭐⭐

| WHERE                                         | HAVING                                    |
| --------------------------------------------- | ----------------------------------------- |
| Filters individual rows                       | Filters grouped results                   |
| Runs before grouping                          | Runs after grouping                       |
| Generally cannot use `COUNT()`, `SUM()`, etc. | Can use `COUNT()`, `SUM()`, `AVG()`, etc. |
| Used before `GROUP BY`                        | Used after `GROUP BY`                     |

### Example

**WHERE**

```sql
SELECT *
FROM employees
WHERE salary > 40000;
```

Filters **rows**.

---

**HAVING**

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 1;
```

Filters **groups**.

---

## Q2. SQL Query Execution Order ⭐⭐⭐⭐

Interviewers sometimes ask:

**What is the logical execution order of a SQL query?**

```text
1. FROM
2. WHERE
3. GROUP BY
4. HAVING
5. SELECT
6. ORDER BY
7. LIMIT
```

Memorize this order—it's a favorite interview question.

---



