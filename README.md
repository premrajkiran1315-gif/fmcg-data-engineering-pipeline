# SportsBar Data Engineering Pipeline

An end-to-end data engineering project developed for SportsBar to replace manual data handling with a structured and scalable data pipeline using AWS S3 and Databricks.

## Project Overview

AtliQon is a multinational parent company with an established data
pipeline and data platform. SportsBar is a child company operating in
the sports-products business.

While AtliQon already had an established data pipeline, SportsBar was
managing its data manually. Management therefore decided to implement
a dedicated data pipeline for SportsBar while keeping its processed
data compatible with AtliQon's existing analytical ecosystem.

The solution processes SportsBar's data through a Medallion Architecture
and produces business-ready data that can be used independently for
SportsBar analytics or integrated with AtliQon's existing Gold layer
when combined analysis is required.

## Business Problem

SportsBar's manual approach to storing and processing data created challenges in managing growing data volumes and preparing reliable information for analysis.

The business required a dedicated pipeline that could:

- Automate data processing and reduce manual data handling.
- Preserve raw and historical data.
- Clean and transform data before analytical use.
- Separate raw, processed, and business-ready data.
- Support both complete and newly arriving data.
- Provide reliable datasets for reporting and analytics.
- Enable integration with AtliQon's existing analytical data platform.

## Client Requirements

- Build a dedicated data pipeline for SportsBar.
- Store raw and historical data in AWS S3.
- Use Databricks for data ingestion and processing.
- Implement a Bronze layer for raw data.
- Implement a Silver layer for cleaned and transformed data.
- Implement a Gold layer for business-ready data.
- Support Full Load and Incremental Load processing.
- Process customer, product, pricing, and order data.
- Enable SportsBar's business-ready data to integrate with AtliQon's Gold layer.
- Provide data suitable for analytical reporting and visualization.

## Data Architecture

<img width="1576" height="873" alt="image" src="https://github.com/user-attachments/assets/2749a924-0f34-4317-a2b5-ff75f6544e2e" />


The project follows a **Medallion Architecture** consisting of Bronze,
Silver, and Gold layers.

### Bronze Layer — Raw Data Ingestion

The Bronze layer ingests raw source data such as Customer, Product,
Pricing, and Order files from **AWS S3** using **Databricks Auto Loader /
Lakeflow Jobs**.

Raw data is stored in **Delta Lake / Delta Tables** in an append-only
format, preserving historical records without modifying the original
source data.

After successful ingestion, source files are automatically archived
from the S3 Landing Zone to the S3 Archive location.

### Silver Layer — Data Cleansing & Transformation

The Silver layer reads the raw Delta data from the Bronze layer and
applies data quality and transformation processes.

The processing includes:

- Schema and data-type enforcement.
- Handling missing and null values.
- Removing duplicate records.
- Standardizing data structures.
- Creating clean and unified datasets for downstream business logic.

### Gold Layer — Business Analytics & Enterprise Integration

The Gold layer transforms the cleaned Silver data into structured
**fact and dimension models** designed around SportsBar's business
requirements and analytical metrics.

SportsBar's Gold-layer schemas are mapped and aligned with **AtliQon's
existing Enterprise Gold layer**, allowing the two companies'
business-ready data to be integrated when combined analysis is required.

The Gold layer serves business-ready datasets for analytical
consumption through **Databricks Genie** and external BI tools such as
**Power BI**.

## DashBoard
The Power BI dashboard provides a business-level view of SportsBar's
sales performance and enables analysis across products, customers,
regions, and time.

<img width="1878" height="672" alt="image" src="https://github.com/user-attachments/assets/30bd5325-671c-4717-ae65-bc508afbcf77" />

<img width="1858" height="767" alt="image" src="https://github.com/user-attachments/assets/72627f71-8537-4dae-afda-333414ce4842" />

## Dashboard Insights

### 1. High-Level Metrics

- **Total Revenue:** **105.34B** generated overall.
- **Total Quantity Sold:** **34.13M** units.
- **Customer Base:** **54 unique customers**, indicating a concentrated B2B/wholesale customer base.
- **Average Selling Price (ASP):** **4,043.16** per unit.

### 2. Channel & Sales Strategy

- **Retailer:** Contributes **78.49%** of total revenue and is the dominant sales channel.
- **Direct:** Contributes **20.23%** of total revenue.
- **Key Opportunity:** The high concentration of revenue in the Retailer channel creates an opportunity to strengthen the Direct channel and diversify revenue sources.

### 3. Product & Variant Performance

