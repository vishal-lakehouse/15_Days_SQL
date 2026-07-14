# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 05 -- SQL Joins

> **Difficulty:** ⭐⭐⭐☆☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

By the end of today you will be able to:

-   Understand why joins are used
-   Use INNER JOIN
-   Use LEFT JOIN
-   Use RIGHT JOIN
-   Use FULL OUTER JOIN
-   Use CROSS JOIN
-   Use SELF JOIN
-   Read relationships between tables

------------------------------------------------------------------------

# Why Joins Matter

In real databases, information is stored in multiple tables.

Example:

-   customers
-   orders
-   order_items
-   products

To answer business questions, these tables must be joined together.

------------------------------------------------------------------------

# Database Relationships

``` text
Customers
    │
    │ customer_id
    ▼
Orders
    │
    │ order_id
    ▼
Order_Items
    │
    │ product_id
    ▼
Products
```

------------------------------------------------------------------------

# INNER JOIN

Returns only matching records.

``` sql
SELECT c.customer_name,
       o.order_id
FROM customers c
INNER JOIN orders o
ON c.customer_id = o.customer_id;
```

Use when you need records that exist in both tables.

------------------------------------------------------------------------

# LEFT JOIN

Returns all rows from the left table and matching rows from the right
table.

``` sql
SELECT c.customer_name,
       o.order_id
FROM customers c
LEFT JOIN orders o
ON c.customer_id=o.customer_id;
```

Useful for finding customers who never placed orders.

------------------------------------------------------------------------

# RIGHT JOIN

Returns all rows from the right table and matching rows from the left.

``` sql
SELECT c.customer_name,
       o.order_id
FROM customers c
RIGHT JOIN orders o
ON c.customer_id=o.customer_id;
```

------------------------------------------------------------------------

# FULL OUTER JOIN

Returns all matching and non-matching rows from both tables.

``` sql
SELECT *
FROM customers c
FULL OUTER JOIN orders o
ON c.customer_id=o.customer_id;
```

------------------------------------------------------------------------

# CROSS JOIN

Returns every possible combination.

``` sql
SELECT *
FROM stores
CROSS JOIN products;
```

Use carefully---this can create huge result sets.

------------------------------------------------------------------------

# SELF JOIN

Joins a table to itself.

``` sql
SELECT e.employee_name,
       m.employee_name AS manager_name
FROM employees e
LEFT JOIN employees m
ON e.manager_id=m.employee_id;
```

Useful for organizational hierarchies.

------------------------------------------------------------------------

# Join Summary

  Join         Returns
  ------------ ---------------------------
  INNER        Matching rows only
  LEFT         All left + matching right
  RIGHT        All right + matching left
  FULL OUTER   All rows from both
  CROSS        Cartesian product
  SELF         Table joined with itself

------------------------------------------------------------------------

# Real Business Scenario

Retail managers request:

-   Customer name with order details.
-   Product with category.
-   Employees with managers.
-   Customers without orders.
-   Stores and inventory.

All require joins.

------------------------------------------------------------------------

# Common Mistakes

1.  Forgetting the ON condition.
2.  Joining on wrong columns.
3.  Using CROSS JOIN unintentionally.
4.  Selecting duplicate column names.
5.  Not using table aliases.

------------------------------------------------------------------------

# Best Practices

-   Always use aliases.
-   Join using primary and foreign keys.
-   Select only required columns.
-   Format joins clearly.
-   Verify row counts after joins.

------------------------------------------------------------------------

# Interview Corner

1.  What is a JOIN?
2.  INNER vs LEFT JOIN?
3.  LEFT vs RIGHT JOIN?
4.  FULL OUTER JOIN use case?
5.  CROSS JOIN risk?
6.  SELF JOIN use case?
7.  Why use aliases?
8.  What are PK and FK?
9.  What happens if ON is missing?
10. Which join finds missing records?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Join customers and orders.
2.  Join products and categories.
3.  Join employees and departments.
4.  Join orders and payments.
5.  Join products and suppliers.
6.  Join stores and inventory.
7.  Join warehouses and inventory.
8.  Join orders and customers.
9.  Join order_items and products.
10. Join returns and orders.

## Medium (11--20)

11. Customers without orders.
12. Products without suppliers.
13. Orders without payments.
14. Employees with departments.
15. Products with categories.
16. Inventory by warehouse.
17. Supplier products.
18. Store orders.
19. Customer payment report.
20. Employee-manager report.

## Business (21--25)

21. Sales report by customer.
22. Product category report.
23. Inventory availability report.
24. Payment reconciliation.
25. Customer order summary.

## Interview (26--30)

26. INNER vs LEFT JOIN.
27. LEFT JOIN vs FULL OUTER JOIN.
28. Explain CROSS JOIN.
29. Explain SELF JOIN.
30. Why are joins essential in Data Engineering?

------------------------------------------------------------------------

# Mini Project

Create reports for:

-   Customer order history
-   Product category mapping
-   Store inventory
-   Employee-manager hierarchy
-   Customers who never ordered

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   INNER JOIN
-   LEFT JOIN
-   RIGHT JOIN
-   FULL OUTER JOIN
-   CROSS JOIN
-   SELF JOIN
-   ON

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT *
FROM customers c
INNER JOIN orders o
ON c.customer_id=o.customer_id;

SELECT *
FROM customers c
LEFT JOIN orders o
ON c.customer_id=o.customer_id;

SELECT *
FROM employees e
LEFT JOIN employees m
ON e.manager_id=m.employee_id;
```

------------------------------------------------------------------------

# Tomorrow (Day 06)

-   Multi-table joins
-   Complex reporting
-   Join optimization
-   Real business reports

------------------------------------------------------------------------

# Data Engineer Insight

Joins are used in almost every ETL pipeline. Data Engineers combine
transactional, customer, product, and inventory data to create
analytics-ready datasets for reporting and machine learning.
