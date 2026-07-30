# Topic 9: WHERE Clause & Operators ⭐⭐⭐⭐⭐ (Extremely Important)

> **Interview Reality:**
> If you know only `SELECT * FROM table`, that's not enough. Almost every interviewer asks questions using the **WHERE** clause.

---

# 1. What is the WHERE Clause?

## Definition (Interview Answer)

The **WHERE** clause is used to **filter records** based on a specified condition.

### Short Interview Answer

> "The WHERE clause is used to retrieve, update, or delete only those records that satisfy a given condition."

---

# 2. Why do We Use WHERE?

Suppose your `students` table has 10,000 records.

If you want only the student whose `id = 5`, you don't want all 10,000 records.

The `WHERE` clause filters the required data.

---

# 3. Real-Life Example

Imagine a school has **5,000 students**.

The principal asks:

> "Show me only students from Bhopal."

Instead of checking all records manually, we use:

```sql
SELECT * FROM students
WHERE city='Bhopal';
```

---

# 4. Sample Table

## students

| id | name    | age | city   | marks |
| -- | ------- | --- | ------ | ----- |
| 1  | Rahul   | 21  | Delhi  | 85    |
| 2  | Sandhya | 22  | Bhopal | 92    |
| 3  | Aman    | 20  | Indore | 70    |
| 4  | Priya   | 23  | Delhi  | 95    |
| 5  | Rohit   | 21  | Bhopal | 65    |

We'll use this table throughout.

---

# 5. Syntax

```sql
SELECT column_name
FROM table_name
WHERE condition;
```

---

# 6. Comparison Operators ⭐⭐⭐

## (=) Equal To

```sql
SELECT *
FROM students
WHERE city='Delhi';
```

Output:

| Rahul |
| Priya |

---

## (>) Greater Than

```sql
SELECT *
FROM students
WHERE marks > 80;
```

Output:

Rahul

Sandhya

Priya

---

## (<) Less Than

```sql
SELECT *
FROM students
WHERE age < 22;
```

Output:

Rahul

Aman

Rohit

---

## (>=)

```sql
SELECT *
FROM students
WHERE marks >=90;
```

Output:

Sandhya

Priya

---

## (<=)

```sql
SELECT *
FROM students
WHERE age<=21;
```

---

## (!=) or (<>)

Not Equal

```sql
SELECT *
FROM students
WHERE city!='Delhi';
```

or

```sql
SELECT *
FROM students
WHERE city<>'Delhi';
```

Output:

Sandhya

Aman

Rohit

---

# 7. Logical Operators ⭐⭐⭐⭐⭐

## AND

Both conditions must be true.

```sql
SELECT *
FROM students
WHERE city='Delhi'
AND marks>90;
```

Output:

Priya

---

## OR

At least one condition must be true.

```sql
SELECT *
FROM students
WHERE city='Delhi'
OR city='Bhopal';
```

Output:

Rahul

Sandhya

Priya

Rohit

---

## NOT

Opposite condition.

```sql
SELECT *
FROM students
WHERE NOT city='Delhi';
```

Output:

Sandhya

Aman

Rohit

---

# 8. BETWEEN ⭐⭐⭐

Used to select values within a range.

### Syntax

```sql
SELECT *
FROM students
WHERE marks
BETWEEN 70 AND 90;
```

Output:

Rahul

Aman

---

# 9. IN ⭐⭐⭐

Checks multiple values.

Instead of

```sql
WHERE city='Delhi'
OR city='Bhopal'
```

Use

```sql
SELECT *
FROM students
WHERE city
IN('Delhi','Bhopal');
```

---

# 10. NOT IN

```sql
SELECT *
FROM students
WHERE city
NOT IN('Delhi','Bhopal');
```

Output:

Aman

---

# 11. LIKE ⭐⭐⭐⭐⭐

Used for pattern matching.

## Starts With

```sql
SELECT *
FROM students
WHERE name
LIKE 'R%';
```

Output

Rahul

Rohit

---

## Ends With

```sql
SELECT *
FROM students
WHERE name
LIKE '%a';
```

