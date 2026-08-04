---
title: "SQL Learning Journal #14 – Multiple INNER JOINs"
date: 2026-08-03
permalink: /posts/sql-learning-journal-14/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

Today I learned how to combine information from more than two tables using multiple **INNER JOIN** clauses. I also learned how to use additional matching conditions with the **AND** operator in the **ON** clause.

---

# 💻 SQL Commands Learned Today

## 1. Joining Multiple Tables

Multiple **INNER JOIN** clauses can be used to combine data from several related tables.

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

### Table_3

| city | population |
|------|-----------:|
| Madrid | 3400k |
| Köln | 1100k |
| Istanbul | 16k |

```sql
SELECT t1.name,
       t1.year,
       t2.city,
       t3.population
FROM Table_1 AS t1
INNER JOIN Table_2 AS t2
ON t1.name = t2.name
INNER JOIN Table_3 AS t3
ON t2.city = t3.city;
```

The same query can also be written using the **USING** clause.

```sql
SELECT t1.name,
       t1.year,
       t2.city,
       t3.population AS city_population
FROM Table_1 AS t1
INNER JOIN Table_2 AS t2
USING (name)
INNER JOIN Table_3 AS t3
USING (city);
```

### Result

| name | year | city | city_population |
|------|-----:|------|----------------:|
| John | 1999 | Madrid | 3400k |
| Kristin | 1996 | Köln | 1100k |

---

## 2. Using AND in the ON Clause

Additional matching conditions can be added by using the **AND** operator inside the **ON** clause.

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
| Kristin | 2005 | Köln |

```sql
SELECT *
FROM Table_1 AS t1
INNER JOIN Table_2 AS t2
ON t1.name = t2.name
AND t1.year = t2.year;
```

### Result

| name | year | city |
|------|-----:|------|
| John | 1999 | Madrid |

---

# ✅ What I Learned Today

Today I learned how to join more than two tables by using multiple **INNER JOIN** clauses. I also practiced adding extra matching conditions with the **AND** operator inside the **ON** clause. These techniques make SQL queries more powerful when working with relational databases.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_14.pdf)
