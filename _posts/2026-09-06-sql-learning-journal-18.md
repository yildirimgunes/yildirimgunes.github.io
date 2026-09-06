---
title: "SQL Learning Journal #18 – SET OPERATIONS"
date: 2026-09-06
permalink: /posts/sql-learning-journal-18/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 1. UNION and UNION ALL

### UNION

`UNION` combines the results of two or more `SELECT` queries into a single result table.

If the same row appears in both tables, `UNION` returns it only once.

~~~sql
SELECT *
FROM product1_table

UNION

SELECT *
FROM product2_table;
~~~

### Example

#### product1_table

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 3 | keyboard | 10 |
| 4 | coffee | 15 |
| 5 | tea | 15 |
| 6 | milk | 15 |

#### product2_table

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 7 | keyboard_a | 15 |

### Result

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 3 | keyboard | 10 |
| 4 | coffee | 15 |
| 5 | tea | 15 |
| 6 | milk | 15 |
| 7 | keyboard_a | 15 |

The duplicate rows (`laptop` and `mouse`) appear only once.

---

### UNION ALL

`UNION ALL` also combines the results of two or more `SELECT` queries, but it keeps duplicate rows.

~~~sql
SELECT *
FROM product1_table

UNION ALL

SELECT *
FROM product2_table;
~~~

### Result

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 3 | keyboard | 10 |
| 4 | coffee | 15 |
| 5 | tea | 15 |
| 6 | milk | 15 |
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 7 | keyboard_a | 15 |

The rows that appear in both tables are included twice.

### 📌 Key Difference

- `UNION` → combines results and removes duplicate rows.
- `UNION ALL` → combines results and keeps duplicate rows.

---

# 2. INTERSECT

`INTERSECT` returns only the rows that exist in both result sets.

### table_1

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 3 | keyboard | 10 |

### table_2

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 4 | coffee | 15 |
| 5 | tea | 15 |
| 6 | milk | 15 |
| 7 | keyboard_a | 15 |

~~~sql
SELECT *
FROM table_1

INTERSECT

SELECT *
FROM table_2;
~~~

### Result

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |

The result contains only the row that is common to both tables.

---

# 3. EXCEPT

`EXCEPT` returns the rows that exist in the first result set but do not exist in the second result set.

### table_1

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 2 | mouse | 10 |
| 3 | keyboard | 10 |

### table_2

| product_id | product | category_id |
|-----------:|---------|------------:|
| 1 | laptop | 10 |
| 4 | coffee | 15 |
| 5 | tea | 15 |
| 6 | milk | 15 |
| 7 | keyboard_a | 15 |

~~~sql
SELECT *
FROM table_1

EXCEPT

SELECT *
FROM table_2;
~~~

### Result

| product_id | product | category_id |
|-----------:|---------|------------:|
| 2 | mouse | 10 |
| 3 | keyboard | 10 |

The result contains the rows that are in `table_1` but not in `table_2`.

---

# 📌 Summary of SET OPERATIONS

| Operation | Result |
|-----------|--------|
| `UNION` | Combines two result sets and removes duplicates |
| `UNION ALL` | Combines two result sets and keeps duplicates |
| `INTERSECT` | Returns rows common to both result sets |
| `EXCEPT` | Returns rows in the first result set but not in the second |

---

# ✅ What I Learned Today

Today I learned how SQL set operations can be used to combine and compare groups of data.

I learned that `UNION` combines two result sets while removing duplicate rows, whereas `UNION ALL` keeps duplicates. I also learned that `INTERSECT` returns the rows that are common to both result sets, while `EXCEPT` returns the rows that exist in the first result set but not in the second.

---

## 📥 Downloads

- 📄 [Download PDF](/files/SQL_Learning_Journal_18.pdf)
