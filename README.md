
# Scholarship Intelligence & Data Platform

## Project Overview

An end-to-end data engineering project that extracts scholarship scheme information from the official National Scholarship Portal (NSP), processes and cleans the data using Python and PySpark, validates data quality, stores structured datasets in Snowflake, and visualizes category-level insights using Power BI.

## Architecture Diagram

![Scholarship Intelligence Data Platform Architecture](report/Scholarship%20Intelligence%20Data%20Platform%20Architecture.png)

## Technologies Used

- Python
- SQL
- PySpark
- PyArrow
- Snowflake
- Power BI
- GitHub

## Key Features

- Extract scholarship scheme names from the official NSP listing.
- Preserve the raw HTML snapshot for source traceability.
- Generate structured CSV datasets using Python.
- Clean and transform scholarship records using PySpark.
- Store cleaned data in Parquet format.
- Load 31 scholarship records into Snowflake.
- Organize Snowflake data using Bronze, Silver, and Gold schemas.
- Perform data quality checks using Python and SQL.
- Generate scholarship category summaries using SQL.
- Visualize category-level insights using Power BI.

## Project Workflow

1. Extract scholarship scheme names from the official NSP listing.
2. Preserve the downloaded HTML snapshot.
3. Parse the HTML and generate a structured CSV file using Python.
4. Clean records and derive scholarship categories using PySpark.
5. Store the cleaned dataset in Parquet format in the local Silver layer.
6. Load processed records into the Snowflake Silver schema.
7. Generate category-level summary data in the Snowflake Gold schema.
8. Validate data quality using Python and SQL.
9. Connect the Snowflake Gold summary table to Power BI.

## Data Source

**National Scholarship Portal (NSP)**

Website: https://scholarships.gov.in/All-Scholarships

The current dataset contains 31 scholarship scheme names extracted from the official NSP listing.

**Data Limitation:** Detailed scholarship eligibility information has not been collected or verified. The dataset represents official listing information only.

## Snowflake Data Platform

**Database:** `SCHOLARSHIP_DB`

**Warehouse:** `COMPUTE_WH`

**Schemas:**
- BRONZE
- SILVER
- GOLD

**Implemented Tables:**
- `SILVER.SCHOLARSHIPS`
- `GOLD.SCHOLARSHIP_CATEGORY_SUMMARY`

## Data Quality Results

| Validation | Result |
|---|---:|
| Total Records | 31 |
| Unique Records | 31 |
| Empty Scholarship Names | 0 |
| Duplicate Names | 0 |
| Invalid Categories | 0 |
| Empty Source URLs | 0 |

**Overall Data Quality Status: PASSED**

## Power BI Dashboard

The Power BI dashboard presents scholarship category distribution and key project metrics using data from the Snowflake Gold summary table.

[View / Download Power BI Dashboard](report/Scholarship_Intelligence_Dashboard.pbix)

## Repository Structure

```text
scholarship-intelligence-pipeline/
│
├── data/
│   └── lake/
│       ├── bronze/
│       ├── silver/
│       └── gold/
│
├── docs/
│   └── data_sources.md
│
├── report/
│   ├── README.md
│   ├── Scholarship Intelligence Data Platform Architecture.png
│   └── Scholarship_Intelligence_Dashboard.pbix
│
├── src/
│   ├── ingestion/
│   │   └── parse_nsp.py
│   ├── processing/
│   │   └── process_scholarships.py
│   ├── quality/
│   │   └── validate_parquet.py
│   └── analytics/
│       └── create_gold_summary.py
│
├── .gitignore
├── requirements.txt
└── README.md
```

## Future Scope

- Integrate Azure Data Lake Storage Gen2.
- Add additional official scholarship data sources.
- Collect and validate detailed eligibility information.
- Implement automated pipeline scheduling and monitoring.
- Extend analytics with additional scholarship insights.

## Project Status

**Current Status:** Core data extraction, processing, quality validation, Snowflake integration, and Power BI visualization completed.

## Author

**Shivanjali Pravin Thanke**

Developed as a Data Engineering portfolio project.
