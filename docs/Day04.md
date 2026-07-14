# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 04 -- Aggregate Functions, GROUP BY & HAVING

> **Difficulty:** ⭐⭐☆☆☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

By the end of today you will be able to:

-   Use aggregate functions
-   Apply COUNT, SUM, AVG, MIN and MAX
-   Group records using GROUP BY
-   Filter grouped results using HAVING
-   Build basic business reports

------------------------------------------------------------------------

# Why This Matters

Companies rarely want individual records. They usually ask:

-   Total sales
-   Average order value
-   Number of customers
-   Highest product price
-   Sales by category

Aggregate functions answer these questions.

------------------------------------------------------------------------

# Aggregate Functions

## COUNT()

Counts rows.

``` sql
SELECT COUNT(*)
FROM customers;
```

## SUM()

Adds numeric values.

``` sql
SELECT SUM(amount)
FROM payments;
```

## AVG()

Calculates averages.

``` sql
SELECT AVG(price)
FROM products;
```

## MIN()

Returns the smallest value.

``` sql
SELECT MIN(price)
FROM products;
```

## MAX()

Returns the largest value.

``` sql
SELECT MAX(price)
FROM products;
```

------------------------------------------------------------------------

# GROUP BY

Groups rows before aggregation.

``` sql
SELECT category,
       COUNT(*) AS total_products
FROM products
GROUP BY category;
```

Use GROUP BY whenever non-aggregated columns appear with aggregate
functions.

------------------------------------------------------------------------

# HAVING

Filters grouped results.

``` sql
SELECT category,
       COUNT(*) AS total_products
FROM products
GROUP BY category
HAVING COUNT(*) > 10;
```

------------------------------------------------------------------------

# WHERE vs HAVING

  WHERE                          HAVING
  ------------------------------ -------------------------------
  Filters rows before grouping   Filters groups after grouping
  Used with individual records   Used with aggregate results

------------------------------------------------------------------------

# Real Business Scenario

Management asks for:

-   Total sales by store
-   Average salary by department
-   Highest priced product in each category
-   Categories with more than 100 products
-   Customers with more than 5 orders

These reports use GROUP BY and HAVING.

------------------------------------------------------------------------

# Common Mistakes

1.  Forgetting GROUP BY.
2.  Using WHERE instead of HAVING.
3.  Mixing aggregated and non-aggregated columns.
4.  Counting the wrong column.
5.  Ignoring NULL values in aggregates.

------------------------------------------------------------------------

# Best Practices

-   Use aliases for calculated columns.
-   Filter rows with WHERE before GROUP BY.
-   Use HAVING only for aggregate conditions.
-   Format queries clearly.
-   Name reports meaningfully.

------------------------------------------------------------------------

# Interview Corner

1.  What is an aggregate function?
2.  COUNT(\*) vs COUNT(column)?
3.  SUM vs AVG?
4.  MIN vs MAX?
5.  Why GROUP BY?
6.  WHERE vs HAVING?
7.  Can HAVING be used without GROUP BY?
8.  Why aliases?
9.  When are aggregates ignored?
10. Give a business example of GROUP BY.

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Count customers.
2.  Count products.
3.  Count orders.
4.  Sum payment amounts.
5.  Find average product price.
6.  Find highest salary.
7.  Find lowest price.
8.  Count suppliers.
9.  Count stores.
10. Sum inventory quantity.

## Medium (11--20)

11. Products by category.
12. Employees by department.
13. Orders by status.
14. Customers by city.
15. Average salary by department.
16. Maximum price by category.
17. Minimum stock by warehouse.
18. Total payments by method.
19. Orders by store.
20. Average order amount by city.

## Business (21--25)

21. Sales by store.
22. Revenue by category.
23. Customers by country.
24. Departments with average salary above ₹60,000.
25. Categories with more than 50 products.

## Interview (26--30)

26. Explain GROUP BY.
27. WHERE vs HAVING.
28. COUNT(\*) vs COUNT(column).
29. AVG with NULL values.
30. Business use of aggregate functions.

------------------------------------------------------------------------

# Mini Project

Create reports for:

-   Revenue by store
-   Products by category
-   Employees by department
-   Average product price by category
-   Categories with more than 20 products

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   COUNT
-   SUM
-   AVG
-   MIN
-   MAX
-   GROUP BY
-   HAVING

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT COUNT(*) FROM customers;

SELECT SUM(amount) FROM payments;

SELECT AVG(price) FROM products;

SELECT category, COUNT(*)
FROM products
GROUP BY category;

SELECT category, COUNT(*)
FROM products
GROUP BY category
HAVING COUNT(*) > 10;
```

------------------------------------------------------------------------

# Tomorrow (Day 05)

-   INNER JOIN
-   LEFT JOIN
-   RIGHT JOIN
-   FULL OUTER JOIN
-   CROSS JOIN
-   SELF JOIN

------------------------------------------------------------------------

# Data Engineer Insight

Aggregation is the foundation of reporting and analytics. Dashboards in
Power BI, Tableau, Looker, Databricks SQL and Azure Synapse depend
heavily on aggregate queries and GROUP BY operations.
