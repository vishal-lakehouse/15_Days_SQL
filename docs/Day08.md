# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 08 -- Common Table Expressions (CTEs) & Recursive CTEs

> **Difficulty:** ⭐⭐⭐⭐☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

By the end of today you will be able to:

-   Understand Common Table Expressions (CTEs)
-   Use the `WITH` clause
-   Improve query readability
-   Replace complex nested subqueries with CTEs
-   Understand Recursive CTEs
-   Build reusable query logic

------------------------------------------------------------------------

# Why This Matters

As SQL queries become larger, they become difficult to read and
maintain.

CTEs help Data Engineers write cleaner, modular SQL for reporting, ETL,
and analytics.

------------------------------------------------------------------------

# What is a CTE?

A Common Table Expression (CTE) is a temporary named result set created
using the `WITH` clause.

It exists only for the duration of the query.

``` sql
WITH customer_orders AS (
    SELECT customer_id,
           COUNT(*) AS total_orders
    FROM orders
    GROUP BY customer_id
)
SELECT *
FROM customer_orders;
```

------------------------------------------------------------------------

# Why Use CTEs?

-   Improve readability
-   Break complex logic into smaller parts
-   Reuse intermediate results
-   Simplify debugging

------------------------------------------------------------------------

# CTE vs Subquery

  CTE                             Subquery
  ------------------------------- --------------------------
  More readable                   Can become deeply nested
  Easier to debug                 Harder to maintain
  Better for step-by-step logic   Better for simple tasks

------------------------------------------------------------------------

# Multiple CTEs

``` sql
WITH sales AS (
    SELECT customer_id, SUM(amount) AS revenue
    FROM payments
    GROUP BY customer_id
),
top_customers AS (
    SELECT *
    FROM sales
    WHERE revenue > 100000
)
SELECT *
FROM top_customers;
```

------------------------------------------------------------------------

# Recursive CTE

Recursive CTEs solve hierarchical problems.

Example: Employee → Manager hierarchy.

``` sql
WITH RECURSIVE employee_tree AS (
    SELECT employee_id,
           manager_id,
           employee_name
    FROM employees
    WHERE manager_id IS NULL

    UNION ALL

    SELECT e.employee_id,
           e.manager_id,
           e.employee_name
    FROM employees e
    JOIN employee_tree t
      ON e.manager_id = t.employee_id
)
SELECT *
FROM employee_tree;
```

------------------------------------------------------------------------

# Real Business Scenario

A retail company needs:

-   Sales summary before dashboard creation
-   Customer ranking preparation
-   Employee reporting hierarchy
-   Inventory roll-up by warehouse

CTEs make these reports easier to understand and maintain.

------------------------------------------------------------------------

# Common Mistakes

1.  Forgetting the `WITH` keyword.
2.  Missing column aliases.
3.  Infinite recursion in recursive CTEs.
4.  Overusing CTEs for very simple queries.
5.  Poor formatting of multiple CTE blocks.

------------------------------------------------------------------------

# Best Practices

-   Give CTEs meaningful names.
-   Keep each CTE focused on one task.
-   Format each CTE clearly.
-   Test each logical step separately.
-   Use recursive CTEs only when needed.

------------------------------------------------------------------------

# Interview Corner

1.  What is a CTE?
2.  Why use a CTE instead of a subquery?
3.  What is the `WITH` clause?
4.  What is a recursive CTE?
5.  Give a business use case for recursion.
6.  Can multiple CTEs be chained?
7.  Are CTEs permanent?
8.  CTE vs View?
9.  CTE vs Temporary Table?
10. Performance considerations of CTEs?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Create a CTE for customers.
2.  Create a CTE for products.
3.  Display all rows from a CTE.
4.  Create a CTE using payments.
5.  Count orders using a CTE.
6.  Sum sales using a CTE.
7.  Average price using a CTE.
8.  Products above average price.
9.  Customers with more than 5 orders.
10. Top categories by product count.

## Medium (11--20)

11. Two chained CTEs.
12. Sales by city.
13. Revenue by category.
14. Employee salary summary.
15. Inventory summary.
16. Product ranking preparation.
17. Monthly sales summary.
18. Customer revenue report.
19. Warehouse stock summary.
20. Department salary report.

## Business (21--25)

21. Top customers report.
22. Daily sales report.
23. Category performance.
24. Inventory dashboard dataset.
25. Executive revenue summary.

## Interview (26--30)

26. CTE vs Subquery.
27. Recursive CTE use case.
28. CTE vs View.
29. Multiple CTEs.
30. ETL use of CTEs.

------------------------------------------------------------------------

# Mini Project

Build a reporting query using multiple CTEs to prepare:

-   Customer revenue
-   Product sales
-   Category totals
-   Top customers
-   Warehouse inventory summary

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   WITH
-   CTE
-   Recursive CTE
-   UNION ALL
-   Hierarchy

------------------------------------------------------------------------

# Cheat Sheet

``` sql
WITH sales AS (
SELECT customer_id,
       SUM(amount) revenue
FROM payments
GROUP BY customer_id
)
SELECT *
FROM sales;
```

------------------------------------------------------------------------

# Tomorrow (Day 09)

-   ROW_NUMBER()
-   RANK()
-   DENSE_RANK()
-   Window Functions

------------------------------------------------------------------------

# Data Engineer Insight

CTEs are widely used in production ETL pipelines because they make
complex transformations easier to read, maintain, and review. Modern SQL
platforms such as PostgreSQL, Azure SQL, Snowflake, BigQuery, Databricks
SQL, and Synapse all support CTEs.
