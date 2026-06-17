# Olist Customer Intelligence Project

## Project Objective

Build an end-to-end Customer Intelligence Analytics Project using SQL, Python, Pandas, NumPy, Excel and Power BI.

---

# Day 1 - Project Setup & Data Understanding

## Activities Completed

* Downloaded Olist E-Commerce Dataset from Kaggle.
* Explored the dataset and selected 6 core tables:
  * customers
  * orders
  * order_items
  * order_payments
  * products
  * order_reviews
* Created project folder structure.
* Created MySQL database: `olist`.
* Analyzed the customers dataset.
* Created the customers table.
* Imported customer data into MySQL.

## Key Learnings

### Why Tables Are Separated

* To reduce data duplication.
* To improve consistency.
* To create relationships between entities.

### Primary Key

Learned that a Primary Key:

* Must be unique.
* Cannot be NULL.
* Identifies each record uniquely.

Example:

* customer_id

---

# Day 2 - Orders Table & ETL Concepts

## Activities Completed

* Analyzed the orders dataset.
* Created the orders table.
* Defined relationships between customers and orders.
* Learned Primary Key and Foreign Key concepts.
* Learned One-to-Many relationships.
* Learned INNER JOIN and LEFT JOIN concepts.
* Attempted to import orders data.
* Encountered datetime import errors.
* Investigated the root cause.
* Identified missing delivery date values in the dataset.
* Dropped the incomplete orders table import.
* Recreated the orders table correctly.
* Created a staging table: `orders_raw`.

## Key Learnings

### Foreign Key

Used to create relationships between tables.

Example:

orders.customer_id → customers.customer_id

### One-to-Many Relationship

One customer can place multiple orders.

### ETL Process

CSV
↓
orders_raw
↓
Data Cleaning
↓
orders

### Real-World Data Challenges

* Missing values.
* Invalid datetime formats.
* Partial imports.
* Data cleaning before analysis.

---

# Current Status

## Completed

* [X] Database Created
* [X] Customers Table Created
* [X] Customers Data Imported
* [X] Orders Table Created
* [X] Orders Raw Table Created

## In Progress

* [ ] Import orders data into orders_raw
* [ ] Clean datetime columns
* [ ] Load clean data into orders

## Upcoming

* [ ] order_items table
* [ ] payments table
* [ ] products table
* [ ] reviews table
* [ ] SQL analysis
* [ ] Python analysis
* [ ] Power BI dashboard
