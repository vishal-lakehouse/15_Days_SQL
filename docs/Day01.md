# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 01 -- SQL Fundamentals & PostgreSQL

> **Difficulty:** ⭐☆☆☆☆\
> **Estimated Study Time:** 2 Hours

## Motivational Quote

> "Every Data Engineer writes SQL. Master the basics and the advanced
> topics become much easier."

------------------------------------------------------------------------

# Learning Objectives

By the end of today you should be able to:

-   Understand what SQL is.
-   Understand PostgreSQL.
-   Explain Database, Schema, Table, Row and Column.
-   Install PostgreSQL and pgAdmin.
-   Write your first SQL query.
-   Use `SELECT`, `FROM`, `ORDER BY`, and `LIMIT`.

------------------------------------------------------------------------

# Theory

## What is SQL?

SQL (Structured Query Language) is the standard language used to
communicate with relational databases.

### Why SQL?

-   Retrieve business data
-   Analyze sales
-   Build ETL pipelines
-   Validate data quality
-   Feed dashboards

------------------------------------------------------------------------

## What is PostgreSQL?

PostgreSQL is a powerful open-source Relational Database Management
System (RDBMS).

It stores data and executes SQL queries efficiently.

------------------------------------------------------------------------

## SQL vs PostgreSQL

  SQL                     PostgreSQL
  ----------------------- -------------------------
  Query language          Database system
  Used to ask questions   Stores and manages data

------------------------------------------------------------------------

## Database Hierarchy

``` text
Server
└── Database
    └── Schema
        └── Table
            ├── Rows
            └── Columns
```

------------------------------------------------------------------------

## Core SQL Statements

### SELECT

Retrieve data.

``` sql
SELECT *
FROM customers;
```

### SELECT Specific Columns

``` sql
SELECT customer_name,
       city
FROM customers;
```

### ORDER BY

Sort records.

``` sql
SELECT product_name,
       price
FROM products
ORDER BY price DESC;
```

### LIMIT

Return only a limited number of rows.

``` sql
SELECT *
FROM customers
LIMIT 10;
```

------------------------------------------------------------------------

# Real Business Scenario

You are a Junior Data Engineer at a retail company.

Business requests:

-   Show the first 20 customers.
-   Show the most expensive products.
-   Preview the orders table.

These tasks use `SELECT`, `ORDER BY`, and `LIMIT`.

------------------------------------------------------------------------

# Common Mistakes

1.  Using `SELECT *` in production.
2.  Poor query formatting.
3.  Assuming row order without `ORDER BY`.
4.  Retrieving unnecessary rows.
5.  Ignoring readable naming conventions.

------------------------------------------------------------------------

# Best Practices

-   Use uppercase SQL keywords.
-   Retrieve only required columns.
-   Format SQL consistently.
-   Use `LIMIT` while testing.
-   Write readable SQL.

------------------------------------------------------------------------

# Interview Corner

1.  What is SQL?
2.  What is PostgreSQL?
3.  Difference between SQL and PostgreSQL?
4.  What is a database?
5.  What is a schema?
6.  What is a table?
7.  What is a row?
8.  What is a column?
9.  Why avoid `SELECT *`?
10. Why use `ORDER BY`?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Display all customers.
2.  Display all products.
3.  Display all employees.
4.  Show customer names only.
5.  Show product names only.
6.  Display all warehouses.
7.  Display all suppliers.
8.  Display all orders.
9.  Display all payments.
10. Display all categories.

## Medium (11--20)

11. Show first 10 customers.
12. Show first 20 products.
13. Show first 50 orders.
14. Sort products by price ascending.
15. Sort products by price descending.
16. Sort employees alphabetically.
17. Sort customers by city.
18. Sort suppliers alphabetically.
19. Sort warehouses alphabetically.
20. Display first 25 stores.

## Business (21--25)

21. First 20 customers for marketing.
22. Top expensive products.
23. Alphabetical employee list.
24. First 15 warehouses.
25. Preview first 30 orders.

## Interview (26--30)

26. Explain `SELECT *`.
27. Explain `ORDER BY`.
28. Explain `LIMIT`.
29. Explain Database → Schema → Table.
30. Explain why SQL is important for Data Engineers.

------------------------------------------------------------------------

# Mini Project

Using the retail database, write SQL queries to:

-   Display all customers.
-   Display all products.
-   Display customer names.
-   Display first 20 products.
-   Display products ordered by price.
-   Display employees alphabetically.

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Remember:

-   SQL retrieves data.
-   PostgreSQL stores data.
-   Database → Schema → Table → Row → Column.
-   Keywords: `SELECT`, `FROM`, `ORDER BY`, `LIMIT`.

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT *
FROM customers;

SELECT customer_name, city
FROM customers;

SELECT *
FROM products
ORDER BY price DESC;

SELECT *
FROM customers
LIMIT 10;
```

------------------------------------------------------------------------

# Tomorrow (Day 02)

-   WHERE
-   Comparison Operators
-   AND
-   OR
-   LIKE
-   BETWEEN
-   IN
-   IS NULL

------------------------------------------------------------------------

# Data Engineer Insight

Almost every Data Engineering task begins by exploring data with SQL
before building ETL pipelines in Azure SQL, Databricks, Snowflake,
Synapse, BigQuery, or Redshift.
