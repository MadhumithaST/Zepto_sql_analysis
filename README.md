Zepto Inventory Analysis (SQL) 🛒
Project Overview
This project involves an end-to-end SQL analysis of real-world e-commerce inventory data from Zepto. The goal was to transform raw, "messy" data into actionable business insights regarding revenue, stock management, and logistics.

Key Highlight: While the original project guide used PostgreSQL, I successfully implemented this entire analysis using MySQL Workbench, adapting the schema and data types to fit the MySQL environment.

🛠️ Tech Stack & Skills
Database: MySQL (Workbench)
Concepts: Data Cleaning, ETL (Extract, Transform, Load), Aggregate Functions, CASE Statements, Data Type Casting.
Data Format: CSV (UTF-8)

🧼 Data Transformation (The ETL Process)
Real-world data is rarely "ready-to-use." I performed several critical cleaning steps:

The VARCHAR Pivot: Staged the out_of_stock column as VARCHAR during import to prevent data loss from "TRUE/FALSE" string mismatches.

Standardization: Cleaned and cast the out_of_stock column into TINYINT (Boolean) for optimized querying.

Currency Scaling: The raw data was stored in paise. I converted these values into Rupees (price / 100) to ensure financial accuracy.

Anomalies: Identified and removed records with an MRP of 0 to prevent skewed analysis.

📈 Business Insights
Revenue Potential: Calculated estimated total revenue per category by analyzing selling price vs. available quantity.
Revenue Leakage: Identified high-value products (MRP > 300) currently out of stock, highlighting immediate restocking priorities.
Logistics Segmentation: Categorized over 3,700 products into Low, Medium, and Bulk weight classes using CASE statements to assist in warehouse planning.

🚀 How to Run
Import the zepto_data.csv using the MySQL Table Data Import Wizard.
Execute the queries in zepto_queries.sql in sequential order.
