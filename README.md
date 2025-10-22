# Payroll-Analytics-Pipeline-in-Microsoft-Fabric
This project demonstrates an end-to-end data engineering and analytics workflow in Microsoft Fabric, implementing the Medallion Architecture (Bronze → Silver → Gold).
# Project Goals 
. Automate data ingestion from raw CSV files to Fabric Lakehouse (Bronze layer).

. Clean and transform data into a standardized Silver layer.

. Aggregate and model Gold-layer data into a dimensional (star) schema.

. Visualize KPIs in Power BI, including:

1 Total Overtime

2 Average Salary

3 % Overtime Spend

. Implement governance, optimization, and monitoring within Fabric pipelines.
# Technologies & Tools
| Category        | Tool                                      | Purpose                               |
| --------------- | ----------------------------------------- | ------------------------------------- |
| Data Ingestion  | Microsoft Fabric Data Factory (Pipelines) | Ingest CSV to Lakehouse               |
| Data Storage    | Microsoft Fabric Lakehouse (OneLake)      | Store Bronze, Silver, Gold data       |
| Data Processing | Fabric Notebooks (Spark, PySpark, SQL)    | Transform and aggregate               |
| Data Modeling   | Materialized Lake Views                   | Define Silver and Gold tables         |
| Visualization   | Power BI (DirectLake Connection)          | KPI dashboards                        |
| Version Control | GitHub                                    | Store code and documentation          |
| Documentation   | Markdown (README.md)                      | Report and project details            |
| Optional        | Power Automate / Fabric Alerts            | Pipeline monitoring and notifications |

# Project walkthrough 
# Step 1 — Data Ingestion (Bronze Layer)

# Objective: Load raw CSV files into a Bronze Lakehouse table.

# Actions:

. Create a Fabric Data Pipeline.

. Add Copy Data activity to pull CSV files.

. Define target Bronze Lakehouse and table name.

. Include ingestion metadata (load_timestamp, source_filename).


<img width="735" height="281" alt="Screenshot (77)" src="https://github.com/user-attachments/assets/2f632447-aa6e-42bf-a086-df287bcc1f11" />


<img width="706" height="388" alt="Screenshot (76)" src="https://github.com/user-attachments/assets/bbae135e-a567-40d4-a557-86caaca1325d" />

# Step 2 — Data Transformation (Silver Layer)

# Objective: Clean, standardize, and join Employee and Payroll data.

<img width="777" height="309" alt="Screenshot (84)" src="https://github.com/user-attachments/assets/0a79e01d-8c92-4e14-be25-0affa1cd352b" />

# Step 3 — Data Aggregation & Modeling (Gold Layer)

# Objective: Build a star schema with Fact and Dimension tables, and compute KPIs.
<img width="756" height="440" alt="Screenshot (85)" src="https://github.com/user-attachments/assets/0cb5ae0a-745e-4c87-a98b-ec991db61262" />
<img width="740" height="406" alt="Screenshot (86)" src="https://github.com/user-attachments/assets/20a31dd3-7c8b-4082-8224-bd7d4baf8a7c" />

# Step 4 — Analytics & Visualization (Power BI)

# Objective: Build a Power BI dashboard using the Gold Lakehouse.

# Steps:

. Open Power BI Desktop → Get Data → Azure → Microsoft Fabric → Lakehouse.

# Build visuals for:

. Total Overtime

. Average Salary

. % Overtime Spend

. Trend over Time by Agency

. Publish to Fabric Workspace and create an App.
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/897c614a-aefb-4357-a0db-b75a78b59be4" />

# Recommendations
1. # Architecture & Design

.Adopt a Medallion Architecture (Bronze–Silver–Gold) for clarity and maintainability.

.Use separate Lakehouses for each layer.

2. # Automation & Monitoring

. Schedule pipeline refreshes in Fabric Data Factory.

. Add alert rules for failed pipeline runs (via Power Automate or email).

3. # Performance Optimization

. Use Delta tables with partitioning (e.g., by pay_date or agency_id).

. Implement Materialized Lake Views for frequently queried aggregates.

4. # Governance & Security

. Configure Role-Based Access Control (RBAC) in Fabric Workspace.

. Mask or hash sensitive employee data.

5. # Documentation & Version Control

. Store all notebooks, SQL, and pipeline JSONs in GitHub.

. Maintain a clear CHANGELOG.md and README.md.

. Include architecture diagrams and Power BI screenshots for reviewers.
