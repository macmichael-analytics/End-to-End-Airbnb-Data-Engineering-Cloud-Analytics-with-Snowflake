# End-to-End Airbnb Data Engineering & Cloud Analytics with Snowflake

### Azure • Snowflake • dbt Core • Power BI

## 📍 Problem Statement

Airbnb generates vast volumes of structured and semi-structured data across listings, bookings, hosts, and reviews. However, without a robust data engineering strategy:

- Raw data remains fragmented and inconsistent, making it hard to derive business insights.

- Traditional systems are unable to scale with growing analytical demands.

- Tracking historical changes (e.g., price fluctuations or host performance over time) is complex without proper historical modeling.

- Data pipelines lack structure for data quality, lineage, and testability, reducing trust in analytics.

The core challenge: Design a scalable, maintainable, and performant data platform that transforms raw Airbnb datasets into business-ready insights for analytics and visualization using cloud data engineering best practices.

## 📌 Project Overview

This project demonstrates an end-to-end analytics engineering workflow, from raw data ingestion in the cloud to business-ready insights.

The goal was to:

- Build a scalable cloud data warehouse

- Apply best-practice data modeling using dbt

- Track historical changes using Slowly Changing Dimensions (SCD Type 2)

= Deliver actionable insights through Power BI dashboards

## 💡 Solution Summary

This project implements a modern analytics engineering pipeline leveraging cloud infrastructure and best practices to solve the above challenges:

### Cloud Data Warehouse (Snowflake)

Data is centralized in Snowflake, providing scalable storage and compute with automatic performance optimization. 
Airbyte

Structured into Bronze, Silver, and Gold layers to support data reliability, standardization, and business use cases. 
GitHub

Implements Slowly Changing Dimensions (SCD Type 2) to maintain historical trends for key dimensional entities like listings, hosts, and bookings. 
GitH

## 🏗️ Architecture Overview

The project follows the Medallion Architecture using Azure + Snowflake + dbt Core:

![]((https://github.com/macmichael-analytics/End-to-End-Airbnb-Data-Engineering-Cloud-Analytics-with-Snowflake/blob/main/pictures/design%20dbt.png)).

### Azure
- Used as the cloud platform for data storage and orchestration

### Snowflake
- Cloud data warehouse for scalable storage and compute

### dbt Core
- Used for transformations, testing, snapshots, and modeling

### Power BI
- Used for final data visualization and business insights

## 🥉 Bronze Layer – Raw Data

Raw data is ingested with minimal transformation to preserve source integrity.

Tables:

- bronze_bookings – Raw booking transactions
-  bronze_hosts – Raw host information
-  bronze_listings – Raw property listings

Purpose:

- Maintain a historical copy of source data
- Enable traceability and auditing

## 🥈 Silver Layer – Cleaned & Standardized Data

The Silver layer applies data quality rules and standardization.

Tables:

- silver_bookings – Validated booking records
- silver_hosts – Cleaned host profiles with quality metrics
- silver_listings – Standardized listings with price categorization

Key Transformations:

- Null handling and data type corrections
- Standardized naming conventions
- Derived columns for analytics

## 🥇 Gold Layer – Analytics Ready

The Gold layer contains business-ready models optimized for reporting.

Models:
- obt (One Big Table) : Denormalized table combining bookings, listings, and hosts
- fact : Fact table designed for dimensional modeling
- Ephemeral models : Used for intermediate logic without materializing tables

Purpose:
- Support fast analytics and BI reporting
- Simplify Power BI data modeling

## 🕒 Snapshots – Slowly Changing Dimensions (SCD Type 2)
- Snapshots are used to track historical changes over time.

Snapshot Models:
- dim_bookings – Tracks booking record changes
- dim_hosts – Tracks host profile updates
- dim_listings – Tracks listing changes

Why this matters:
- Enables historical analysis
- Supports trend analysis and auditing
- Critical for enterprise-grade analytics

# 📊 Data Visualization (Power BI)

### Data Modelling:

![](https://github.com/macmichael-analytics/End-to-End-Airbnb-Data-Engineering-Cloud-Analytics-with-Snowflake/blob/main/pictures/Airbnb%20model.png)

The final Gold models were connected to Power BI to create interactive dashboards showing:


![](https://github.com/macmichael-analytics/End-to-End-Airbnb-Data-Engineering-Cloud-Analytics-with-Snowflake/blob/main/pictures/Airbnb%20power%20bi.png)

- Pricing trends by month
- Listing distribution by property type
- Host activity and performance
- Revenue and service fee insights
These dashboards support data-driven business decisions.

### 🧪 Data Quality & Testing

- Source-level tests for data integrity
- dbt tests for nulls and consistency
- Reusable macros for standard logic

### 🚀 Key Skills Demonstrated

- Cloud data warehousing (Azure & Snowflake)
- Analytics engineering with dbt Core
- Medallion Architecture design
- Dimensional modeling & SCD Type 2
- Version control with GitHub
- Business intelligence with Power BI

## 📌 Why This Project Matters

This project mirrors real-world enterprise analytics workflows and demonstrates the ability to:
- Build scalable data pipelines
- Maintain data quality and history
- Translate raw data into business insights






