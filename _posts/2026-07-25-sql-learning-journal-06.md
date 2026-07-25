---
title: "SQL Learning Journal #6 – Aggregate Functions to Understand Data"
date: 2026-07-25
permalink: /posts/sql-learning-journal-06/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

In today's lesson, I learned how to use SQL aggregate functions to summarize data. I practiced the **AVG()**, **SUM()**, **MIN()**, **MAX()**, **COUNT()**, and **ROUND()** functions, and I also learned how to combine these functions with filtering conditions.

---

# 💻 SQL Commands Learned Today

## 1. Aggregate Functions

The following aggregate functions are used after the `SELECT` statement:

- `AVG()`
- `SUM()`
- `MIN()`
- `MAX()`
- `COUNT()`

### AVG() and SUM()

These functions can only be used with numerical values.

```sql
SELECT AVG(field_name)
FROM table_name;
```

```sql
SELECT SUM(field_name)
FROM table_name;
```

---

## 2. MIN(), MAX(), and COUNT()

These functions can be used with both numerical and non-numerical values.

For text values:

- `MIN()` returns the first value in alphabetical order.
- `MAX()` returns the last value in alphabetical order.

```sql
SELECT MIN(field_name)
FROM table_name;
```

```sql
SELECT MAX(field_name)
FROM table_name;
```

```sql
SELECT COUNT(field_name)
FROM table_name;
```

---

## 3. Using Aliases

An alias gives a new name to the output column.

```sql
SELECT MAX(field_name) AS nick_name_max
FROM table_name;
```

---

## 4. Combining Filtering with Aggregate Functions

Average value:

```sql
SELECT AVG(year) AS average_year
FROM table_name
WHERE city = 'Istanbul';
```

Sum of values:

```sql
SELECT SUM(year) AS sum_year
FROM table_name
WHERE city = 'Istanbul';
```

---

## 5. Using the ROUND() Function

The `ROUND()` function rounds decimal values.

If the second argument is omitted, SQL uses **0** as the default value.

The following two queries return the same result:

```sql
SELECT ROUND(AVG(money)) AS average_money
FROM films;
```

```sql
SELECT ROUND(AVG(money), 0) AS average_money
FROM films;
```

---

## 6. ROUND() with Positive and Negative Values

A positive second argument rounds digits to the right of the decimal point.

```sql
SELECT ROUND(AVG(money), 2) AS average_money
FROM films;
```

A negative second argument rounds digits to the left of the decimal point.

```sql
SELECT ROUND(AVG(money), -2) AS average_money
FROM films;
```

---
# ✅ What I Learned Today
Today I learned how to summarize data using SQL aggregate functions. I practiced **AVG()**, **SUM()**, **MIN()**, **MAX()**, **COUNT()**, and **ROUND()**, 
and I learned how to combine aggregate functions with filtering conditions. One important lesson I learned today is that writing SQL requires careful attention 
to syntax. Even a small mistake, such as a missing comma or incorrect parentheses, can cause a query to fail.

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_06.pdf)
