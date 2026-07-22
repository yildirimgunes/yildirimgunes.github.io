---
title: "SQL Learning Journal #3 – Filtering Data with WHERE"
date: 2026-07-21
permalink: /posts/sql-learning-journal-03/
tags:
  - SQL
  - Data Analytics
  - Learning Notes
---

# Introduction

Today I learned how to filter data in SQL using the `WHERE` clause. The `WHERE` clause allows us to retrieve only the rows that satisfy a specified condition, making SQL queries more precise and efficient.

## Filtering Data

The `WHERE` clause is used together with the `SELECT` statement to filter records based on one or more conditions.

---

## SQL Commands Learned Today

### 1. Greater Than (`>`)

Returns records where the value is greater than the specified value.

```sql
SELECT field_name
FROM table_name
WHERE field_name > 1973;
```

---

### 2. Equal To (`=`)

Returns records where the value is equal to the specified value.

```sql
SELECT field_name
FROM table_name
WHERE field_name = 1973;
```

---

### 3. Not Equal To (`<>`)

The `<>` operator means **not equal to**.

```sql
SELECT field_name
FROM table_name
WHERE field_name <> 1973;
```

---

### 4. Greater Than or Equal To (`>=`)

Returns records where the value is greater than or equal to the specified value.

```sql
SELECT field_name
FROM table_name
WHERE field_name >= 1973;
```

---

### 5. Using `WHERE` with Strings

The `WHERE` clause can also be used to filter text values.

```sql
SELECT field_name
FROM table_name
WHERE field_name = 'John';
```

> **Note:** In SQL, string values are normally enclosed in **single quotation marks (`'`)**.

---

## What I Learned Today

Today I learned how the `WHERE` clause works together with the `SELECT` statement to filter data in a table. I practiced using comparison operators such as `>`, `=`, `<>`, and `>=` to retrieve specific records. I also learned that the `WHERE` clause can be used with both numeric and text values.

---

## Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_03.pdf)
