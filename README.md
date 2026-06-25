# ecommerce-bi-ml-pipeline
# E-Commerce Business Intelligence & Machine Learning Pipeline (`ecommerce-bi-ml-pipeline`)

This repository contains a production-grade, end-to-end data platform that transforms raw retail transactions into actionable business intelligence and predictive customer segments. The architecture follows the industry-standard **Medallion Pattern**, fully orchestrated via the cloud and optimized for distributed computing[cite: 1].

## 🏗️ Architecture Layout
The data processing pipeline is structurally divided into three distinct layers hosted within Azure Data Lake Storage Gen2 (ADLS) and managed via Databricks Serverless Notebooks[cite: 1]:

*   **Bronze Layer (Historical Ingestion):** Append-only raw CSV ingestion using PySpark[cite: 1]. Enforces schema evolution (`mergeSchema=true`) and appends immutable lineage auditing metadata (`ingestion_timestamp` and `source_file`)[cite: 1].
*   **Silver Layer (Enterprise Truth):** Automated data cleaning, deduplication, and handling of missing transactional records[cite: 1]. Employs fault-tolerant date parsing algorithms to handle inconsistent source timestamps and derives calculated business features like `TotalAmount`[cite: 1].
*   **Gold Layer (Analytical Hub):** High-performance, pre-aggregated Delta tables optimized for analytical query engines[cite: 1]. Powers targeted reporting business domains including daily sales trends, product velocity, regional analytics, and specialized machine learning features[cite: 1].

## 🤖 Integrated Machine Learning Pipeline
Beyond static descriptive reporting, this platform embeds an automated, predictive ML pipeline directly into the final transformation cycle[cite: 1]:
1. **Feature Engineering:** Computes an algorithmic RFM (Recency, Frequency, Monetary) matrix for the active customer base[cite: 1].
2. **Preprocessing:** Assembles multidimensional feature data into single vectors and applies a standard scaler (`StandardScaler`) to normalize distribution variances[cite: 1].
3. **Clustering:** Fits a distributed **K-Means Clustering** algorithm to automatically categorize consumers into distinct operational groups (e.g., High-Value Loyalists vs. Churn Risks)[cite: 1].
4. **Actionable Outputs:** Persists algorithmic predictions directly into Delta lake tables to drive filtered, customer-centric campaigns[cite: 1].

## 🛠️ Technology Stack & Orchestration
*   **Data Processing:** Apache Spark / PySpark MLlib[cite: 1]
*   **Storage Framework:** Delta Lake / Azure ADLS Gen2[cite: 1]
*   **Orchestration:** Azure Data Factory (Sequential pipeline triggers with built-in execution checks)[cite: 1]
*   **Governance:** Databricks Unity Catalog for data asset security[cite: 1]
*   **Visualization:** Power BI Dashboard powered by Databricks SQL Warehouse endpoints[cite: 1]
