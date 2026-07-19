---
title: "SQL Learning Journal #1 – Basic SQL Concepts and the SELECT Statement"
date: 2026-07-19
permalink: /posts/sql-learning-journal-01/
tags:
  - SQL
  - Data Analytics
  - Learning Notes
---
# Introduction

Today I started learning SQL as part of my Data Analytics learning journey.

The purpose of these notes is to document what I learn, organize my knowledge, and create a personal reference that I can revisit in the future. Rather than being a complete SQL tutorial, this journal reflects my own learning process and understanding of the concepts.

In this first lesson, I learned the basic structure of relational databases and the fundamental SQL commands used to retrieve data.
Basic Concepts
Today I learned the basic terminology used in SQL and relational databases.
Data are stored in databases, which consist of one or more tables. Each table contains records (rows or observations) and fields (columns). When naming fields, it is generally recommended to use singular nouns (for example, name instead of names).
The information stored in tables can be either text (string) or numeric (integers or floating-point numbers).
A database usually consists of multiple related tables that share common information. Such a database is called a relational database.
SQL Commands Learned Today
1. Retrieving Data with SELECT
The SELECT ... FROM statement is used to retrieve one or more columns from a table.
SELECT field_name
FROM table_name;
Examples
SELECT name
FROM table_name;

SELECT name, num
FROM table_name;

SELECT name, num, surname
FROM table_name;

SELECT *
FROM table_name;
SELECT * retrieves all columns from a table. The * symbol is called a wildcard.
Note: The output of a SQL query is called a result set.
2. Renaming a Column
The AS keyword is used to give a temporary name (alias) to a column.
SELECT name AS sur_name
FROM table_name;
3. Selecting Unique Values
The DISTINCT keyword returns only unique values.
SELECT DISTINCT year_born
FROM table_name;
It can also be applied to multiple columns.
SELECT DISTINCT year_born, city
FROM table_name;
If both year_born and city have the same values in multiple rows, only one unique combination is returned.
4. Creating a View
A VIEW stores a SQL query as a virtual table so that it can be reused later.
CREATE VIEW employee_name AS
SELECT name, surname, hired
FROM table_name;
A view does not duplicate the data. It stores only the query definition.
5. PostgreSQL vs. SQL Server
One difference I learned today is how these database systems limit the number of returned rows.
PostgreSQL
SELECT name
FROM employee
LIMIT 3;
SQL Server
SELECT TOP (3) name
FROM employee;
What I Learned Today
Today I became familiar with the basic concepts of relational databases and wrote my first SQL queries using the SELECT statement. I also learned how to rename columns with AS, retrieve unique values using DISTINCT, create reusable views, and the difference between the LIMIT command in PostgreSQL and the TOP command in SQL Server.
<img width="468" height="633" alt="image" src="https://github.com/user-attachments/assets/c2b95ff5-79d3-4579-9f12-f0bdf5e07289" />
