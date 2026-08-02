---
title: "SQL Learning Journal #13 – INNER JOIN"
date: 2026-08-02
permalink: /posts/sql-learning-journal-13/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

Today I learned how to combine related data from two tables using the **INNER JOIN** clause. An INNER JOIN returns only the rows that have matching values in both tables.

---

# 💻 SQL Commands Learned Today

## 1. INNER JOIN with ON

The **INNER JOIN** clause combines two tables by matching values in a specified column.

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
SELECT Table_1.name,
       Table_1.year,
       Table_1.age,
       Table_2.city
FROM Table_1
INNER JOIN Table_2
ON Table_1.name = Table_2.name;
```

### Result

| name | year | age | city |
|------|-----:|----:|------|
| John | 1999 | 26 | Madrid |
| Kristin | 1996 | 29 | Köln |

---

## 2. INNER JOIN with USING

The **USING** clause can be used instead of **ON** when both tables contain a column with the same name.

```sql
SELECT Table_1.name,
       Table_1.year,
       Table_1.age,
       Table_2.city
FROM Table_1
INNER JOIN Table_2
USING (name);
```

### Result

| name | year | age | city |
|------|-----:|----:|------|
| John | 1999 | 26 | Madrid |
| Kristin | 1996 | 29 | Köln |

---

## Notes

- **ON** is used to specify the matching condition between two tables.
- **USING** is a shorter alternative when both tables have a column with the same name.
- It is good practice to use the **table_name.column_name** format when selecting columns, especially if multiple tables contain columns with the same name.

---

# ✅ What I Learned Today

Today I learned how to combine data from two related tables using the **INNER JOIN** clause. I practiced joining tables with both the **ON** and **USING** clauses and learned that an INNER JOIN returns only the rows with matching values in both tables.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_13.pdf)
