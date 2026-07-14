# SQL Mastery for Data Engineering -- 15-Day Intensive Bootcamp

# Day 12 -- INSERT, UPDATE, DELETE, Transactions & Views

> **Difficulty:** ⭐⭐⭐⭐⭐\
> **Estimated Study Time:** 2 Hours

------------------------------------------------------------------------

# Learning Objectives

-   Insert new records with `INSERT`
-   Modify data using `UPDATE`
-   Remove data using `DELETE`
-   Understand transactions
-   Use `COMMIT` and `ROLLBACK`
-   Create and use SQL Views

------------------------------------------------------------------------

# Why This Matters

Data Engineers don't only read data---they also load, correct, and
maintain it. Safe data manipulation is essential in ETL pipelines.

------------------------------------------------------------------------

# INSERT

Add new rows.

``` sql
INSERT INTO customers
(customer_id, customer_name, city)
VALUES
(1001,'Rahul Sharma','Bangalore');
```

------------------------------------------------------------------------

# UPDATE

Modify existing records.

``` sql
UPDATE customers
SET city='Hyderabad'
WHERE customer_id=1001;
```

> Always use a `WHERE` clause unless you intend to update every row.

------------------------------------------------------------------------

# DELETE

Remove records.

``` sql
DELETE FROM customers
WHERE customer_id=1001;
```

------------------------------------------------------------------------

# Transactions

A transaction groups multiple SQL statements into a single logical unit.

Properties (ACID):

-   Atomicity
-   Consistency
-   Isolation
-   Durability

------------------------------------------------------------------------

# COMMIT

Permanently saves changes.

``` sql
BEGIN;

UPDATE inventory
SET stock_quantity = stock_quantity - 5
WHERE product_id=101;

COMMIT;
```

------------------------------------------------------------------------

# ROLLBACK

Undo changes before committing.

``` sql
BEGIN;

DELETE FROM orders
WHERE order_id=5001;

ROLLBACK;
```

------------------------------------------------------------------------

# Views

A View stores a SQL query as a virtual table.

``` sql
CREATE VIEW vw_active_customers AS
SELECT customer_id,
       customer_name,
       city
FROM customers
WHERE status='Active';
```

Query the view:

``` sql
SELECT *
FROM vw_active_customers;
```

------------------------------------------------------------------------

# Real Business Scenario

A retail company needs to:

-   Load new customers
-   Correct product prices
-   Remove duplicate records
-   Roll back accidental updates
-   Provide analysts with a reusable active customer view

------------------------------------------------------------------------

# Common Mistakes

1.  Updating without `WHERE`.
2.  Deleting all rows accidentally.
3.  Forgetting `COMMIT`.
4.  Committing incorrect changes.
5.  Assuming a View stores physical data.

------------------------------------------------------------------------

# Best Practices

-   Test `UPDATE` using `SELECT` first.
-   Use transactions for critical operations.
-   Back up important data.
-   Name views clearly.
-   Review affected row counts.

------------------------------------------------------------------------

# Interview Corner

1.  INSERT vs COPY?
2.  UPDATE vs MERGE?
3.  DELETE vs TRUNCATE?
4.  What is a transaction?
5.  Explain ACID.
6.  COMMIT vs ROLLBACK?
7.  What is a View?
8.  Why use Views?
9.  Can Views be updated?
10. Data Engineering use case?

------------------------------------------------------------------------

# Practice Questions

## Easy (1--10)

1.  Insert one customer.
2.  Insert one product.
3.  Update customer city.
4.  Update product price.
5.  Delete one supplier.
6.  Delete one order.
7.  Create a transaction.
8.  Commit a transaction.
9.  Roll back a transaction.
10. Create a simple view.

## Medium (11--20)

11. Insert multiple products.
12. Update inventory.
13. Update employee salary.
14. Delete cancelled orders.
15. Create active products view.
16. Customer summary view.
17. Payment report view.
18. Product category view.
19. Roll back failed update.
20. Commit successful inventory update.

## Business (21--25)

21. New customer onboarding.
22. Product price correction.
23. Inventory adjustment.
24. Customer reporting view.
25. Failed transaction recovery.

## Interview (26--30)

26. ACID properties.
27. DELETE vs TRUNCATE.
28. COMMIT vs ROLLBACK.
29. Why use Views?
30. Safe UPDATE strategy.

------------------------------------------------------------------------

# Mini Project

Write SQL to:

-   Insert new customers.
-   Update inventory.
-   Delete invalid records.
-   Create reusable reporting views.
-   Use transactions safely.

(No solutions.)

------------------------------------------------------------------------

# Revision Notes

Keywords:

-   INSERT
-   UPDATE
-   DELETE
-   BEGIN
-   COMMIT
-   ROLLBACK
-   VIEW
-   ACID

------------------------------------------------------------------------

# Cheat Sheet

``` sql
INSERT INTO customers(customer_id,customer_name)
VALUES(1,'Amit');

UPDATE customers
SET city='Delhi'
WHERE customer_id=1;

DELETE FROM customers
WHERE customer_id=1;

BEGIN;
UPDATE products SET price=price*1.05;
ROLLBACK;

CREATE VIEW vw_products AS
SELECT * FROM products;
```

------------------------------------------------------------------------

# Tomorrow (Day 13)

-   Constraints
-   Primary Key
-   Foreign Key
-   UNIQUE
-   CHECK
-   Indexes
-   EXPLAIN
-   Query Optimization

------------------------------------------------------------------------

# Data Engineer Insight

Data modification and transaction management are fundamental to reliable
ETL pipelines. Understanding ACID, transactions, and Views helps ensure
data quality and consistency across PostgreSQL, Azure SQL, Snowflake,
Databricks SQL, BigQuery, Redshift, and Synapse.
