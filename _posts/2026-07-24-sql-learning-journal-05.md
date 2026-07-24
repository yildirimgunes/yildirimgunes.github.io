---
title: "SQL Learning Journal #5 – Combining Filtering, Counting and Missing Values"
date: 2026-07-24
permalink: /posts/sql-learning-journal-05/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

In today's lesson, I learned how to combine SQL filtering and counting functions in a single query. I also studied how SQL handles missing values (NULL values) and the differences between various COUNT functions.

---

# 💻 SQL Commands Learned Today

## 1. Combining Multiple Conditions

Example:

```sql
SELECT COUNT(DISTINCT people_name) AS unique_people_name
FROM people_name_table
WHERE age BETWEEN 10 AND 19
AND language = 'French';
```

This query counts the number of unique people who:

- are between 10 and 19 years old, and
- speak French.

---

## 2. Counting Missing and Non-Missing Values

### Count all rows

```sql
COUNT(*)
```

Counts all rows in a table, including rows containing NULL values.

---

### Count only non-NULL values

```sql
COUNT(field_name)
```

Counts only the non-NULL values in the specified column.

---

### Count unique non-NULL values

```sql
COUNT(DISTINCT field_name)
```

Counts only the unique non-NULL values in the specified column.

---

## 3. Using IS NULL and IS NOT NULL

### Count missing values

```sql
SELECT COUNT(*) AS count_no_age
FROM table_name
WHERE field_name_age IS NULL;
```

---

### Count non-missing values

```sql
SELECT COUNT(field_name_age) AS count_age
FROM table_name
WHERE field_name_age IS NOT NULL;
```

---

### Equivalent Queries

```sql
SELECT COUNT(age) AS count_age
FROM films;
```

and

```sql
SELECT COUNT(age) AS count_age
FROM films
WHERE age IS NOT NULL;
```

Both queries return the same result because the `COUNT(column_name)` function automatically ignores NULL values.

---
# ✅ What I Learned Today

Today I learned how to combine filtering conditions with counting functions in SQL. I also understood how SQL handles NULL values and when to use `COUNT(*)`, 
`COUNT(column_name)`, `COUNT(DISTINCT column_name)`, `IS NULL`, and `IS NOT NULL`. One important lesson I learned today is that combining multiple SQL commands makes queries more powerful, but it is also more challenging to 
remember the correct syntax. Regular practice is essential to become confident in writing SQL queries.
