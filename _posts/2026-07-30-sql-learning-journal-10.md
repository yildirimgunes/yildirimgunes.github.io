---
title: "SQL Learning Journal #10 – Filtering Grouped Data with HAVING"
date: 2026-07-30
permalink: /posts/sql-learning-journal-10/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

Today I learned how to filter grouped data using the **HAVING** clause. I also learned the difference between the **WHERE** and **HAVING** clauses and when each one should be used.

---

# 💻 SQL Commands Learned Today

## 1. The HAVING Clause

The **HAVING** clause is used to filter grouped data after the **GROUP BY** clause.

```sql
SELECT year, COUNT(name) AS count_name
FROM table_name
GROUP BY year
HAVING COUNT(name) > 20;
```

---

## 2. Difference Between WHERE and HAVING

The **WHERE** clause filters individual rows **before** the data is grouped.

The **HAVING** clause filters grouped results **after** the data has been grouped.

### Example 1 – Using WHERE

Question:

> Who was born in 2002?

This requires filtering individual records.

```sql
SELECT year, name
FROM table_name
WHERE year = 2002;
```

---

### Example 2 – Using HAVING

Question:

> In which years was the average age greater than 25?

This requires filtering grouped data.

```sql
SELECT year
FROM table_name
GROUP BY year
HAVING AVG(age) > 25;
```

---

# ✅ What I Learned Today

Today I learned the difference between the **WHERE** and **HAVING** clauses. Although they seem similar, they are used for different purposes. **WHERE** filters individual records before grouping, whereas **HAVING** filters grouped results after the **GROUP BY** clause has been applied.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_10.pdf)
