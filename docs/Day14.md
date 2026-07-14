# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 14 -- Real-World SQL Reporting & Retail Analytics

> **Difficulty:** ⭐⭐⭐⭐⭐\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

-   Build real business reports
-   Analyze sales KPIs
-   Perform customer analytics
-   Analyze inventory and warehouse performance
-   Create executive dashboards using SQL
-   Apply SQL in Data Engineering reporting pipelines

------------------------------------------------------------------------

# Why This Matters

Business users do not ask for SQL syntax---they ask for answers.

Typical requests include:

-   Total revenue this month
-   Top-selling products
-   Customers who generate the most revenue
-   Low-stock products
-   Best-performing stores

A Data Engineer prepares datasets that answer these questions accurately
and efficiently.

------------------------------------------------------------------------

# Key Business KPIs

-   Total Revenue
-   Total Orders
-   Average Order Value
-   Customer Lifetime Value (CLV)
-   Gross Sales
-   Net Sales
-   Inventory Turnover
-   Top Products
-   Top Stores
-   Return Rate

------------------------------------------------------------------------

# Sales Analytics

``` sql
SELECT
    DATE_TRUNC('month', order_date) AS month,
    SUM(total_amount) AS monthly_revenue
FROM orders
GROUP BY DATE_TRUNC('month', order_date)
ORDER BY month;
```

------------------------------------------------------------------------

# Top Customers

``` sql
SELECT
    c.customer_name,
    SUM(p.amount) AS total_spent
FROM customers c
JOIN orders o
  ON c.customer_id = o.customer_id
JOIN payments p
  ON o.order_id = p.order_id
GROUP BY c.customer_name
ORDER BY total_spent DESC;
```

------------------------------------------------------------------------

# Best-Selling Products

``` sql
SELECT
    p.product_name,
    SUM(oi.quantity) AS units_sold
FROM products p
JOIN order_items oi
  ON p.product_id = oi.product_id
GROUP BY p.product_name
ORDER BY units_sold DESC;
```

------------------------------------------------------------------------

# Inventory Analytics

``` sql
SELECT
    product_name,
    stock_quantity
FROM inventory
WHERE stock_quantity < 20;
```

------------------------------------------------------------------------

# Store Performance

Compare stores by revenue, orders, and customer count.

Use: - GROUP BY - SUM() - COUNT() - AVG()

------------------------------------------------------------------------

# Customer Analytics

Business Questions:

-   Who are the top customers?
-   Which customers have not ordered recently?
-   Which city generates the highest revenue?
-   What is the average order value per customer?

------------------------------------------------------------------------

# Executive Dashboard Metrics

Create datasets for:

-   Daily Sales
-   Monthly Revenue
-   Revenue by Category
-   Orders by Store
-   Top 10 Customers
-   Top 10 Products
-   Low Inventory
-   Returns by Category

------------------------------------------------------------------------

# Common Mistakes

1.  Ignoring business requirements.
2.  Returning unnecessary columns.
3.  Missing date filters.
4.  Incorrect joins causing duplicate totals.
5.  Not validating aggregated results.

------------------------------------------------------------------------

# Best Practices

-   Clarify KPI definitions.
-   Validate totals with stakeholders.
-   Filter data early.
-   Use meaningful aliases.
-   Format reports consistently.

------------------------------------------------------------------------

# Interview Corner

1.  What is a KPI?
2.  How do you calculate revenue?
3.  How would you identify top customers?
4.  Explain customer lifetime value.
5.  How do you build a sales dashboard?
6.  Which SQL features are commonly used in reporting?
7.  How do you validate business reports?
8.  Why are joins important in analytics?
9.  How would you optimize a dashboard query?
10. Describe a reporting project you have worked on.

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Total customers.
2.  Total orders.
3.  Total products.
4.  Revenue by month.
5.  Revenue by store.
6.  Revenue by city.
7.  Average order value.
8.  Top-selling product.
9.  Low inventory report.
10. Products never sold.

## Medium (11--20)

11. Monthly customer growth.
12. Revenue by category.
13. Orders by payment method.
14. Sales by warehouse.
15. Average sales per store.
16. Customer ranking.
17. Product ranking.
18. Inventory summary.
19. Returns by category.
20. Sales trend by month.

## Business (21--25)

21. CEO sales dashboard.
22. Inventory health report.
23. Customer retention report.
24. Executive KPI report.
25. Store performance report.

## Interview (26--30)

26. Design a sales dashboard.
27. Build a customer analytics report.
28. Explain revenue aggregation.
29. Optimize a reporting query.
30. SQL reporting in ETL pipelines.

------------------------------------------------------------------------

# Mini Project

Prepare an executive retail dashboard dataset containing:

-   Monthly Revenue
-   Top Customers
-   Top Products
-   Sales by Store
-   Inventory Alerts
-   Customer Growth
-   Product Categories
-   Return Summary

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   KPI
-   Revenue
-   Dashboard
-   Analytics
-   Aggregation
-   Reporting
-   Trend Analysis

------------------------------------------------------------------------

# Cheat Sheet

``` sql
SELECT DATE_TRUNC('month', order_date),
       SUM(total_amount)
FROM orders
GROUP BY DATE_TRUNC('month', order_date);

SELECT product_name,
       SUM(quantity)
FROM order_items
GROUP BY product_name;
```

------------------------------------------------------------------------

# Tomorrow (Day 15)

-   Comprehensive SQL Mock Interview
-   Advanced Business Challenges
-   End-to-End SQL Assessment
-   Final Capstone Project

------------------------------------------------------------------------

# Data Engineer Insight

Production Data Engineers spend much of their time creating reliable
datasets for Power BI, Tableau, Looker, Azure Synapse, Databricks SQL,
Snowflake, Amazon Redshift, and BigQuery. Accurate reporting, KPI
calculation, and business validation are essential skills for every Data
Engineer.
