# SportsBar Data Engineering Pipeline

An end-to-end data engineering project developed for SportsBar to replace manual data handling with a structured and scalable data pipeline using AWS S3 and Databricks.

## Project Overview

AtliQon is a multinational company with an established data pipeline and data platform. SportsBar, a company operating in the sports-products business, was previously managing and storing its data manually.

To improve data reliability, scalability, historical data management, and analytical capabilities, management decided to establish a dedicated data pipeline for SportsBar.

The solution processes SportsBar's data through a Medallion Architecture and produces business-ready data that can be used independently for SportsBar analytics or integrated with AtliQon's existing Gold layer when combined analysis is required.

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

<img width="20005" height="11129" alt="project_architecture" src="https://github.com/user-attachments/assets/83cc6d0e-c4b6-4b80-b6c2-fae95524b2f8" />

### Bronze Layer

The Bronze layer stores raw source data while preserving the original information and historical records.

Key responsibilities:

- Raw data ingestion.
- Historical data preservation.
- Initial storage of source data.
- Providing a reliable foundation for downstream processing.

### Silver Layer

The Silver layer transforms raw data into clean and standardized datasets.

The layer is responsible for cleansing, validating, standardizing, transforming, and integrating the incoming data before it is passed to the Gold layer.

### Gold Layer

The Gold layer contains business-ready data designed for analytical consumption.

SportsBar's Gold layer provides a structured and reliable representation of its business data for reporting and analysis.

A major requirement of the project is to make **SportsBar's Gold layer compatible with AtliQon's existing Gold layer**. This allows the two companies' business-ready data to be brought together when management requires combined analysis across the organizations.

This approach allows:

- SportsBar to maintain its own dedicated data pipeline.
- AtliQon to continue using its existing data platform.
- SportsBar's processed data to remain independent while still being compatible with AtliQon's analytical ecosystem.
- Management to analyze SportsBar and AtliQon data together when required.
## DashBoard

<img width="1878" height="672" alt="image" src="https://github.com/user-attachments/assets/30bd5325-671c-4717-ae65-bc508afbcf77" />

<img width="1858" height="767" alt="image" src="https://github.com/user-attachments/assets/72627f71-8537-4dae-afda-333414ce4842" />


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

## Credits

