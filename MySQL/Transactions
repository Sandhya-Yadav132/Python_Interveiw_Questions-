# Topic 18: Transactions (COMMIT, ROLLBACK, SAVEPOINT) ⭐⭐⭐⭐⭐ (Must Know for Freshers)

> **Interview Reality:**
>
> Almost every fresher interview has one of these questions:
>
> * What is a transaction?
> * What is COMMIT?
> * What is ROLLBACK?
> * What is SAVEPOINT?

---

# 1. What is a Transaction?

## Definition (Interview Answer)

A **Transaction** is a group of one or more SQL statements that are executed as a **single unit of work**.

### Short Interview Answer

> "A transaction is a sequence of SQL operations that either complete successfully together or fail together."

---

# 2. Why Do We Use Transactions?

Imagine you transfer **₹1000** from Rahul's account to Sandhya's account.

Two operations happen:

1. Deduct ₹1000 from Rahul.
2. Add ₹1000 to Sandhya.

If the first operation succeeds but the second fails, money is lost.

A transaction ensures **both operations succeed or neither is applied**.

---

# 3. Example Table

## accounts

| id | name    | balance |
| -- | ------- | ------- |
| 1  | Rahul   | 5000    |
| 2  | Sandhya | 3000    |

Transfer ₹1000 from Rahul to Sandhya.

---

# 4. START TRANSACTION

```sql
START TRANSACTION;
```

This tells MySQL that a new transaction has started.

---

# 5. COMMIT ⭐⭐⭐⭐⭐

## Definition

`COMMIT` permanently saves all changes made during the transaction.

### Example

```sql
START TRANSACTION;

UPDATE accounts
SET balance = balance - 1000
WHERE id = 1;

UPDATE accounts
SET balance = balance + 1000
WHERE id = 2;

COMMIT;
```

Result:

| Rahul   | 4000 |
| ------- | ---- |
| Sandhya | 4000 |

The changes are now permanent.

---

# 6. ROLLBACK ⭐⭐⭐⭐⭐

## Definition

`ROLLBACK` cancels all changes made during the current transaction and restores the previous state.

### Example

```sql
START TRANSACTION;

UPDATE accounts
SET balance = balance - 1000
WHERE id = 1;

ROLLBACK;
```

Result:

| Rahul | 5000 |

The deduction is undone.

---

# 7. SAVEPOINT ⭐⭐⭐⭐

## Definition

A `SAVEPOINT` creates a checkpoint inside a transaction.

You can roll back only to that point instead of canceling the entire transaction.

### Example

```sql
START TRANSACTION;

UPDATE accounts
SET balance = balance - 1000
WHERE id = 1;

SAVEPOINT sp1;

UPDATE accounts
SET balance = balance + 1000
WHERE id = 2;

ROLLBACK TO sp1;

COMMIT;
```

Meaning:

* First update remains.
* Second update is undone.
* Then the remaining changes are committed.

---

# 8. Real-Life Example

### Online Shopping

You place an order.

Steps:

1. Reduce product stock.
2. Create order.
3. Process payment.

If payment fails:

* Restore stock.
* Cancel order.

This is handled using transactions.

---

# 9. Common Interview Questions

### Q1. What is a transaction?

A group of SQL statements executed as one unit.

---

### Q2. What does COMMIT do?

Permanently saves changes.

---

### Q3. What does ROLLBACK do?

Undoes changes made in the current transaction.

---

### Q4. What is SAVEPOINT?

A checkpoint inside a transaction.

---

### Q5. Can we roll back after COMMIT?

**No.**

Once committed, the changes are permanent.

---

### Q6. Why are transactions important?

To keep data consistent and prevent partial updates.

---

# 10. Common Mistakes

❌ "COMMIT can be undone using ROLLBACK."

Wrong.

Once `COMMIT` is executed, `ROLLBACK` cannot undo those changes.

---

❌ "ROLLBACK only undoes the last query."

Wrong.

It undoes all uncommitted changes, or changes after a specified `SAVEPOINT`.

---

# 11. Best Interview Answer

> "A transaction is a group of SQL operations executed as a single unit. COMMIT permanently saves the changes, ROLLBACK cancels uncommitted changes, and SAVEPOINT creates checkpoints that allow partial rollback within a transaction."

---

# 📌 Interview Cheat Sheet

### Q1. What is a transaction?

**Answer:** A group of SQL statements executed as one unit.

---

### Q2. What does COMMIT do?

**Answer:** Permanently saves changes.

---

### Q3. What does ROLLBACK do?

**Answer:** Cancels uncommitted changes.

---

### Q4. What is SAVEPOINT?

**Answer:** A checkpoint inside a transaction.

---

### Q5. Can ROLLBACK undo a committed transaction?

**Answer:** No.

---

# ⭐ Must Remember (30-Second Revision)

| Command             | Purpose                                   |
| ------------------- | ----------------------------------------- |
| `START TRANSACTION` | Begins a transaction                      |
| `COMMIT`            | Saves changes permanently                 |
| `ROLLBACK`          | Cancels uncommitted changes               |
| `SAVEPOINT`         | Creates a checkpoint for partial rollback |

---

# 🔥 Most Asked Cross Question

## COMMIT vs ROLLBACK

| COMMIT                        | ROLLBACK                    |
| ----------------------------- | --------------------------- |
| Saves changes permanently     | Undoes uncommitted changes  |
| Cannot be undone              | Restores the previous state |
| Used when everything succeeds | Used when an error occurs   |

---
s one of the **top 10 MySQL interview questions** for freshers and is often asked immediately after transactions.
