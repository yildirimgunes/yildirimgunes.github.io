---
title: "SQL Learning Journal #4 – Multiple Criteria, LIKE and IN"
date: 2026-07-23
permalink: /posts/sql-learning-journal-04/
tags:
  - SQL
  - Data Analytics
  - Learning Journal
---

# 📘 Introduction

In today's lesson, I learned how to filter data using multiple conditions. I practiced the **AND**, **OR**, **BETWEEN**, **LIKE**, **NOT LIKE**, and **IN** operators. These commands make SQL queries more flexible and efficient when searching for specific information.

---

# 💻 SQL Commands Learned Today

## 1. Multiple Criteria Operators

### Using OR

Returns records that satisfy at least one condition.

```sql
SELECT *
FROM table_name
WHERE name = 'John' OR name = 'Mike';
```

### Using AND

Returns records that satisfy both conditions.

```sql
SELECT *
FROM table_name
WHERE name = 'John' AND city = 'Istanbul';
```

### Using BETWEEN

Returns values within a specified range (inclusive).

```sql
SELECT *
FROM table_name
WHERE age BETWEEN 5 AND 10;
```

Example with multiple conditions:

```sql
SELECT *
FROM table_name
WHERE age BETWEEN 5 AND 10
AND city = 'Istanbul';
```

---

## 2. Filtering Text with LIKE and NOT LIKE

### Starts with

```sql
WHERE name LIKE 'Joh%'
```

Matches values such as:

- John
- Johnson
- Johnny

`%` represents zero or more characters.

### Single Character

```sql
WHERE name LIKE 'Joh_'
```

Matches values such as:

- John

`_` represents exactly one character.

### Excluding a Pattern

```sql
WHERE name NOT LIKE 'Y%'
```

Returns names that do not start with the letter **Y**.

### Ends with

```sql
WHERE name LIKE '%s'
```

Returns text ending with the letter **s**.

### Character Position

```sql
WHERE name LIKE '__n%'
```

Returns text where the third character is **n**.

---

## 3. Using the IN Operator

Instead of writing:

```sql
WHERE year = 1973
OR year = 1977
OR year = 1979;
```

we can write:

```sql
WHERE year IN (1973, 1977, 1979);
```

The same method can also be used with text values.

```sql
WHERE name IN ('John', 'Albert');
```

The **IN** operator makes SQL queries shorter, cleaner, and easier to read.

---
# ✅ What I Learned Today
Today I learned how to filter data using multiple conditions with **AND**, **OR**, and **BETWEEN**.I also practiced text filtering with **LIKE**, **NOT LIKE**, and the **IN** operator.
One important lesson I learned today is that understanding SQL commands is only the first step. Real learning comes through regular practice. 
Even after understanding the syntax, I may forget how to write queries unless I continue practicing consistently.