- **Top Revenue Product:** **PX Grip Cricket Batting Gloves** with approximately **7.98B** in revenue.
- **Second:** **WL Hex Dumbbell** with approximately **7.62B**.
- **Third:** **NX Pro Cricket Leg Guards** with approximately **6.21B**.
- Revenue is distributed across both **Cricket equipment** and **Fitness/Gym equipment**, indicating demand across multiple product categories.
- **Top Variant:** **Large** with approximately **4.76B** in revenue.
- **Fitness variants:** **5 kg** and **Curl Bar** are among the strongest-performing variants.

### 4. Seasonal Revenue Trends

- Revenue remains relatively stable from **January to August**, ranging from approximately **4.58B to 6.59B** per month.
- Revenue increases significantly from **September**, reaching **12.87B**.
- **November records the highest monthly revenue at 20.82B**.
- Revenue falls to **7.19B in December** after the November peak.

### 5. Top Customer Accounts

- **FitnessWorld:** **9.53B** revenue from **2.25M units**.
- **FastTrack Sports:** **8.21B** revenue from **1.94M units**.
- **Fitness Mania:** **5.96B** revenue.
- **Active Gear:** **5.87B** revenue.

### 6. Areas for Sales Improvement

Based on the dashboard, the following areas could help improve sales performance:

- **Increase Direct-channel sales:** Since Retailers contribute **78.49%** of revenue, increasing Direct-channel contribution could reduce dependence on a single channel.
- **Focus on high-performing products:** Maintain inventory and promotional focus on products such as **PX Grip Cricket Batting Gloves, WL Hex Dumbbell, and NX Pro Cricket Leg Guards**.
- **Optimize inventory before peak months:** The sharp increase in revenue from September to November suggests that inventory and supply planning should be strengthened before the peak period.
- **Strengthen key-account relationships:** Customers such as **FitnessWorld and FastTrack Sports** contribute significant revenue and should receive focused account management.
- **Use cross-selling opportunities:** Since both Cricket and Fitness products perform strongly, customers purchasing one category could potentially be targeted with relevant products from the other category.
- **Diversify the customer base:** With only **54 unique customers**, acquiring additional B2B customers could reduce dependency on a relatively concentrated customer base.
- **Monitor post-peak performance:** The drop from **20.82B in November to 7.19B in December** should be monitored to understand whether it is driven by demand, inventory, or customer ordering patterns.

### Key Business Recommendation

> **Prioritize peak-season planning, strengthen key customer relationships, increase Direct-channel contribution, and diversify the customer base while maintaining strong availability of high-performing products.**

## Technologies Used

- **AWS S3** — Cloud storage for raw and historical data.
- **Databricks** — Data ingestion, processing, and transformation.
- **Python** — Data processing within the Databricks environment.
- **SQL** — Data querying and transformation.
- **Delta** — Structured storage for processed data.
- **Power BI** — Business reporting and visualization.
- **GitHub** — Version control and project documentation.

## Tools & Concepts Learned

Through this project, I gained practical exposure to:

- AWS S3 and cloud-based data storage.
- Databricks data processing.
- Medallion Architecture.
- Bronze, Silver, and Gold data layers.
- ETL pipeline development.
- Full Load processing.
- Incremental Load processing.
- Data cleansing and transformation.
- Historical data management.
- Cloud-based data workflows.
- Data integration between analytical layers.
- Power BI reporting and visualization.

## Challenges Faced

### Handling Multiple Data Sources

Working with data from different business sources required understanding their structures, relationships, and business meaning before integrating them into a common analytical workflow.

### Full and Incremental Processing

A key challenge was handling both initial complete datasets and newly arriving data while ensuring that incremental processing did not unnecessarily reprocess historical information.

### Data Quality

Raw data required cleansing, validation, standardization, and transformation before it could be reliably used for analytical purposes.

### Designing the Medallion Architecture

Maintaining a clear separation between raw, cleaned, and business-ready data required careful organization of the processing workflow across the Bronze, Silver, and Gold layers.

### Integrating SportsBar with AtliQon

SportsBar required its own dedicated pipeline while still being able to work with AtliQon's existing analytical ecosystem.

A key challenge was therefore producing a consistent Gold-layer structure that allows SportsBar's business-ready data to connect with AtliQon's Gold layer for combined analysis when required.

## Key Outcomes

- Built a dedicated data engineering pipeline for SportsBar.
- Replaced manual data handling with a structured data-processing workflow.
- Implemented Bronze, Silver, and Gold data layers.
- Used AWS S3 for raw and historical data storage.
- Used Databricks for data ingestion and transformation.
- Implemented Full Load and Incremental Load workflows.
- Processed customer, product, pricing, and order data.
- Prepared business-ready data for analytical use.
- Enabled SportsBar's Gold layer to integrate with AtliQon's existing Gold layer.
- Created a foundation for combined analysis of SportsBar and AtliQon data.



