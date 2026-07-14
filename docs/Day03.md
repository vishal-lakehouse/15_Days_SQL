# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 03 -- DISTINCT, Aliases & Built-in Functions

> **Difficulty:** ⭐⭐☆☆☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

By the end of today you will be able to:

-   Remove duplicate values using `DISTINCT`
-   Rename columns and tables using aliases
-   Use common string functions
-   Use numeric functions
-   Use basic date functions in PostgreSQL
-   Write cleaner and more readable SQL

------------------------------------------------------------------------

# Why This Matters

Business reports often require unique values instead of duplicates.

Data Engineers also use built-in functions to clean, transform, and
standardize data before loading it into analytics platforms.

------------------------------------------------------------------------

# DISTINCT

Returns unique values.

``` sql
SELECT DISTINCT city
FROM customers;
```

Use `DISTINCT` when duplicate values should appear only once.

------------------------------------------------------------------------

# Column Aliases

Aliases rename output columns.

``` sql
SELECT customer_name AS customer,
       city AS customer_city
FROM customers;
```

------------------------------------------------------------------------

# Table Aliases

Useful for long table names and joins.

``` sql
SELECT c.customer_name,
       c.city
FROM customers AS c;
```

------------------------------------------------------------------------

# String Functions

## UPPER

``` sql
SELECT UPPER(customer_name)
FROM customers;
```

## LOWER

``` sql
SELECT LOWER(customer_name)
FROM customers;
```

## LENGTH

``` sql
SELECT LENGTH(customer_name)
FROM customers;
```

## TRIM

``` sql
SELECT TRIM(customer_name)
FROM customers;
```

## CONCAT

``` sql
SELECT CONCAT(first_name,' ',last_name)
FROM employees;
```

------------------------------------------------------------------------

# Numeric Functions

## ROUND

``` sql
SELECT ROUND(price,2)
FROM products;
```

## CEIL

``` sql
SELECT CEIL(price)
FROM products;
```

## FLOOR

``` sql
SELECT FLOOR(price)
FROM products;
```

## ABS

``` sql
SELECT ABS(discount)
FROM order_items;
```

------------------------------------------------------------------------

# Date Functions

## CURRENT_DATE

``` sql
SELECT CURRENT_DATE;
```

## CURRENT_TIMESTAMP

``` sql
SELECT CURRENT_TIMESTAMP;
```

## EXTRACT

``` sql
SELECT EXTRACT(YEAR FROM order_date)
FROM orders;
```

------------------------------------------------------------------------

# Real Business Scenario

The Sales team wants:

-   A unique list of customer cities.
-   Product names in uppercase.
-   Employee full names.
-   Current report date.
-   Rounded product prices.

These are everyday SQL tasks.

------------------------------------------------------------------------

# Common Mistakes

1.  Using DISTINCT unnecessarily.
2.  Forgetting aliases improve readability.
3.  Mixing string and numeric functions.
4.  Ignoring NULL values in CONCAT.
5.  Using functions on indexed columns without understanding
    performance.

------------------------------------------------------------------------

# Best Practices

-   Use aliases with meaningful names.
-   Apply DISTINCT only when required.
-   Keep function usage readable.
-   Format SQL consistently.
-   Use built-in functions instead of manual processing where
    appropriate.

------------------------------------------------------------------------

# Interview Corner

1.  What does DISTINCT do?
2.  DISTINCT vs GROUP BY?
3.  Why use aliases?
4.  Difference between UPPER and LOWER?
5.  What does LENGTH return?
6.  Why use TRIM?
7.  ROUND vs FLOOR?
8.  CURRENT_DATE vs CURRENT_TIMESTAMP?
9.  What is EXTRACT?
10. When should DISTINCT be avoided?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Display unique cities.
2.  Display unique categories.
3.  Rename customer_name as customer.
4.  Rename price as selling_price.
5.  Convert names to uppercase.
6.  Convert cities to lowercase.
7.  Display product name lengths.
8.  Trim customer names.
9.  Round product prices.
10. Display today's date.

## Medium (11--20)

11. Display unique departments.
12. Display employee full names.
13. Extract year from hire_date.
14. Extract month from order_date.
15. Round discounts.
16. Display warehouse names in uppercase.
17. Display supplier names in lowercase.
18. Find length of product names.
19. Display current timestamp.
20. Rename multiple output columns.

## Business (21--25)

21. Marketing needs unique customer cities.
22. HR needs employee names in uppercase.
23. Finance needs rounded prices.
24. Sales needs report generation date.
25. Inventory needs unique product categories.

## Interview (26--30)

26. DISTINCT vs GROUP BY.
27. Why aliases matter.
28. Explain EXTRACT.
29. ROUND vs CEIL vs FLOOR.
30. When would you avoid DISTINCT?

------------------------------------------------------------------------

# Mini Project

Write SQL queries to:

-   Produce a unique customer city report.
-   Format employee names.
-   Display rounded product prices.
-   Generate a report with today's date.
-   Create readable column aliases.

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Today's keywords:

-   DISTINCT
-   AS
-   UPPER
-   LOWER
-   LENGTH
-   TRIM
-   CONCAT
-   ROUND
-   FLOOR
-   CEIL
-   CURRENT_DATE
-   CURRENT_TIMESTAMP
-   EXTRACT

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT DISTINCT city FROM customers;

SELECT customer_name AS customer
FROM customers;

SELECT UPPER(customer_name)
FROM customers;

SELECT ROUND(price,2)
FROM products;

SELECT CURRENT_DATE;

SELECT EXTRACT(YEAR FROM order_date)
FROM orders;
```

------------------------------------------------------------------------

# Tomorrow (Day 04)

-   COUNT
-   SUM
-   AVG
-   MIN
-   MAX
-   GROUP BY
-   HAVING

------------------------------------------------------------------------

# Data Engineer Insight

Built-in SQL functions are heavily used in ETL pipelines for cleaning,
formatting, and standardizing data before it reaches reporting tools or
data warehouses.
