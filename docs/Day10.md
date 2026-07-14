# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 10 -- LEAD(), LAG(), FIRST_VALUE(), LAST_VALUE(), Running Totals & Moving Averages

> **Difficulty:** ⭐⭐⭐⭐☆\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

-   Understand advanced window functions
-   Use `LEAD()` and `LAG()`
-   Use `FIRST_VALUE()` and `LAST_VALUE()`
-   Calculate running totals
-   Calculate moving averages
-   Perform trend analysis

------------------------------------------------------------------------

# Why This Matters

Businesses compare today's performance with yesterday, last month, or
last year.

Window functions help answer questions without writing complex self
joins.

------------------------------------------------------------------------

# LEAD()

Returns a value from the next row.

``` sql
SELECT order_date,
       amount,
       LEAD(amount) OVER(ORDER BY order_date) AS next_amount
FROM payments;
```

------------------------------------------------------------------------

# LAG()

Returns a value from the previous row.

``` sql
SELECT order_date,
       amount,
       LAG(amount) OVER(ORDER BY order_date) AS previous_amount
FROM payments;
```

------------------------------------------------------------------------

# FIRST_VALUE()

Returns the first value in the window.

``` sql
SELECT product_name,
       FIRST_VALUE(price)
OVER(ORDER BY price DESC)
FROM products;
```

------------------------------------------------------------------------

# LAST_VALUE()

Returns the last value in the window.

``` sql
SELECT product_name,
       LAST_VALUE(price)
OVER(
ORDER BY price
ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING
)
FROM products;
```

------------------------------------------------------------------------

# Running Total

``` sql
SELECT order_date,
       amount,
       SUM(amount)
OVER(
ORDER BY order_date
) AS running_total
FROM payments;
```

------------------------------------------------------------------------

# Moving Average

``` sql
SELECT order_date,
       amount,
AVG(amount)
OVER(
ORDER BY order_date
ROWS BETWEEN 2 PRECEDING AND CURRENT ROW
) AS moving_avg
FROM payments;
```

------------------------------------------------------------------------

# Real Business Scenario

Create reports for:

-   Daily revenue trend
-   Month-over-month sales
-   Previous order comparison
-   Running revenue
-   Moving average of daily sales
-   First and latest sales value

------------------------------------------------------------------------

# Common Mistakes

1.  Forgetting ORDER BY in window functions.
2.  Using LAST_VALUE without a frame clause.
3.  Confusing LEAD and LAG.
4.  Ignoring NULL values.
5.  Using window functions where GROUP BY is more appropriate.

------------------------------------------------------------------------

# Best Practices

-   Always specify ORDER BY.
-   Understand the window frame.
-   Use aliases.
-   Test with small datasets.
-   Format analytical queries clearly.

------------------------------------------------------------------------

# Interview Corner

1.  LEAD vs LAG?
2.  Running total use case?
3.  Moving average use case?
4.  FIRST_VALUE vs LAST_VALUE?
5.  Why is ORDER BY required?
6.  What is a window frame?
7.  Business use of LEAD?
8.  Trend analysis example?
9.  How are running totals calculated?
10. Data Engineering use case?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Previous payment.
2.  Next payment.
3.  Running sales total.
4.  Running inventory quantity.
5.  First product price.
6.  Last order amount.
7.  Running customer count.
8.  Moving average price.
9.  Running warehouse stock.
10. Previous employee salary.

## Medium (11--20)

11. Month-over-month revenue.
12. Previous order comparison.
13. Category running total.
14. Product moving average.
15. Revenue trend.
16. Customer purchase trend.
17. Store sales trend.
18. Inventory trend.
19. Payment comparison.
20. Department salary trend.

## Business (21--25)

21. Executive revenue dashboard.
22. Sales trend report.
23. Customer growth analysis.
24. Inventory movement report.
25. Product performance trend.

## Interview (26--30)

26. LEAD vs LAG.
27. Running total explanation.
28. Moving average calculation.
29. Window frame purpose.
30. Business analytics use case.

------------------------------------------------------------------------

# Mini Project

Prepare an analytics dataset with:

-   Daily sales
-   Running revenue
-   Previous day's revenue
-   Next day's forecast value
-   3-day moving average

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   LEAD
-   LAG
-   FIRST_VALUE
-   LAST_VALUE
-   Running Total
-   Moving Average

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT amount,
LAG(amount) OVER(ORDER BY order_date)
FROM payments;

SELECT amount,
LEAD(amount) OVER(ORDER BY order_date)
FROM payments;

SELECT order_date,
SUM(amount) OVER(ORDER BY order_date)
FROM payments;
```

------------------------------------------------------------------------

# Tomorrow (Day 11)

-   CASE
-   COALESCE
-   NULLIF
-   CAST
-   Advanced Date & String Functions

------------------------------------------------------------------------

# Data Engineer Insight

LEAD, LAG, running totals, and moving averages are widely used in KPI
dashboards, anomaly detection, forecasting, customer behavior analysis,
and financial reporting across PostgreSQL, Snowflake, BigQuery, Azure
SQL, Synapse, Redshift, and Databricks SQL.
