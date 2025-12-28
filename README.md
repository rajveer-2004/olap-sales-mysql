# Simulation of OLAP Cube Using MySQL

This project simulates an OLAP (Online Analytical Processing) Cube using MySQL by implementing a star schema, pre-aggregated summary tables, and OLAP operations such as SLICE and DICE for fast multidimensional analysis of sales data.

The implementation follows a Relational OLAP (ROLAP) approach, where the OLAP cube is represented using relational tables instead of a dedicated multidimensional engine.

---

## Objective

To demonstrate how OLAP cube concepts can be simulated using MySQL by:
- Designing a dimensional data model (Star Schema)
- Creating aggregate tables for performance optimization
- Implementing SLICE and DICE operations
- Benchmarking query performance

---

## Schema Design

A Star Schema was implemented with the following structure:

### Fact Table
- fact_sales  
  - sales_amount  
  - quantity  
  - date_id  
  - product_id  
  - region_id  

### Dimension Tables
- dim_date – date-related attributes  
- dim_product – product-related attributes  
- dim_region – region-related attributes  

The fact table stores transactional data, while dimension tables store descriptive attributes used for analysis.

---

## OLAP Cube Representation

The OLAP cube is simulated using:
- Measures from the fact table (sales amount, quantity)
- Dimensions from dimension tables (date, product, region)
- Pre-aggregated tables representing summarized cube views

This approach represents a ROLAP-style OLAP cube.

---

## OLAP Aggregates

To improve query performance, pre-aggregated tables were created at different levels of granularity:

- Daily sales aggregation
- Product-wise sales aggregation
- Region-wise sales aggregation

These tables store summarized results and eliminate repeated runtime aggregation.

---

## OLAP Operations

### SLICE Operation
Filters the cube along a single dimension.

Example:

---

### DICE Operation
Filters the cube using multiple dimensions simultaneously.

Example:

---

## Performance Benchmarking

Query performance was evaluated using MySQL profiling:

- Raw queries on the fact_sales table required joins and runtime aggregation
- Queries on pre-aggregated tables executed faster due to pre-computed summaries

This demonstrates how OLAP systems trade additional storage for improved analytical performance.

---

## Technologies Used

- MySQL Server  
- MySQL Workbench  
- SQL (DDL, DML, Stored Procedures)  
- GitHub  

---

## How to Use

1. Open the SQL file in MySQL Workbench  
2. Execute the script to create tables, insert data, and create procedures  
3. Run OLAP operations:
4. Benchmark performance using:

---

## Project Type

Relational OLAP (ROLAP) Simulation

---

## Author

Rajveer Singh  
B.Tech – Electronics & Communication Engineering  
NIT Delhi

