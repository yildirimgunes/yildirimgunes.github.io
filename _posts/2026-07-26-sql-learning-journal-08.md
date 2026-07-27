---
title: "SQL Learning Journal #8 – Sorting Tables with ORDER BY"
date: 2026-07-28
permalink: /posts/sql-learning-journal-08/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

Today I learned how to sort query results using the **ORDER BY** clause. I practiced sorting data in both ascending and descending order, ordering by multiple columns, combining **ORDER BY** with filtering conditions, and limiting the number of returned rows.

---

# 💻 SQL Commands Learned Today

## 1. Sorting Data with ORDER BY

By default, the **ORDER BY** clause sorts numbers from the smallest to the largest and text in alphabetical order (A to Z).

```sql
SELECT name, age
FROM table_name
ORDER BY age;
```

The following query produces the same result and makes the sorting direction explicit.

```sql
SELECT name, age
FROM table_name
ORDER BY age ASC;
```

---

## 2. Sorting in Descending Order

To sort values from the largest to the smallest (or from Z to A), use the **DESC** keyword.

```sql
SELECT name, age
FROM table_name
ORDER BY age DESC;
```

---

## 3. Sorting Text Values

Text values can also be sorted using **ORDER BY**.

If a text field contains numbers or special symbols, SQL usually places those values before alphabetic characters according to the database's sorting rules.

```sql
SELECT name, age
FROM table_name
ORDER BY name;
```

---

## 4. Filtering Before Sorting

The **WHERE** clause is executed before **ORDER BY**, allowing you to filter the data before sorting the results.

```sql
SELECT name, age
FROM table_name
WHERE age IS NOT NULL
ORDER BY age DESC;
```

---

## 5. Sorting by a Column That Is Not Displayed

It is possible to sort by a column without displaying it in the result.

```sql
SELECT name
FROM table_name
ORDER BY age DESC;
```

However, including the sorting column often makes the output easier to understand.

```sql
SELECT name, age
FROM table_name
ORDER BY age DESC;
```

---

## 6. Sorting by Multiple Columns

The **ORDER BY** clause can sort data using multiple columns.

If two rows have the same value in the first column, SQL uses the second column to determine their order.

```sql
SELECT name, age
FROM table_name
ORDER BY fieldname1, fieldname2;
```

---

## 7. Using Different Sorting Directions

Different sorting directions can be applied to different columns.

```sql
SELECT name, age
FROM table_name
ORDER BY name ASC, age DESC;
```

The following query returns the same result because **ASC** is the default sorting order.

```sql
SELECT name, age
FROM table_name
ORDER BY name, age DESC;
```

---

## 8. Combining ORDER BY with Other SQL Clauses

The **ORDER BY** clause is frequently used together with **WHERE** and **LIMIT**.

```sql
SELECT name, age
FROM table_name
WHERE city = 'Istanbul'
ORDER BY age DESC
LIMIT 10;
```

---

# ✅ What I Learned Today

Today I learned different ways to use the **ORDER BY** clause in SQL. I practiced sorting data in ascending and descending order, sorting by multiple columns, combining **ORDER BY** with **WHERE** and **LIMIT**, and understanding that SQL can sort by a column even if it is not displayed in the result table.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_08.pdf)
