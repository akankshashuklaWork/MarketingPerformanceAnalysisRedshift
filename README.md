# Marketing ELT Pipeline (Matillion + BigQuery + Amazon Redshift)

## Project Overview

This project implements an **ELT (Extract–Load–Transform) data pipeline** for marketing analytics using a modern data engineering stack. The pipeline ingests marketing campaign data, stages it in BigQuery, loads it into Amazon Redshift, and performs transformations and data profiling using Matillion.

The goal of this project is to simulate a **production-style data pipeline** that supports scalable marketing performance analysis.

---

## Architecture

Data flows through the following architecture:

Facebook Ads Data
↓
BigQuery (Staging Layer)
↓
Matillion ETL
↓
Amazon Redshift (Data Warehouse)
↓
Analytics / Reporting

---

## Tech Stack

| Component           | Tool Used       |
| ------------------- | --------------- |
| Data Source         | Facebook Ads    |
| Staging Layer       | Google BigQuery |
| ETL / Orchestration | Matillion       |
| Data Warehouse      | Amazon Redshift |
| Version Control     | GitHub          |

---

## Pipeline Overview

### 1. Data Ingestion Pipeline

Loads raw marketing campaign data into the staging layer.

Key responsibilities:

* Extract campaign data
* Load data into BigQuery staging tables
* Prepare data for transformation

![Orchestration Pipeline](images/orchestration_pipeline.png)

---

### 2. Transformation Pipeline

Transforms raw marketing data into an analytics-ready dataset stored in Amazon Redshift.

Key transformations include:

* Data cleaning
* Metric calculations
* Aggregation
* Business metric generation

Example calculated metrics:

* CTR (Click Through Rate)
* CPA (Cost per Acquisition)
* ROAS (Return on Ad Spend)

![Transformation Pipeline](images/transformation_pipeline.png)

---

### 3. Data Profiling Pipeline

Performs profiling to ensure data quality and validate loaded datasets.

Checks include:

* Null value analysis
* Distribution checks
* Row count validation
* Data completeness

![Data Profiling Pipeline](images/data_profiling_pipeline.png)

---

## Repository Structure

```
marketing-elt-pipeline
│
├ pipelines
│   ├ load-bigquery-marketing-data.orch.yaml
│   ├ transform-marketing-dataRedshift.tran.yaml
│   └ profile-marketing-tables.tran.yaml
│
├ images
│   ├ orchestration_pipeline.png
│   ├ transformation_pipeline.png
│   └ data_profiling_pipeline.png
│
└ README.md
```

---

## Example Warehouse Table

Final analytics table:

`dm_marketing_performance`

Fields include:

* date
* campaign
* datasource
* clicks
* impressions
* spend
* conversions
* ctr
* cpa
* roas

---

## Example Metrics

CTR:

```
CTR = clicks / impressions
```

CPA:

```
CPA = spend / conversions
```

ROAS:

```
ROAS = revenue / spend
```

---

## Key Learnings

This project demonstrates:

* Building ELT pipelines with Matillion
* Integrating multiple cloud data platforms
* Designing analytics-ready warehouse tables
* Data validation and profiling workflows
* Real-world marketing analytics pipeline design

---

## Future Improvements

Potential enhancements include:

* Automating pipeline scheduling
* Adding data quality frameworks
* Integrating dashboard tools (Tableau / Power BI)
* Implementing CI/CD for pipeline deployment

---

## Author

Akanksha Shukla
