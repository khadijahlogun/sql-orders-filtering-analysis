# SQL Retail Orders Data Filtering & Querying Demonstration

## 1. Project Introduction
This repository contains a structured collection of SQL queries designed to extract, filter, and analyze customer order data from a relational database. Built as part of an ongoing data analysis portfolio development, this project highlights foundational data retrieval techniques, conditional filtering (`WHERE` clause logic), range evaluations, and complex boolean operator precedence.

## 2. Business Problem
In commercial environments, stakeholders frequently need to isolate specific subsets of transactional data to answer targeted business questions—such as regional purchasing trends, high-volume product demand, or exclusions of specific geographic markets. This project simulates common analytical data-pull scenarios, demonstrating how to construct precise SQL queries to answer operational questions efficiently.

## 3. Project Objectives and Analytical Questions
The primary objective is to demonstrate core SQL competency through clean, readable, and logically structured queries. Key investigative questions addressed include:
* How can we retrieve all raw customer order records for broad inspection?
* How do we isolate orders originating from specific geographic markets (e.g., Canada or Nigeria)?
* What queries effectively filter transactions by specific product categories (e.g., phones, laptops, tablets, and smartwatches)?
* How do we apply numeric thresholds (e.g., quantity minimums) and multi-condition grouping using `AND` and `OR` logic?

## 4. Dataset Description and Scope
The analysis operates on a sample relational structure containing order records (`Orders` and `Orders_table`). 
* **Variables / Columns:** `Customername`, `product`, `country`, and `Quantity`.
* **Geographic Scope:** International transactions spanning multiple regions, including Canada, the USA, and Nigeria.
* **Scope & Limitations:** This is a focused technical demonstration dataset intended to showcase query logic and syntax proficiency rather than deep macroscopic business forecasting.

## 5. Tools and Technologies
* **SQL (Structured Query Language):** Used for database querying, projection, and conditional filtering.
* **Database Environment:** Compatible with standard SQL dialects (PostgreSQL, MySQL, SQLite, SQL Server).

## 6. Analytical Methodology and Workflow
The queries progress from basic data projection to advanced conditional filtering:
1. **Basic Projection:** Extracting entire tables (`SELECT * FROM Orders`) and projecting specific columns (`SELECT Customername, product, country FROM Orders`).
2. **Exact String Matching & Exclusion:** Filtering rows using equality (`=`) and inequality (`<>`) operators (e.g., isolating Canadian orders or excluding the USA market).
3. **Numeric Comparisons & Ranges:** Utilizing comparison operators (`>=`, `>`) and the `BETWEEN` operator to segment orders by quantity thresholds.
4. **Compound Boolean Logic & Precedence:** Combining multiple criteria using `AND` and `OR` operators alongside parentheses to control evaluation order (e.g., filtering laptops sold in Nigeria, or multi-item purchases of tablets and smartwatches).

```sql
-- Example: Compound filtering with logical operator precedence
SELECT * 
FROM Orders_table
WHERE Quantity > 3 AND (Product = 'tablet' OR product = 'smartwatch');
