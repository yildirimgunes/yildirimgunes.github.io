---
title: "SQL Learning Journal #16 – FULL JOINs, Crossing into CROSS JOIN"
date: 2026-08-09
permalink: /posts/sql-learning-journal-16/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 1. FULL JOIN (FULL OUTER JOIN)

A **FULL JOIN** returns all rows from both tables. When a row has no matching value in the other table, SQL returns `NULL` for the missing values.

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
FULL JOIN Table_2 AS t2
USING (name);
```

### Result

| name | year | age | city |
|------|-----:|----:|------|
| John | 1999 | 26 | Madrid |
| Barbro | 2001 | 24 | NULL |
| Kristin | 1996 | 29 | Köln |
| Kenneth | NULL | NULL | Istanbul |

The unmatched rows from **both tables** are preserved.

---

# 2. CROSS JOIN

A **CROSS JOIN** returns every possible combination of rows from the two tables. It does not require a matching column or an `ON`/`USING` condition.

### Table_1

| name | year |
|------|-----:|
| John | 1999 |
| Barbro | 2001 |
| Kristin | 1996 |

### Table_2

| name | city |
|------|------|
| John | Madrid |
| Kenneth | Istanbul |
| Kristin | Köln |

```sql
SELECT t1.name,
       t2.city
FROM Table_1 AS t1
CROSS JOIN Table_2 AS t2;
```

### Result

| name | city |
|------|------|
| John | Madrid |
| John | Istanbul |
| John | Köln |
| Barbro | Madrid |
| Barbro | Istanbul |
| Barbro | Köln |
| Kristin | Madrid |
| Kristin | Istanbul |
| Kristin | Köln |

With **3 rows** in each table, the CROSS JOIN produces:

**3 × 3 = 9 rows**

---

# 📌 FULL JOIN vs. CROSS JOIN

- **FULL JOIN** combines rows based on a matching condition and preserves unmatched rows from both tables.
- **CROSS JOIN** does not look for matching values. It creates every possible combination of rows from the two tables.

---

# ✅ What I Learned Today

Today I learned how to use **FULL JOIN** to combine two tables while preserving all rows from both tables. I also learned how **CROSS JOIN** creates every possible combination of rows from two tables. These two JOIN types work differently and are useful for different types of data analysis.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_16.pdf)
