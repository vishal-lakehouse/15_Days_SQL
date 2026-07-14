# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 13 -- Constraints, Indexes, EXPLAIN & Query Optimization

> **Difficulty:** ⭐⭐⭐⭐⭐\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

-   Understand database constraints
-   Use PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK and NOT NULL
-   Understand indexes
-   Read execution plans with `EXPLAIN`
-   Learn basic query optimization techniques

------------------------------------------------------------------------

# Why This Matters

Data Engineers build reliable and fast data pipelines. Constraints
protect data quality, while indexes and query optimization improve
performance on large datasets.

------------------------------------------------------------------------

# PRIMARY KEY

Uniquely identifies each row.

``` sql
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    customer_name VARCHAR(100)
);
```

------------------------------------------------------------------------

# FOREIGN KEY

Maintains relationships between tables.

``` sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT REFERENCES customers(customer_id)
);
```

------------------------------------------------------------------------

# UNIQUE

Prevents duplicate values.

``` sql
email VARCHAR(255) UNIQUE
```

------------------------------------------------------------------------

# NOT NULL

Ensures a column always has a value.

``` sql
customer_name VARCHAR(100) NOT NULL
```

------------------------------------------------------------------------

# CHECK

Restricts allowed values.

``` sql
CHECK (price > 0)
```

------------------------------------------------------------------------

# Indexes

Indexes speed up data retrieval.

``` sql
CREATE INDEX idx_orders_customer
ON orders(customer_id);
```

Use indexes on frequently searched or joined columns.

------------------------------------------------------------------------

# EXPLAIN

Shows how PostgreSQL executes a query.

``` sql
EXPLAIN
SELECT *
FROM orders
WHERE customer_id = 101;
```

Look for sequential scans, index scans, estimated cost, and row counts.

------------------------------------------------------------------------

# Query Optimization Tips

-   Select only required columns.
-   Filter early using WHERE.
-   Index frequently filtered columns.
-   Avoid unnecessary `SELECT *`.
-   Review execution plans with `EXPLAIN`.

------------------------------------------------------------------------

# Real Business Scenario

An e-commerce company has 100 million orders.

Tasks:

-   Prevent duplicate customer emails.
-   Ensure every order references a valid customer.
-   Speed up customer-order lookups.
-   Investigate slow reports using `EXPLAIN`.

------------------------------------------------------------------------

# Common Mistakes

1.  Missing primary keys.
2.  Creating too many indexes.
3.  Forgetting foreign keys.
4.  Using `SELECT *` on huge tables.
5.  Ignoring execution plans.

------------------------------------------------------------------------

# Best Practices

-   Design constraints early.
-   Index only where beneficial.
-   Analyze slow queries.
-   Keep table relationships consistent.
-   Test performance after changes.

------------------------------------------------------------------------

# Interview Corner

1.  What is a PRIMARY KEY?
2.  PRIMARY KEY vs UNIQUE?
3.  Why use FOREIGN KEY?
4.  What is an index?
5.  Clustered vs non-clustered index (concept)?
6.  What does EXPLAIN do?
7.  Why avoid too many indexes?
8.  How do constraints improve data quality?
9.  How would you optimize a slow query?
10. Give an indexing use case.

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Create a table with PRIMARY KEY.
2.  Add NOT NULL.
3.  Add UNIQUE email.
4.  Add CHECK price \> 0.
5.  Create a FOREIGN KEY.
6.  Create an index.
7.  Run EXPLAIN.
8.  Find indexed columns.
9.  Explain NOT NULL.
10. Explain UNIQUE.

## Medium (11--20)

11. Design customers table.
12. Design orders table.
13. Add constraints to products.
14. Index order_date.
15. Index customer_id.
16. Explain a join query.
17. Optimize a filter query.
18. Compare indexed vs non-indexed search.
19. Prevent duplicate products.
20. Validate inventory values.

## Business (21--25)

21. Customer master design.
22. Sales table optimization.
23. Inventory integrity.
24. Payment validation.
25. Reporting query tuning.

## Interview (26--30)

26. PRIMARY KEY vs FOREIGN KEY.
27. UNIQUE vs PRIMARY KEY.
28. Index advantages and disadvantages.
29. EXPLAIN output interpretation.
30. Steps to optimize a slow SQL query.

------------------------------------------------------------------------

# Mini Project

Design a retail schema with appropriate constraints and indexes, then
identify two reporting queries that would benefit from indexing.

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   PRIMARY KEY
-   FOREIGN KEY
-   UNIQUE
-   NOT NULL
-   CHECK
-   INDEX
-   EXPLAIN
-   Query Optimization

------------------------------------------------------------------------

# Cheat Sheet

``` sql
CREATE INDEX idx_orders_customer
ON orders(customer_id);

EXPLAIN
SELECT *
FROM orders
WHERE customer_id = 101;
```

------------------------------------------------------------------------

# Tomorrow (Day 14)

-   Real-world SQL reporting
-   Retail analytics
-   Sales KPIs
-   Inventory analytics
-   Customer analytics

------------------------------------------------------------------------

# Data Engineer Insight

Constraints ensure trustworthy data, while indexes and execution-plan
analysis are critical for scaling ETL pipelines and analytics workloads
in PostgreSQL, Azure SQL, Snowflake, BigQuery, Databricks SQL, Amazon
Redshift, and Azure Synapse.
