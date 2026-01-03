# Airbnb End-to-End Analytics Engineering Project

### Azure • Snowflake • dbt Core • Power BI

## 📌 Project Overview

This project demonstrates an end-to-end analytics engineering workflow, from raw data ingestion in the cloud to business-ready insights.

The goal was to:

- Build a scalable cloud data warehouse

- Apply best-practice data modeling using dbt

- Track historical changes using Slowly Changing Dimensions (SCD Type 2)

= Deliver actionable insights through Power BI dashboards

## 🏗️ Architecture Overview

The project follows the Medallion Architecture using Azure + Snowflake + dbt Core:

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

# 📁 Project Structure
Azure_DBT_Snowflake/
├── README.md
├── pyproject.toml
├── main.py
│
├── SourceData/
│   ├── bookings.csv
│   ├── hosts.csv
│   └── listings.csv
│
├── DDL/
│   ├── ddl.sql
│   └── resources.sql
│
└── azure_dbt_snowflake_project/
    ├── dbt_project.yml
    ├── ExampleProfiles.yml
    │
    ├── models/
    │   ├── sources/
    │   │   └── sources.yml
    │   ├── bronze/
    │   ├── silver/
    │   └── gold/
    │       ├── fact.sql
    │       ├── obt.sql
    │       └── ephemeral/
    │
    ├── macros/
    ├── analyses/
    ├── snapshots/
    ├── tests/
    └── seeds/

# 📊 Data Visualization (Power BI)
### Data Modelling:

The final Gold models were connected to Power BI to create interactive dashboards showing:

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
