# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 07 -- Subqueries, Correlated Subqueries, EXISTS, IN, ANY & ALL

> **Difficulty:** ⭐⭐⭐⭐☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

By the end of today you will be able to:

-   Understand subqueries
-   Write scalar and multi-row subqueries
-   Use correlated subqueries
-   Use EXISTS and NOT EXISTS
-   Compare IN, ANY and ALL
-   Solve real business problems using nested queries

------------------------------------------------------------------------

# Why This Matters

Many business questions require one query to depend on the result of
another.

Examples:

-   Customers who placed orders
-   Products never ordered
-   Employees earning above department average
-   Categories with highest sales

These are solved using subqueries.

------------------------------------------------------------------------

# What is a Subquery?

A subquery is a query written inside another SQL query.

``` sql
SELECT customer_name
FROM customers
WHERE customer_id IN (
    SELECT customer_id
    FROM orders
);
```

The inner query executes first, then the outer query uses its result.

------------------------------------------------------------------------

# Types of Subqueries

-   Scalar Subquery (returns one value)
-   Multi-row Subquery
-   Correlated Subquery
-   EXISTS / NOT EXISTS

------------------------------------------------------------------------

# Scalar Subquery

``` sql
SELECT product_name
FROM products
WHERE price >
(
SELECT AVG(price)
FROM products
);
```

------------------------------------------------------------------------

# Correlated Subquery

The inner query depends on the current row of the outer query.

``` sql
SELECT c.customer_name
FROM customers c
WHERE EXISTS
(
SELECT 1
FROM orders o
WHERE o.customer_id = c.customer_id
);
```

------------------------------------------------------------------------

# EXISTS

Returns TRUE if at least one matching row exists.

``` sql
SELECT customer_name
FROM customers c
WHERE EXISTS
(
SELECT 1
FROM orders o
WHERE o.customer_id=c.customer_id
);
```

------------------------------------------------------------------------

# NOT EXISTS

Find customers without orders.

``` sql
SELECT customer_name
FROM customers c
WHERE NOT EXISTS
(
SELECT 1
FROM orders o
WHERE o.customer_id=c.customer_id
);
```

------------------------------------------------------------------------

# IN

``` sql
SELECT *
FROM customers
WHERE city IN ('Delhi','Mumbai','Bangalore');
```

------------------------------------------------------------------------

# ANY

``` sql
SELECT *
FROM products
WHERE price > ANY
(
SELECT price
FROM products
WHERE category='Electronics'
);
```

------------------------------------------------------------------------

# ALL

``` sql
SELECT *
FROM products
WHERE price > ALL
(
SELECT price
FROM products
WHERE category='Accessories'
);
```

------------------------------------------------------------------------

# Real Business Scenario

The retail analytics team wants to know:

-   Customers who purchased at least once.
-   Products never sold.
-   Employees above department average salary.
-   Suppliers with no products.
-   Categories containing premium products.

These are classic subquery use cases.

------------------------------------------------------------------------

# Common Mistakes

1.  Returning multiple rows in a scalar subquery.
2.  Confusing EXISTS with IN.
3.  Forgetting correlation conditions.
4.  Using subqueries where JOIN is more appropriate.
5.  Writing unreadable nested queries.

------------------------------------------------------------------------

# Best Practices

-   Keep subqueries simple.
-   Use aliases consistently.
-   Prefer EXISTS for existence checks.
-   Test inner query independently.
-   Format nested queries clearly.

------------------------------------------------------------------------

# Interview Corner

1.  What is a subquery?
2.  Types of subqueries?
3.  EXISTS vs IN?
4.  Correlated vs non-correlated subquery?
5.  ANY vs ALL?
6.  When would you use NOT EXISTS?
7.  Can a subquery return multiple columns?
8.  JOIN vs subquery?
9.  Performance considerations?
10. Real Data Engineering use case?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Customers who placed orders.
2.  Products above average price.
3.  Employees above average salary.
4.  Categories with products.
5.  Suppliers with products.
6.  Cities having customers.
7.  Orders by active customers.
8.  Warehouses with stock.
9.  Products in sold categories.
10. Customers from ordering cities.

## Medium (11--20)

11. Products never ordered.
12. Customers without orders.
13. Employees below department average.
14. Highest priced product by category.
15. Orders above average amount.
16. Suppliers without products.
17. Stores with sales.
18. Categories above average revenue.
19. Products in top-selling categories.
20. Payments above average.

## Business (21--25)

21. VIP customer report.
22. Unsold product report.
23. Salary comparison report.
24. Low-performing category report.
25. Supplier activity report.

## Interview (26--30)

26. EXISTS vs IN.
27. Correlated subquery.
28. ANY vs ALL.
29. JOIN vs Subquery.
30. Optimize nested queries.

------------------------------------------------------------------------

# Mini Project

Create SQL queries to identify:

-   Customers without purchases
-   Unsold products
-   High-value customers
-   Above-average products
-   Active suppliers

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   Subquery
-   Scalar Subquery
-   Correlated Subquery
-   EXISTS
-   NOT EXISTS
-   IN
-   ANY
-   ALL

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT *
FROM customers
WHERE customer_id IN
(
SELECT customer_id
FROM orders
);

SELECT *
FROM customers c
WHERE EXISTS
(
SELECT 1
FROM orders o
WHERE o.customer_id=c.customer_id
);
```

------------------------------------------------------------------------

# Tomorrow (Day 08)

-   Common Table Expressions (CTEs)
-   Recursive CTEs
-   WITH clause

------------------------------------------------------------------------

# Data Engineer Insight

Subqueries are frequently used in ETL validation, data quality checks,
and business rule implementation. Knowing when to use JOINs versus
subqueries is an important interview skill for Data Engineers.
