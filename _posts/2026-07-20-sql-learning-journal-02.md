---

---
title: "SQL Learning Journal #2 – Data Aggregation Functions"
date: 2026-07-20
permalink: /posts/sql-learning-journal-02/
tags:
  - SQL
  - Data Analytics
  - Learning Notes

---

# Introduction

Today I learned SQL aggregation functions, which are used to summarize and analyze data stored in database tables. These functions make it possible to calculate totals, averages, minimum and maximum values, and the number of records in a table.

## Data Aggregation

Aggregation functions are used to perform calculations on multiple rows and return a single summarized result.

---

## SQL Commands Learned Today

### 1. `SUM()`

The `SUM()` function adds all numeric values in a column.

```sql
SELECT SUM(field_name)
FROM table_name;
```

The result can be renamed using the `AS` keyword.

```sql
SELECT SUM(field_name) AS total_revenue
FROM orders;
```

> **Note:** The `AS` keyword only changes the column name in the **result set**. It does **not** modify the original column name in the database.

---

### 2. `AVG()`, `MIN()`, `MAX()`, and `COUNT()`

These aggregation functions calculate the average, minimum value, maximum value, and the number of rows in a table.

```sql
SELECT
    MIN(field_name) AS minimum_value,
    MAX(field_name) AS maximum_value,
    AVG(field_name) AS average_value
FROM table_name;
```

Count the total number of values (or non-NULL rows) in a column.

```sql
SELECT COUNT(field_name) AS count_of_values
FROM table_name;
```

---

### 3. `DISTINCT`

The `DISTINCT` keyword returns only unique values.

```sql
SELECT DISTINCT field_name
FROM table_name;
```

---

### 4. Counting Unique Values

The following query counts the number of unique values in a column.

```sql
SELECT COUNT(DISTINCT field_name)
FROM table_name;
```

---

### 5. Counting All Records

The following query returns the total number of records in a table.

```sql
SELECT COUNT(*) AS total_records
FROM table_name;
```

---

## What I Learned Today

Today I learned how SQL aggregation functions summarize data efficiently. I practiced using the `SUM()`, `AVG()`, `MIN()`, `MAX()`, and `COUNT()` functions to calculate statistics from table data. I also learned how to retrieve unique values using `DISTINCT` and how to count unique values and total records in a table.
---

## Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_02.pdf)
