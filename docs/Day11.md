# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 11 -- CASE, COALESCE, NULLIF, CAST & Advanced Functions

> **Difficulty:** ⭐⭐⭐⭐⭐\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

-   Use `CASE` for conditional logic
-   Handle NULL values with `COALESCE`
-   Prevent errors using `NULLIF`
-   Convert data types using `CAST`
-   Work with advanced string and date functions
-   Apply data transformation techniques used in ETL

------------------------------------------------------------------------

# Why This Matters

Real-world data is messy. Data Engineers constantly transform, classify,
and clean data before loading it into warehouses and dashboards.

------------------------------------------------------------------------

# CASE Expression

Use `CASE` to apply conditional logic.

``` sql
SELECT product_name,
       price,
       CASE
           WHEN price >= 50000 THEN 'Premium'
           WHEN price >= 10000 THEN 'Standard'
           ELSE 'Budget'
       END AS price_band
FROM products;
```

------------------------------------------------------------------------

# COALESCE()

Returns the first non-NULL value.

``` sql
SELECT customer_name,
       COALESCE(phone,'Not Available') AS phone
FROM customers;
```

------------------------------------------------------------------------

# NULLIF()

Returns NULL if two expressions are equal.

Useful to avoid divide-by-zero errors.

``` sql
SELECT revenue / NULLIF(quantity,0)
FROM sales;
```

------------------------------------------------------------------------

# CAST()

Converts one data type to another.

``` sql
SELECT CAST(price AS NUMERIC(10,2))
FROM products;
```

or

``` sql
SELECT price::NUMERIC(10,2)
FROM products;
```

------------------------------------------------------------------------

# Advanced String Functions

## REPLACE

``` sql
SELECT REPLACE(product_name,'-',' ')
FROM products;
```

## SUBSTRING

``` sql
SELECT SUBSTRING(customer_name FROM 1 FOR 3)
FROM customers;
```

## POSITION

``` sql
SELECT POSITION('@' IN email)
FROM customers;
```

------------------------------------------------------------------------

# Advanced Date Functions

## AGE()

``` sql
SELECT AGE(CURRENT_DATE, hire_date)
FROM employees;
```

## DATE_TRUNC()

``` sql
SELECT DATE_TRUNC('month',order_date)
FROM orders;
```

------------------------------------------------------------------------

# Real Business Scenario

Create reports for:

-   Replace missing phone numbers
-   Categorize products by price
-   Monthly sales summary
-   Employee experience
-   Safe calculations with zero quantities

------------------------------------------------------------------------

# Common Mistakes

1.  Missing ELSE in CASE.
2.  Forgetting COALESCE for NULL values.
3.  Dividing by zero.
4.  Casting to incorrect data types.
5.  Ignoring date formatting.

------------------------------------------------------------------------

# Best Practices

-   Always provide an ELSE branch.
-   Use COALESCE for reporting.
-   Use NULLIF in calculations.
-   Cast explicitly when needed.
-   Keep transformation logic readable.

------------------------------------------------------------------------

# Interview Corner

1.  CASE vs IF?
2.  Why use COALESCE?
3.  What does NULLIF do?
4.  CAST vs implicit conversion?
5.  AGE() use case?
6.  DATE_TRUNC() purpose?
7.  Why handle NULLs?
8.  CASE in ETL?
9.  Data type conversion examples?
10. Common transformation tasks?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Categorize products by price.
2.  Replace NULL phone values.
3.  Replace NULL email values.
4.  Convert price to numeric.
5.  Display first three letters of names.
6.  Replace '-' in product names.
7.  Find '@' position in email.
8.  Show employee age using AGE().
9.  Display month using DATE_TRUNC().
10. Prevent divide-by-zero.

## Medium (11--20)

11. Customer status with CASE.
12. Revenue bands.
13. Inventory status.
14. Salary grades.
15. Payment categories.
16. Safe discount calculation.
17. Convert timestamps.
18. Clean product names.
19. Monthly order summary.
20. Employee tenure.

## Business (21--25)

21. Product pricing dashboard.
22. Customer contact cleanup.
23. Executive monthly sales report.
24. Inventory health report.
25. HR employee experience report.

## Interview (26--30)

26. CASE expression.
27. COALESCE vs NULLIF.
28. CAST examples.
29. DATE_TRUNC use case.
30. NULL handling in ETL.

------------------------------------------------------------------------

# Mini Project

Prepare a cleaned reporting dataset that:

-   Categorizes products
-   Replaces missing values
-   Calculates safe metrics
-   Formats dates
-   Standardizes text

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   CASE
-   COALESCE
-   NULLIF
-   CAST
-   REPLACE
-   SUBSTRING
-   POSITION
-   AGE
-   DATE_TRUNC

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT COALESCE(phone,'NA') FROM customers;

SELECT CASE
WHEN price>50000 THEN 'Premium'
ELSE 'Standard'
END
FROM products;

SELECT revenue/NULLIF(quantity,0)
FROM sales;

SELECT DATE_TRUNC('month',order_date)
FROM orders;
```

------------------------------------------------------------------------

# Tomorrow (Day 12)

-   INSERT
-   UPDATE
-   DELETE
-   Transactions
-   COMMIT
-   ROLLBACK
-   Views

------------------------------------------------------------------------

# Data Engineer Insight

CASE expressions, NULL handling, type conversion, and string/date
transformations are core ETL skills. They are heavily used in
PostgreSQL, Azure SQL, Snowflake, BigQuery, Databricks SQL, Redshift,
and Synapse for data cleansing and business-rule implementation.
