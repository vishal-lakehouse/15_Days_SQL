# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 02 -- Filtering Data with WHERE

> **Difficulty:** ⭐☆☆☆☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

By the end of today you will be able to:

-   Filter rows using `WHERE`
-   Use comparison operators
-   Combine conditions with `AND`, `OR`, and `NOT`
-   Search text using `LIKE` and `ILIKE`
-   Filter ranges with `BETWEEN`
-   Filter lists with `IN`
-   Handle missing values using `IS NULL`

------------------------------------------------------------------------

# Why This Matters

Data Engineers rarely work with every row in a table.

Instead they retrieve only the required data, such as:

-   Today's orders
-   Active customers
-   Products below stock threshold
-   Orders from one city
-   Payments above a certain amount

The `WHERE` clause is one of the most frequently used SQL features in
production.

------------------------------------------------------------------------

# Theory

## WHERE

The `WHERE` clause filters rows.

### Syntax

``` sql
SELECT column_name
FROM table_name
WHERE condition;
```

### Example

``` sql
SELECT *
FROM customers
WHERE city = 'Bangalore';
```

------------------------------------------------------------------------

# Comparison Operators

  Operator   Meaning
  ---------- -----------------------
  =          Equal
  \<\>       Not Equal
  \>         Greater Than
  \<         Less Than
  \>=        Greater Than or Equal
  \<=        Less Than or Equal

Example:

``` sql
SELECT *
FROM products
WHERE price > 50000;
```

------------------------------------------------------------------------

# AND

Returns rows only when **all** conditions are true.

``` sql
SELECT *
FROM customers
WHERE city='Bangalore'
AND status='Active';
```

------------------------------------------------------------------------

# OR

Returns rows when **any** condition is true.

``` sql
SELECT *
FROM customers
WHERE city='Delhi'
OR city='Mumbai';
```

------------------------------------------------------------------------

# NOT

Reverses a condition.

``` sql
SELECT *
FROM orders
WHERE NOT order_status='Completed';
```

------------------------------------------------------------------------

# LIKE

Pattern matching.

``` sql
SELECT *
FROM customers
WHERE customer_name LIKE 'A%';
```

Common patterns:

  Pattern   Meaning
  --------- ---------------
  A%        Starts with A
  %A        Ends with A
  %A%       Contains A

------------------------------------------------------------------------

# ILIKE (PostgreSQL)

Case-insensitive version of LIKE.

``` sql
SELECT *
FROM customers
WHERE customer_name ILIKE 'rahul%';
```

------------------------------------------------------------------------

# BETWEEN

Range filtering.

``` sql
SELECT *
FROM products
WHERE price BETWEEN 1000 AND 5000;
```

------------------------------------------------------------------------

# IN

Filter multiple values.

``` sql
SELECT *
FROM customers
WHERE city IN ('Delhi','Mumbai','Bangalore');
```

------------------------------------------------------------------------

# IS NULL

Find missing values.

``` sql
SELECT *
FROM customers
WHERE phone IS NULL;
```

------------------------------------------------------------------------

# IS NOT NULL

``` sql
SELECT *
FROM customers
WHERE email IS NOT NULL;
```

------------------------------------------------------------------------

# Real Company Scenario

A retail company asks you to:

-   Find customers from Bangalore.
-   Find products priced above ₹25,000.
-   Find orders that are still pending.
-   Find customers with missing phone numbers.
-   Find inventory between 10 and 50 units.

All of these require the `WHERE` clause.

------------------------------------------------------------------------

# Common Mistakes

1.  Using `=` instead of `IS NULL`.
2.  Forgetting quotes around text values.
3.  Confusing `AND` and `OR`.
4.  Using `LIKE` when exact match is needed.
5.  Ignoring parentheses in complex conditions.

------------------------------------------------------------------------

# Best Practices

-   Filter as early as possible.
-   Use readable formatting.
-   Use parentheses for mixed conditions.
-   Avoid unnecessary `SELECT *`.
-   Test queries with `LIMIT`.

------------------------------------------------------------------------

# Interview Corner

1.  What is the WHERE clause?
2.  WHERE vs HAVING?
3.  Difference between LIKE and ILIKE?
4.  Why can't NULL be compared using `=`?
5.  Difference between IN and OR?
6.  Explain BETWEEN.
7.  Explain AND.
8.  Explain OR.
9.  Explain NOT.
10. When is WHERE executed?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Show customers from Bangalore.
2.  Show products above ₹10,000.
3.  Show products below ₹500.
4.  Show employees with salary above ₹60,000.
5.  Show pending orders.
6.  Show active customers.
7.  Show suppliers from Delhi.
8.  Show warehouses with stock below 100.
9.  Show products in Electronics category.
10. Show payments above ₹5,000.

## Medium (11--20)

11. Customers from Mumbai or Delhi.
12. Customers from Bangalore and Active.
13. Products between ₹1,000 and ₹5,000.
14. Orders not completed.
15. Customers whose names start with A.
16. Customers whose names contain "an".
17. Products in three categories using IN.
18. Employees hired after a given date.
19. Customers with NULL phone numbers.
20. Customers with non-NULL email.

## Business (21--25)

21. Marketing wants active customers from Bangalore.
22. Finance wants payments above ₹25,000.
23. Inventory needs products with low stock.
24. HR wants employees earning above ₹80,000.
25. Sales wants pending orders from one city.

## Interview (26--30)

26. Explain WHERE execution.
27. LIKE vs ILIKE.
28. BETWEEN vs \>= AND \<=.
29. IN vs multiple OR conditions.
30. Explain NULL handling.

------------------------------------------------------------------------

# Mini Project

Write SQL queries to generate:

-   Active customer list.
-   High-value products.
-   Pending orders.
-   Low inventory report.
-   Customers with missing phone numbers.

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Today's keywords:

-   WHERE
-   AND
-   OR
-   NOT
-   LIKE
-   ILIKE
-   BETWEEN
-   IN
-   IS NULL

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT * FROM customers WHERE city='Bangalore';

SELECT * FROM products WHERE price > 10000;

SELECT * FROM customers
WHERE city='Delhi'
AND status='Active';

SELECT * FROM customers
WHERE customer_name LIKE 'A%';

SELECT * FROM products
WHERE price BETWEEN 1000 AND 5000;

SELECT * FROM customers
WHERE city IN ('Delhi','Mumbai');

SELECT * FROM customers
WHERE phone IS NULL;
```

------------------------------------------------------------------------

# Tomorrow (Day 03)

-   DISTINCT
-   Aliases
-   String Functions
-   Numeric Functions
-   Date Functions

------------------------------------------------------------------------

# Data Engineer Insight

Filtering data at the source reduces data movement, improves ETL
performance, and minimizes processing costs. Efficient `WHERE` clauses
are essential in PostgreSQL, Azure SQL, Databricks SQL, Snowflake,
BigQuery, Redshift, and Synapse.
