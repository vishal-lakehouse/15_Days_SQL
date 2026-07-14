# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 09 -- Window Functions: ROW_NUMBER(), RANK() & DENSE_RANK()

> **Difficulty:** ⭐⭐⭐⭐☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

-   Understand Window Functions
-   Learn the `OVER()` clause
-   Use `ROW_NUMBER()`
-   Use `RANK()`
-   Use `DENSE_RANK()`
-   Use `PARTITION BY`
-   Solve ranking problems in business reports

------------------------------------------------------------------------

# Why Window Functions?

Aggregate functions summarize data.

Window functions let you calculate values **without collapsing rows**.

They are widely used in reporting, analytics, leaderboards, and ETL.

------------------------------------------------------------------------

# OVER() Clause

The `OVER()` clause defines the window for calculation.

``` sql
SELECT order_id,
       amount,
       ROW_NUMBER() OVER(ORDER BY amount DESC)
FROM payments;
```

------------------------------------------------------------------------

# ROW_NUMBER()

Assigns a unique sequential number.

``` sql
SELECT customer_id,
       amount,
       ROW_NUMBER() OVER(ORDER BY amount DESC) AS row_num
FROM payments;
```

Use when every row needs a unique rank.

------------------------------------------------------------------------

# RANK()

Equal values receive the same rank.

The next rank is skipped.

``` sql
SELECT product_name,
       price,
       RANK() OVER(ORDER BY price DESC) AS price_rank
FROM products;
```

------------------------------------------------------------------------

# DENSE_RANK()

Equal values receive the same rank.

No rank numbers are skipped.

``` sql
SELECT product_name,
       price,
       DENSE_RANK() OVER(ORDER BY price DESC) AS dense_rank
FROM products;
```

------------------------------------------------------------------------

# PARTITION BY

Restart ranking for each group.

``` sql
SELECT category,
       product_name,
       price,
       ROW_NUMBER() OVER(
           PARTITION BY category
           ORDER BY price DESC
       ) AS category_rank
FROM products;
```

------------------------------------------------------------------------

# ROW_NUMBER vs RANK vs DENSE_RANK

  Function     Duplicate Values   Gaps in Rank
  ------------ ------------------ --------------
  ROW_NUMBER   No                 No
  RANK         Yes                Yes
  DENSE_RANK   Yes                No

------------------------------------------------------------------------

# Real Business Scenario

Create reports for:

-   Top 5 products in each category
-   Highest-paid employee per department
-   Top customers by revenue
-   Best-selling products by store
-   Monthly revenue rankings

------------------------------------------------------------------------

# Common Mistakes

1.  Forgetting `OVER()`.
2.  Missing `ORDER BY` inside the window.
3.  Confusing `RANK()` and `DENSE_RANK()`.
4.  Using `PARTITION BY` incorrectly.
5.  Expecting window functions to reduce rows.

------------------------------------------------------------------------

# Best Practices

-   Always define `ORDER BY`.
-   Use `PARTITION BY` for grouped rankings.
-   Choose the right ranking function.
-   Use meaningful aliases.
-   Format window functions clearly.

------------------------------------------------------------------------

# Interview Corner

1.  What is a window function?
2.  What does `OVER()` do?
3.  ROW_NUMBER vs RANK?
4.  RANK vs DENSE_RANK?
5.  Why use PARTITION BY?
6.  Give a ranking use case.
7.  Can window functions replace GROUP BY?
8.  Where are they used in analytics?
9.  Performance considerations?
10. Data Engineering use cases?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Rank products by price.
2.  Assign row numbers to customers.
3.  Rank employees by salary.
4.  Dense rank products.
5.  Rank stores by sales.
6.  Number payments.
7.  Rank orders by amount.
8.  Rank suppliers.
9.  Rank warehouses by stock.
10. Rank categories by product count.

## Medium (11--20)

11. Top 3 products per category.
12. Highest-paid employee per department.
13. Top customers by city.
14. Rank monthly sales.
15. Rank stores by revenue.
16. Dense rank departments.
17. Row number by warehouse.
18. Rank products by supplier.
19. Customer revenue ranking.
20. Product ranking by category.

## Business (21--25)

21. Sales leaderboard.
22. Customer leaderboard.
23. Product performance report.
24. Store ranking dashboard.
25. Department salary ranking.

## Interview (26--30)

26. Explain OVER().
27. ROW_NUMBER vs RANK.
28. DENSE_RANK use case.
29. PARTITION BY example.
30. Window functions in ETL.

------------------------------------------------------------------------

# Mini Project

Build a dashboard dataset showing:

-   Top customers
-   Top products
-   Top stores
-   Highest-paid employees
-   Top categories

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   OVER
-   ROW_NUMBER
-   RANK
-   DENSE_RANK
-   PARTITION BY

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT product_name,
       price,
       ROW_NUMBER() OVER(ORDER BY price DESC)
FROM products;

SELECT category,
       product_name,
       RANK() OVER(
           PARTITION BY category
           ORDER BY price DESC
       )
FROM products;
```

------------------------------------------------------------------------

# Tomorrow (Day 10)

-   LEAD()
-   LAG()
-   FIRST_VALUE()
-   LAST_VALUE()
-   Running Totals
-   Moving Averages

------------------------------------------------------------------------

# Data Engineer Insight

Window functions power advanced reporting, KPI dashboards, customer
ranking, fraud detection, and trend analysis. They are heavily used in
PostgreSQL, Azure SQL, Snowflake, BigQuery, Databricks SQL, Redshift,
and Synapse.
