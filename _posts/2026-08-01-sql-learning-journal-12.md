---
title: "SQL Learning Journal #12 – Joining Data with UNION"
date: 2026-08-01
permalink: /posts/sql-learning-journal-12/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

Today I started learning how to combine data from multiple tables using the **UNION** operator. Combining datasets is an important technique in SQL because information is often stored in separate tables that need to be merged for analysis.

---

# 💻 SQL Commands Learned Today

## 1. UNION ALL and UNION

If two tables have the same number of columns and compatible data types, they can be combined using the **UNION** operator.

**UNION ALL** keeps every row, including duplicate records.

```sql
SELECT *
FROM table1_name
UNION ALL
SELECT *
FROM table2_name
ORDER BY year DESC;
```

The **UNION** operator removes duplicate rows automatically.

```sql
SELECT *
FROM table1_name
UNION
SELECT *
FROM table2_name
ORDER BY year DESC;
```

---

## 2. Important Notes

- Both tables must contain the same number of columns.
- Corresponding columns must have compatible data types and appear in the same order.
- The column names do not have to be identical.
- The result table always uses the column names from the first `SELECT` statement.

---

# ✅ What I Learned Today

Today I learned how to combine data from multiple tables using the **UNION** operator. I also learned the difference between **UNION ALL**, which keeps duplicate rows, and **UNION**, which automatically removes duplicates. Understanding how to combine datasets is an essential step toward working with larger and more complex databases.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_12.pdf)
