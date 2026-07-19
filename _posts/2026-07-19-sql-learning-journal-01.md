---
title: "SQL Learning Journal #1 – Basic SQL Concepts and the SELECT Statement"
date: 2026-07-19
permalink: /posts/sql-learning-journal-01/
tags:
  - SQL
  - Data Analytics
  - Learning Notes
---
## Basic Concepts

Today I learned the basic terminology used in SQL and relational databases.

Data are stored in **databases**, which consist of one or more **tables**. Each table contains **rows (records or observations)** and **columns (fields)**.

When naming columns, it is generally recommended to use **singular nouns** (for example, `name` instead of `names`).

The information stored in tables can be either **text (string)** or **numeric** (integers or floating-point numbers).

A relational database consists of multiple related tables that share common information through relationships.

---

## SQL Commands Learned Today

### 1. SELECT Statement

The `SELECT ... FROM` statement is used to retrieve one or more columns from a table.

**Examples**

```sql
SELECT field_name
FROM table_name;

SELECT name
FROM table_name;

SELECT name, num
FROM table_name;

SELECT name, num, surname
FROM table_name;

SELECT *
FROM table_name;
```

> **Note:** `SELECT *` retrieves all columns from a table. The `*` symbol is called a **wildcard**.

> **Note:** The output produced by a SQL query is called a **result set**.

---

### 2. Renaming a Column (`AS`)

The `AS` keyword is used to assign a temporary name (alias) to a column.

```sql
SELECT name AS sur_name
FROM table_name;
```

---

### 3. Selecting Unique Values (`DISTINCT`)

The `DISTINCT` keyword returns only unique values.

```sql
SELECT DISTINCT year_born
FROM table_name;
```

It can also be used with multiple columns.

```sql
SELECT DISTINCT year_born, city
FROM table_name;
```

If both `year_born` and `city` contain the same values in multiple rows, only one unique combination is returned.

---

### 4. Creating a View

A **VIEW** stores a SQL query as a virtual table so that it can be reused later.

```sql
CREATE VIEW employee_name AS
SELECT name, surname, hired
FROM table_name;
```

A view stores the query definition rather than duplicating the data.

---

### 5. PostgreSQL vs. SQL Server

One difference I learned today is how these database systems limit the number of returned rows.

**PostgreSQL**

```sql
SELECT name
FROM employee
LIMIT 3;
```

**SQL Server**

```sql
SELECT TOP (3) name
FROM employee;
```

---

## What I Learned Today

Today I learned the basic concepts of relational databases and wrote my first SQL queries using the `SELECT` statement. I also learned how to rename columns with `AS`, retrieve unique values using `DISTINCT`, create reusable views, and the difference between the `LIMIT` command in PostgreSQL and the `TOP` command in SQL Server.

