# Olist Customer Intelligence Project

## Project Objective

Build an end-to-end Customer Intelligence Analytics Project using SQL, Python, Pandas, NumPy, Excel and Power BI.

The project focuses on transforming raw e-commerce data into business insights through data engineering, analytics, visualization and machine learning.

---

## Future Machine Learning Goals

* Customer Segmentation
* Customer Lifetime Value (CLV) Prediction
* Purchase Behavior Analysis
* Customer Retention Analysis
* Product Recommendation Insights

---

## Project Dataset

Source: Olist Brazilian E-Commerce Dataset (Kaggle)

Core Tables Selected:

* customers
* orders
* order_items
* order_payments
* products
* order_reviews

Additional Supporting Tables:

* sellers
* geolocation
* product_category_translation

---

## Tech Stack

### Database & Querying

* MySQL
* SQL

### Data Analysis

* Excel
* Python (Planned)
* Pandas (Planned)
* NumPy (Planned)

### Data Visualization

* Power BI (Planned)

### Version Control

* Git
* GitHub

### Data Engineering Concepts Applied

* ETL Pipelines
* Staging Tables
* Data Validation
* Referential Integrity
* Primary Keys
* Foreign Keys
* Composite Primary Keys

---

## Skills Demonstrated

### SQL

* Data Import
* Data Validation
* Joins
* Primary Keys
* Foreign Keys
* Composite Primary Keys

### Data Engineering

* ETL Pipelines
* Staging Tables
* Data Cleaning
* Data Quality Checks
* Referential Integrity Validation

### Version Control

* Git
* GitHub
* Repository Management

### Analytics

* Customer Intelligence
* E-Commerce Data Modeling
* Business-Oriented Data Analysis

---

# Day 1(15 June 2026) - Project Setup & Data Understanding

## Activities Completed

* Downloaded Olist E-Commerce Dataset from Kaggle.
* Explored the dataset and selected core business tables.
* Created project folder structure.
* Created MySQL database: `olist`.
* Analyzed the customers dataset.
* Created the customers table.
* Imported customer data into MySQL.

## Key Learnings

### Why Tables Are Separated

* Reduce data duplication.
* Improve consistency.
* Improve scalability.
* Create relationships between entities.

### Primary Key

A Primary Key:

* Must be unique.
* Cannot be NULL.
* Uniquely identifies each record.

Example:

* customer_id

---

# Day 2(16 June 2026) - Orders Table & ETL Concepts

## Activities Completed

* Analyzed the orders dataset.
* Created the orders table.
* Defined relationships between customers and orders.
* Learned Primary Key and Foreign Key concepts.
* Learned One-to-Many relationships.
* Learned INNER JOIN and LEFT JOIN concepts.
* Attempted to import orders data.
* Encountered datetime import issues.
* Investigated root causes.
* Identified missing delivery date values.
* Dropped incomplete imports.
* Recreated the orders table.
* Created the staging table: `orders_raw`.

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

Data Validation

↓

orders

### Real-World Data Challenges

* Missing values
* Invalid datetime formats
* Partial imports
* Data cleaning before analysis

---

# Day 3 (17 June 2026) - ETL Pipeline Development, Data Validation & GitHub Setup

## Activities Completed

### Orders Data Pipeline

* Successfully imported `olist_orders_dataset.csv` into `orders_raw`.
* Verified successful import of 99,441 records.
* Resolved datetime import issues.
* Applied staging table methodology.

### Orders Data Validation

Performed validation checks:

* Duplicate order IDs
* NULL customer IDs
* Invalid customer references
* Invalid datetime values

Results:

* Duplicate order IDs = 0
* NULL customer IDs = 0
* Invalid customer references = 0
* Invalid datetime values = 0

### Orders Table Loading

* Loaded validated data into the final `orders` table.
* Established customer-order relationships.
* Successfully loaded 99,441 orders.

---

### Order Items Data Pipeline

* Created `order_items_raw`.
* Imported 112,650 order item records.
* Designed staging schema.

### Order Items Data Validation

Performed validation checks:

* NULL order IDs
* NULL product IDs
* NULL prices
* Negative prices
* Zero prices
* Negative freight values
* Shipping date validation
* Referential integrity validation

Results:

* Invalid order references = 0
* Duplicate `(order_id, order_item_id)` combinations = 0

### Order Items Table Design

* Learned Composite Primary Keys.
* Identified `(order_id, order_item_id)` as the correct primary key.
* Created the final `order_items` table.
* Added foreign key relationship with orders.

### Order Items Loading

* Converted `shipping_limit_date` into DATETIME format.
* Successfully loaded 112,650 validated records into the final table.

---

### GitHub & Project Management

* Created GitHub repository.
* Added project documentation.
* Added Project Journal.
* Created `.gitignore`.
* Removed raw datasets from Git tracking.
* Applied repository cleanup and best practices.
* Pushed project updates to GitHub.

