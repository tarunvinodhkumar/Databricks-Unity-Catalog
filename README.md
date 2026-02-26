Bootcamp Project 4 – Azure Data Engineering Pipeline
📌 Project Overview

This project demonstrates an end-to-end Azure Data Engineering solution using:

Azure Data Factory (Orchestration & Scheduling)

Azure Databricks (Data Ingestion & Transformation)

Unity Catalog with Delta Lake (Gold Layer Storage)

Plotly (Visualization)

The pipeline ingests raw sales data from GitHub, transforms it using PySpark, stores curated data in Unity Catalog, and generates analytical visualizations.
📂 Data Source

Sales datasets for three years:

2019

2020

2021

Each dataset includes:

SalesOrderNumber

SalesOrderLineNumber

OrderDate

CustomerName

Email

Item

Quantity

UnitPrice

Tax

⚙️ Implementation Steps
1️⃣ Unity Catalog Setup

Created a Catalog

Created a Schema

Created Volumes for:

Raw Data (Bronze)

Gold Layer

2️⃣ Data Ingestion (Bronze Layer)

Fetched CSV files directly from GitHub

Applied predefined schema

Loaded data into Spark DataFrames

Stored raw data into Unity Catalog volume

3️⃣ Data Cleaning (Silver Layer)

Removed null primary keys

Removed duplicate records using Window function

Ensured latest records retained

4️⃣ Gold Layer Aggregation

Performed aggregations:

🔹 Customer-Level Aggregation

Total Sales = Quantity × UnitPrice

Total Tax

🔹 Year-Level Aggregation

Total Sales per Year

Total Tax per Year

Stored final results as Delta tables in Unity Catalog.

📊 Visualization

Used Plotly to generate interactive visualizations:

Line graph showing Sales trend (2019–2021)

Line graph showing Tax trend (2019–2021)

Year-over-year comparison

🔁 Azure Data Factory Pipeline

Created ADF pipeline

Added Databricks Notebook activity

Configured trigger & scheduling

Monitored pipeline execution

ADF orchestrates the entire workflow automatically.

⭐ Optional Enhancement

Created metadata Delta table

Designed dynamic ingestion notebook

Enabled scalable ingestion approach

🛠️ Technologies Used

Azure Data Factory

Azure Databricks

PySpark

Unity Catalog

Delta Lake

Plotly

GitHub

📈 Business Insights

Revenue growth analysis (2019–2021)

Tax trend evaluation

Customer sales performance

Year-over-year deviation analysis

🎯 Key Learnings

End-to-end cloud data pipeline development

Data governance using Unity Catalog

Delta Lake implementation

Window functions for deduplication

Aggregation & KPI generation

Workflow orchestration using ADF

Data visualization using Plotly

👤 Author

Tarun Vinodh Kumar
Azure Data Engineering Enthusiast
