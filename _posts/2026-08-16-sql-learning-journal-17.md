---
title: "SQL Learning Journal #17 – INNER (SELF) JOIN"
date: 2026-08-16
permalink: /posts/sql-learning-journal-17/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 1. INNER (SELF) JOIN

There is no special `SELF JOIN` command in SQL. A self join is created by using a regular `INNER JOIN` to join a table to itself.

By using different aliases for the same table, we can compare or connect information from different rows within that table.

### Table_1

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 3 | keyboard | 10 |
| 4 | coffee | 15 |
| 5 | tea | 15 |
| 6 | milk | 15 |

```sql
SELECT
    t1.product AS product1,
    t2.product AS product2
FROM Table_1 AS t1
INNER JOIN Table_1 AS t2
ON t1.category_id = t2.category_id
AND t1.product_id < t2.product_id;
```

The following condition is important:

```sql
AND t1.product_id < t2.product_id
```

It prevents a product from being matched with itself and also prevents the same pair from appearing twice in reverse order.

### Result

| product1 | product2 |
|----------|----------|
| laptop | mouse |
| laptop | keyboard |
| mouse | keyboard |
| coffee | tea |
| coffee | milk |
| tea | milk |

The query therefore finds pairs of different products that belong to the same category.

---

# ✅ What I Learned Today

At first, it was difficult to understand how the same table could be used as two tables in a query. Today I learned that a **SELF JOIN** uses the same table with different aliases, allowing us to compare or connect different rows within that table. I also learned how an additional condition can prevent a row from being matched with itself and avoid duplicate pairs.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_17.pdf)