---

## Key Learnings

### Database Concepts

* Primary Keys
* Foreign Keys
* Composite Primary Keys
* One-to-Many Relationships
* Referential Integrity

### Data Engineering Concepts

* ETL Pipelines
* Staging Tables
* Data Validation
* Data Quality Checks
* Production Data Loading

### Git & GitHub

* Repository Initialization
* Commit Workflow
* Git Ignore Usage
* Repository Management
* Version Control Best Practices

---


# Day 4 (18 June 2026) - Products ETL, Payments ETL & Python Integration

## Activities Completed

### Products ETL Pipeline

* Created the `products_raw` staging table.
* Successfully imported **32,951** product records.
* Validated the imported dataset.
* Performed data quality checks including:
  * NULL and blank value validation
  * Duplicate `product_id` validation
  * Zero and negative value validation
* Investigated **610** products with missing category, name length, description length and photo count.
* Verified that all 610 products were referenced in `order_items`, therefore retained for analysis.
* Created the production `products` table.
* Loaded validated data into the final table.
* Successfully loaded all **32,951** products.

---

### Order Payments ETL Pipeline

* Created the `order_payments_raw` staging table.
* Successfully imported **103,886** payment records.
* Identified `(order_id, payment_sequential)` as the candidate Composite Primary Key.
* Validated that the key combination contained no duplicates.
* Performed data validation:
  * NULL and blank value validation
  * Negative value validation
  * Zero value validation
* Created the production `order_payments` table.
* Implemented:
  * Composite Primary Key
  * Foreign Key relationship with `orders`
* Successfully loaded all validated payment records into the final table.
* Verified row counts and production data.

---

### Order Reviews Investigation

* Began analysis of the `olist_order_reviews_dataset.csv` dataset.
* Designed the `order_reviews_raw` staging table.
* Attempted to import the dataset using MySQL Workbench.
* Identified an unexpected import limitation where only **279** records were imported despite the CSV containing **99,224** records.
* Investigated:
  * Primary Key constraints
  * Table design
  * CSV formatting
  * Import configuration
* Concluded that the issue originates from the MySQL Workbench Import Wizard rather than the database schema.

---

### Introduction to Pandas

To overcome the Workbench import limitation, introduced Pandas into the ETL workflow.

Concepts learned:

* Importing libraries
* Reading CSV files using `pd.read_csv()`
* Understanding DataFrames
* Displaying records using:
  * `head()`
  * `tail()`
* Inspecting datasets using:
  * `shape`
  * `info()`
  * `columns`
* Selecting single and multiple columns.
* Basic aggregation functions:
  * `mean()`
  * `max()`

---

### Python and MySQL Integration

* Installed `mysql-connector-python`.
* Established the first successful Python connection with the MySQL database.
* Executed SQL queries directly from Python.
* Retrieved query results using:
  * `cursor.execute()`
  * `fetchone()`
* Learned how Python returns SQL query results as tuples.
* Learned tuple indexing for extracting individual values.

---

## Key Learnings

### Data Engineering

* Candidate Primary Key validation before implementation.
* Business data validation in addition to technical validation.
* Importance of staging tables in ETL pipelines.
* Verification of production data after loading.

### Python & Pandas

* Reading CSV files into DataFrames.
* Understanding DataFrame structure.
* Inspecting datasets.
* Selecting columns.
* Performing basic statistical analysis.
* Integrating Python with MySQL.

### Problem Solving

* Diagnosed limitations of the MySQL Workbench Import Wizard.
* Began transitioning toward a Python-based ETL workflow for handling complex datasets.

---

## Current Project Status

### Completed

* [X] customers
* [X] orders_raw
* [X] orders
* [X] order_items_raw
* [X] order_items
* [X] products_raw
* [X] products
* [X] order_payments_raw
* [X] order_payments

### In Progress

* [ ] order_reviews_raw (Python-based import)

### Remaining

* [ ] sellers
* [ ] geolocation
* [ ] product_category_translation

### Upcoming

* [ ] Exploratory Data Analysis
* [ ] Business KPI Development
* [ ] Power BI Dashboard
* [ ] Customer Segmentation
* [ ] Machine Learning Models

---

## Data Loaded So Far

| Table          | Records |
| -------------- | ------: |
| customers      |  99,441 |
| orders         |  99,441 |
| order_items    | 112,650 |
| products       |  32,951 |
| order_payments | 103,886 |

---

## Summary

Day 4 focused on strengthening the ETL pipeline by completing the **Products** and **Order Payments** datasets while maintaining rigorous data validation standards. An unexpected limitation in the MySQL Workbench Import Wizard during the **Order Reviews** import led to the introduction of  **Python** ,  **Pandas** , and **MySQL Connector** into the project. This marks the transition from GUI-based imports toward a scalable Python-driven ETL workflow, bringing the project closer to real-world data engineering practices.