Output

Priya

---

## Contains

```sql
SELECT *
FROM students
WHERE name
LIKE '%an%';
```

Output

Sandhya

---

### Wildcards

| Wildcard | Meaning                 |
| -------- | ----------------------- |
| `%`      | Zero or more characters |
| `_`      | Exactly one character   |

Example:

```sql
LIKE '_a%'
```

Matches:

Rahul

Sandhya

---

# 12. IS NULL ⭐⭐⭐

Find NULL values.

```sql
SELECT *
FROM students
WHERE city
IS NULL;
```

---

# 13. IS NOT NULL

```sql
SELECT *
FROM students
WHERE city
IS NOT NULL;
```

---

# 14. Order of Execution

Example

```sql
SELECT *
FROM students
WHERE marks>80
AND city='Delhi';
```

First

Find Delhi students

Then

Check marks >80

Return result

---

# 15. Common Interview Questions

### Q1. What is WHERE?

Used to filter records.

---

### Q2. Which clause filters data?

WHERE

---

### Q3. Difference between WHERE and HAVING?

WHERE filters rows before grouping.

HAVING filters groups after grouping.

(We'll study HAVING later.)

---

### Q4. Which operator checks multiple values?

IN

---

### Q5. Which operator checks a range?

BETWEEN

---

### Q6. Which operator searches patterns?

LIKE

---

### Q7. Which wildcard represents multiple characters?

%

---

### Q8. Which wildcard represents exactly one character?

_

---

### Q9. Can we use WHERE with UPDATE?

Yes.

```sql
UPDATE students
SET age=22
WHERE id=1;
```

---

### Q10. Can we use WHERE with DELETE?

Yes.

```sql
DELETE FROM students
WHERE id=1;
```

---

# 16. Common Mistakes

❌

```sql
WHERE city=NULL
```

Wrong

✔ Correct

```sql
WHERE city IS NULL;
```

---

❌

Using LIKE without %

Wrong

---

✔

```sql
LIKE 'R%'
```

---

❌

Using = for multiple values

Wrong

```sql
city='Delhi','Bhopal'
```

---

✔

Use

```sql
IN('Delhi','Bhopal')
```

---

# 17. Best Interview Answer

> "The WHERE clause is used to filter records based on a specified condition. It can be used with SELECT, UPDATE, and DELETE statements. Common operators used with WHERE include comparison operators (=, >, <), logical operators (AND, OR, NOT), BETWEEN, IN, LIKE, and IS NULL."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What is WHERE?

**Answer:** Used to filter records.

---

### Q2. Which SQL statements commonly use WHERE?

**Answer:** SELECT, UPDATE, DELETE.

---

### Q3. Which operator checks a range?

**Answer:** BETWEEN.

---

### Q4. Which operator checks multiple values?

**Answer:** IN.

---

### Q5. Which operator performs pattern matching?

**Answer:** LIKE.

---

### Q6. Which wildcard matches multiple characters?

**Answer:** `%`

---

### Q7. Which wildcard matches exactly one character?

**Answer:** `_`

---

### Q8. How do you check for NULL values?

**Answer:** `IS NULL`

---

### Q9. How do you check for non-NULL values?

**Answer:** `IS NOT NULL`

---

### Q10. Which logical operators are commonly used?

**Answer:** AND, OR, NOT.

---

# ⭐ Must Remember (30-Second Revision)

| Operator      | Purpose                        |
| ------------- | ------------------------------ |
| `=`           | Equal                          |
| `>`           | Greater than                   |
| `<`           | Less than                      |
| `>=`          | Greater than or equal          |
| `<=`          | Less than or equal             |
| `!=` / `<>`   | Not equal                      |
| `AND`         | All conditions must be true    |
| `OR`          | Any one condition must be true |
| `NOT`         | Opposite condition             |
| `BETWEEN`     | Range                          |
| `IN`          | Multiple values                |
| `LIKE`        | Pattern matching               |
| `IS NULL`     | Find NULL values               |
| `IS NOT NULL` | Find non-NULL values           |

---




# Topic 10: ORDER BY, LIMIT & OFFSET ⭐⭐⭐⭐⭐ (Very Important)

These are used in almost every real project and are frequently asked in interviews.

---

# 1. ORDER BY

## Definition (Interview Answer)

The **ORDER BY** clause is used to **sort the result** in ascending or descending order.

### Short Interview Answer

> "ORDER BY is used to sort the retrieved records in ascending (ASC) or descending (DESC) order."

---

# 2. Why do We Use ORDER BY?

Suppose an interviewer asks:

> Show the students with the highest marks first.

Without sorting, the records may appear in random/default order.

ORDER BY solves this.

---

# 3. Syntax

```sql
SELECT column_name
FROM table_name
ORDER BY column_name ASC;
```

OR

```sql
SELECT column_name
FROM table_name
ORDER BY column_name DESC;
```

---

# 4. Sample Table

| id | name    | age | marks |
| -- | ------- | --- | ----- |
| 1  | Rahul   | 21  | 85    |
| 2  | Sandhya | 22  | 92    |
| 3  | Aman    | 20  | 70    |
| 4  | Priya   | 23  | 95    |
| 5  | Rohit   | 21  | 65    |

---

## ASC (Ascending)

Lowest to Highest

```sql
SELECT *
FROM students
ORDER BY marks ASC;
```

### Output

| name    | marks |
| ------- | ----- |
| Rohit   | 65    |
| Aman    | 70    |
| Rahul   | 85    |
| Sandhya | 92    |
| Priya   | 95    |

---

## DESC (Descending)

Highest to Lowest

```sql
SELECT *
FROM students
ORDER BY marks DESC;
```

### Output

| name    | marks |
| ------- | ----- |
| Priya   | 95    |
| Sandhya | 92    |
| Rahul   | 85    |
| Aman    | 70    |
| Rohit   | 65    |

---

## Multiple Columns

```sql
SELECT *
FROM students
ORDER BY age ASC, marks DESC;
```

Meaning:

* First sort by **age**
* If age is the same, sort by **marks**

---

# 5. LIMIT

## Definition (Interview Answer)

LIMIT is used to **restrict the number of rows returned**.

### Short Interview Answer

> "LIMIT is used to return only a specified number of records."

---

# 6. Why do We Use LIMIT?

Suppose your table has **1 lakh records**.

You want only the first **10 records**.

Use LIMIT.

---

# 7. Syntax

```sql
SELECT *
FROM students
LIMIT 3;
```

### Output

First 3 rows.

---

## Highest Marks

```sql
SELECT *
FROM students
ORDER BY marks DESC
LIMIT 1;
```

### Output

Priya

---

## Top 3 Students

```sql
SELECT *
FROM students
ORDER BY marks DESC
LIMIT 3;
```

Output:

* Priya
* Sandhya
* Rahul

---

# 8. OFFSET

## Definition (Interview Answer)

OFFSET is used to **skip a specified number of rows before returning results**.

### Short Interview Answer

> "OFFSET skips a specified number of records before fetching the remaining rows."

---

# 9. Why do We Use OFFSET?

Used for **pagination**.

Example:

Website shows

* Page 1 → 10 products
* Page 2 → Next 10 products
* Page 3 → Next 10 products

OFFSET makes this possible.

---

# 10. Syntax

```sql
SELECT *
FROM students
LIMIT 2 OFFSET 2;
```

Meaning:

Skip first **2** rows

Return next **2** rows.

---

## Another Syntax (MySQL)

```sql
SELECT *
FROM students
LIMIT 2,2;
```

Meaning:

Skip **2**

Return next **2**

---

# 11. Pagination Example

### Page 1

```sql
SELECT *
FROM students
LIMIT 10 OFFSET 0;
```

---

### Page 2

```sql
SELECT *
FROM students
LIMIT 10 OFFSET 10;
```

---

### Page 3

```sql
SELECT *
FROM students
LIMIT 10 OFFSET 20;
```

---

# 12. Real Project Example

Suppose your e-commerce website has **5,000 products**.

Instead of loading all 5,000 products:

Page 1

```sql
LIMIT 20 OFFSET 0
```

Page 2

```sql
LIMIT 20 OFFSET 20
```

Page 3

```sql
LIMIT 20 OFFSET 40
```

This improves performance and user experience.

---

# 13. Common Interview Questions

### Q1. What is ORDER BY?

Used to sort records.

---

### Q2. What is the default sorting order?

**ASC (Ascending)**

---

### Q3. Which keyword is used for descending order?

DESC

---

### Q4. What is LIMIT?

Used to return a fixed number of rows.

---

### Q5. Why do we use LIMIT?

To fetch only the required number of records.

---

### Q6. What is OFFSET?

Used to skip records.

---

### Q7. Where is OFFSET mostly used?

Pagination.

---

### Q8. How do you find the highest salary?

```sql
SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 1;
```

---

### Q9. How do you find the lowest salary?

```sql
SELECT *
FROM employees
ORDER BY salary ASC
LIMIT 1;
```

---

### Q10. Can ORDER BY be used with LIMIT?

Yes.

It is very common.

---

# 14. Common Mistakes

❌

```sql
ORDER BY DESC marks
```

Wrong

✔ Correct

```sql
ORDER BY marks DESC;
```

---

❌

```sql
LIMIT OFFSET 10
```

Wrong

✔ Correct

```sql
LIMIT 10 OFFSET 20;
```

---

❌

Thinking LIMIT sorts data.

Wrong.

LIMIT only limits the number of rows.

Sorting is done by ORDER BY.

---

# 15. Best Interview Answer

> "ORDER BY is used to sort records in ascending or descending order. LIMIT restricts the number of rows returned, while OFFSET skips a specified number of rows before fetching results. These clauses are commonly used together for sorting, retrieving top records, and implementing pagination."

---

# 📌 Interview Cheat Sheet (Short Q&A)

### Q1. What is ORDER BY?

**Answer:** Used to sort records.

---

### Q2. What is the default sorting order?

**Answer:** ASC.

---

### Q3. Which keyword sorts in descending order?

**Answer:** DESC.

---

### Q4. What is LIMIT?

**Answer:** Returns a specified number of rows.

---

### Q5. What is OFFSET?

**Answer:** Skips a specified number of rows.

---

### Q6. Which clause is used for pagination?

**Answer:** LIMIT + OFFSET.

---

### Q7. Which clause is used to find the highest salary?

**Answer:** ORDER BY salary DESC LIMIT 1.

---

### Q8. Which clause is used to find the lowest salary?

**Answer:** ORDER BY salary ASC LIMIT 1.

---

### Q9. Can ORDER BY be used with LIMIT?

**Answer:** Yes.

---

### Q10. Does LIMIT sort records?

**Answer:** No. ORDER BY sorts; LIMIT only restricts the number of returned rows.

---

# ⭐ Must Remember (30-Second Revision)

| Clause           | Purpose             |
| ---------------- | ------------------- |
| `ORDER BY`       | Sort records        |
| `ASC`            | Ascending (Default) |
| `DESC`           | Descending          |
| `LIMIT`          | Return limited rows |
| `OFFSET`         | Skip rows           |
| `LIMIT + OFFSET` | Pagination          |

---

# 🔥 Cross Questions (Frequently Asked)

### Q1. ORDER BY ASC vs DESC

| ASC                                                  | DESC             |
| ---------------------------------------------------- | ---------------- |
| Lowest → Highest                                     | Highest → Lowest |
| A → Z                                                | Z → A            |
| Oldest → Newest (for numbers/dates where applicable) | Newest → Oldest  |

---

### Q2. LIMIT vs OFFSET

| LIMIT                                 | OFFSET                                          |
| ------------------------------------- | ----------------------------------------------- |
| Restricts the number of rows returned | Skips rows before returning results             |
| `LIMIT 5` → returns first 5 rows      | `OFFSET 5` → skips first 5 rows                 |
| Often used with ORDER BY              | Usually used together with LIMIT for pagination |

---


