---
title: "SQL Learning Journal #9 – Grouping Data with GROUP BY"
date: 2026-07-29
permalink: /posts/sql-learning-journal-09/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

Today I learned how to group data according to the values of one or more columns by using the **GROUP BY** clause. Grouping data allows SQL to summarize information with aggregate functions such as **COUNT()**, **SUM()**, **AVG()**, **MIN()**, and **MAX()**.

---

# 💻 SQL Commands Learned Today

## 1. GROUP BY with a Single Column

The **GROUP BY** clause is commonly used together with aggregate functions such as **COUNT()**.

The following query counts the number of records for each year.

```sql
SELECT year, COUNT(age) AS age_count
FROM table_name
GROUP BY year;
```

Without an aggregate function, this type of query would produce an error because SQL requires all selected columns to either be grouped or aggregated.

---

## 2. GROUP BY with Multiple Columns

It is also possible to group data using more than one column.

```sql
SELECT age, year, COUNT(city) AS count_city
FROM table_name
GROUP BY age, year;
```

---

## 3. Combining GROUP BY with ORDER BY

The grouped results can be sorted using the **ORDER BY** clause.

```sql
SELECT age, year, COUNT(city) AS count_city
FROM table_name
GROUP BY age, year
ORDER BY age DESC
LIMIT 5;
```

---

# ✅ What I Learned Today

Today I learned how to summarize data using the **GROUP BY** clause. I practiced grouping records by one or multiple columns, combining **GROUP BY** with **COUNT()**, and sorting grouped results using **ORDER BY**. I also learned that aggregate functions are essential when summarizing grouped data.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_09.pdf)
