---
title: "SQL Learning Journal #15 – LEFT JOIN and RIGHT JOIN"
date: 2026-08-08
permalink: /posts/sql-learning-journal-15/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

Today I learned how to use **LEFT JOIN** and **RIGHT JOIN** to combine data from two related tables. I also learned how these joins keep unmatched rows from one of the tables and represent missing values as `NULL`.

---

# 💻 SQL Commands Learned Today

## 1. LEFT JOIN (LEFT OUTER JOIN)

A **LEFT JOIN** returns all rows from the left table and the matching rows from the right table. If there is no matching row in the right table, SQL returns `NULL` for the corresponding columns.

### Table_1

| name | year | age |
|------|-----:|----:|
| John | 1999 | 26 |
| Barbro | 2001 | 24 |
| Kristin | 1996 | 29 |

### Table_2

| name | year | city |
|------|-----:|------|
| John | 1999 | Madrid |
| Kenneth | 2007 | Istanbul |
| Kristin | 1996 | Köln |

```sql
SELECT t1.name,
       t1.year,
       t1.age,
       t2.city
FROM Table_1 AS t1
LEFT JOIN Table_2 AS t2
USING (name);
```

### Result

| name | year | age | city |
|------|-----:|----:|------|
| John | 1999 | 26 | Madrid |
| Barbro | 2001 | 24 | NULL |
| Kristin | 1996 | 29 | Köln |

The row for **Barbro** is preserved because it exists in `Table_1`, even though there is no matching `name` in `Table_2`.

---

## 2. RIGHT JOIN (RIGHT OUTER JOIN)

A **RIGHT JOIN** returns all rows from the right table and the matching rows from the left table. If there is no matching row in the left table, SQL returns `NULL` for the corresponding columns.

```sql
SELECT t1.name,
       t1.year,
       t1.age,
       t2.city
FROM Table_1 AS t1
RIGHT JOIN Table_2 AS t2
USING (name);
```

### Result

| name | year | age | city |
|------|-----:|----:|------|
| John | 1999 | 26 | Madrid |
| Kenneth | NULL | NULL | Istanbul |
| Kristin | 1996 | 29 | Köln |

The row for **Kenneth** is preserved because it exists in `Table_2`, even though there is no matching `name` in `Table_1`.

---

# 📌 LEFT JOIN vs. RIGHT JOIN

The main difference is which table's unmatched rows are preserved:

- **LEFT JOIN** → keeps all rows from the **left table**.
- **RIGHT JOIN** → keeps all rows from the **right table**.
- If there is no match, SQL returns `NULL` for the missing values.

---

# ✅ What I Learned Today

Today I learned how to use **LEFT JOIN** and **RIGHT JOIN** to combine related tables. I also learned that these joins can preserve unmatched records and represent missing information with `NULL`. Understanding which table's records should be preserved is important when choosing between different types of joins.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_15.pdf)
