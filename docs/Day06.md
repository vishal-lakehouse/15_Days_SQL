# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 06 -- Multi-Table Joins & Business Reporting

> **Difficulty:** ⭐⭐⭐☆☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

By the end of today you will be able to:

-   Join three or more tables
-   Build business reports from multiple tables
-   Understand join order
-   Use aliases effectively
-   Read SQL used in real Data Engineering projects

------------------------------------------------------------------------

# Why This Matters

Real business data is rarely stored in one table.

A sales report may require data from:

-   customers
-   orders
-   order_items
-   products
-   categories
-   payments

Data Engineers combine these tables to create analytics-ready datasets.

------------------------------------------------------------------------

# Multi-Table Join Example

``` sql
SELECT
    c.customer_name,
    o.order_id,
    p.product_name,
    oi.quantity
FROM customers c
JOIN orders o
  ON c.customer_id = o.customer_id
JOIN order_items oi
  ON o.order_id = oi.order_id
JOIN products p
  ON oi.product_id = p.product_id;
```

------------------------------------------------------------------------

# Join Flow

``` text
Customers
    │
Orders
    │
Order_Items
    │
Products
```

Always join using the relationship keys (Primary Key ↔ Foreign Key).

------------------------------------------------------------------------

# Business Reports

## Customer Order Report

Customer Name \| Order ID \| Order Date

## Product Sales Report

Product \| Quantity \| Revenue

## Category Performance

Category \| Total Products \| Total Sales

## Payment Report

Customer \| Order \| Payment Method \| Amount

------------------------------------------------------------------------

# Choosing the Correct Join

  Requirement             Join
  ----------------------- -----------------
  Matching records only   INNER JOIN
  Keep all customers      LEFT JOIN
  Keep all orders         RIGHT JOIN
  Show everything         FULL OUTER JOIN

------------------------------------------------------------------------

# Common Mistakes

1.  Joining tables in the wrong order.
2.  Using incorrect join keys.
3.  Selecting unnecessary columns.
4.  Forgetting table aliases.
5.  Creating duplicate rows due to incorrect joins.

------------------------------------------------------------------------

# Best Practices

-   Understand table relationships first.
-   Use meaningful aliases.
-   Select only required columns.
-   Verify row counts after joins.
-   Format joins consistently.

------------------------------------------------------------------------

# Interview Corner

1.  Why are multi-table joins needed?
2.  How do you identify join keys?
3.  What causes duplicate rows?
4.  Why use aliases?
5.  How do you debug joins?
6.  INNER vs LEFT in reporting?
7.  What is referential integrity?
8.  Why avoid SELECT \*?
9.  How many tables can SQL join?
10. Explain a real business report.

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Customer with order.
2.  Product with category.
3.  Employee with department.
4.  Order with payment.
5.  Product with supplier.
6.  Inventory with warehouse.
7.  Customer with city.
8.  Store with manager.
9.  Product with inventory.
10. Order with customer.

## Medium (11--20)

11. Customer + Order + Payment.
12. Order + Product + Category.
13. Warehouse + Inventory + Product.
14. Employee + Department + Store.
15. Supplier + Product + Category.
16. Customer + Order + Order Items.
17. Store + Orders + Payments.
18. Customer + Payment + Order.
19. Product + Supplier + Inventory.
20. Category + Product + Sales.

## Business (21--25)

21. Sales report by customer.
22. Revenue by category.
23. Inventory availability report.
24. Store sales summary.
25. Customer purchase history.

## Interview (26--30)

26. Explain multi-table joins.
27. Why aliases matter?
28. Duplicate rows after joins?
29. How do PK/FK help joins?
30. Real ETL join example.

------------------------------------------------------------------------

# Mini Project

Create a sales dashboard dataset containing:

-   Customer Name
-   Order ID
-   Product Name
-   Quantity
-   Payment Amount
-   Category

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   Multi-table JOIN
-   PK/FK
-   Aliases
-   Business Reports
-   Referential Integrity

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT
    c.customer_name,
    o.order_id,
    p.product_name
FROM customers c
JOIN orders o
ON c.customer_id=o.customer_id
JOIN order_items oi
ON o.order_id=oi.order_id
JOIN products p
ON oi.product_id=p.product_id;
```

------------------------------------------------------------------------

# Tomorrow (Day 07)

-   Subqueries
-   Correlated Subqueries
-   EXISTS
-   IN
-   ANY
-   ALL

------------------------------------------------------------------------

# Data Engineer Insight

Multi-table joins are the backbone of ETL pipelines. Data Engineers
combine transactional, master, and reference tables to create trusted
datasets for dashboards, machine learning, and business intelligence.
