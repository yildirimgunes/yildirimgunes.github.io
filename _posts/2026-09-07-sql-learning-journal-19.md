---
title: "SQL Learning Journal #19 – SUBQUERYING"
date: 2026-09-07
permalink: /posts/sql-learning-journal-19/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

We can use subqueries to connect and filter different information from tables.

# 1. SEMI JOIN (IN)

The code below can be used to filter information from `students_table`.

~~~sql
SELECT birth_date
FROM students_table
WHERE birth_date > 1980;
~~~

We can use the query above as a subquery to filter and select information from `information_table`.

### information_table

| name | surname | hometown |
|------|---------|----------|
| John | Tone | Boston |
| Gunar | Blair | New_Jersey |
| Alex | Donna | New_York |
| Jonnes | Knutt | Califormia |

### students_table

| name | surname | birth_date |
|------|---------|------------|
| John | Tone | 1982 |
| Gunar | Blair | 1989 |
| Alex | Donna | 1975 |
| Jonnes | Knutt | 1984 |

~~~sql
SELECT name, surname, hometown
FROM information_table
WHERE birth_date IN
      (
          SELECT birth_date
          FROM students_table
          WHERE birth_date > 1980
      );
~~~

### Result

| name | surname | hometown |
|------|---------|----------|
| John | Tone | Boston |
| Gunar | Blair | New_Jersey |
| Jonnes | Knutt | Califormia |

The subquery first selects the birth dates greater than 1980 from `students_table`. The outer query then uses these values to filter the records in `information_table`.

---

# 2. ANTI JOIN (NOT IN)

This function works similarly to a semi join. However, an anti join selects information that is not included in the second table.

~~~sql
SELECT name, surname, hometown
FROM information_table
WHERE birth_date NOT IN
      (
          SELECT birth_date
          FROM students_table
          WHERE birth_date > 1980
      );
~~~

### Result

| name | surname | hometown |
|------|---------|----------|
| Alex | Donna | New_York |

The subquery identifies the birth dates greater than 1980, and `NOT IN` selects the records whose birth dates are not included in those results.

---

# 📌 Summary

| Operation | Purpose |
|-----------|---------|
| `IN` | Selects rows whose values are included in the result of a subquery |
| `NOT IN` | Selects rows whose values are not included in the result of a subquery |

---

# ✅ What I Learned Today

Today I learned how subqueries can be used for more detailed filtering and for selecting information from different tables.

I learned that `IN` can be used to select records based on the results returned by a subquery, while `NOT IN` can be used to select records whose values are not included in the subquery result.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_19.pdf)
