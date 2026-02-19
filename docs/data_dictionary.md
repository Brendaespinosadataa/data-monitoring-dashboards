# 📖 Data Dictionary

This document describes the structure and fields of the dataset used in the Data Monitoring Dashboard.

| Column Name | Description | Type |
| :--- | :--- | :--- |
| **execution_date** | Date and time of the workflow execution. | DateTime |
| **workflow_name** | The name of the automated pipeline (Marketing, Sales, Logistics). | String |
| **metric_name** | The specific KPI being tracked (e.g., total_revenue, data_volume). | String |
| **metric_value** | The numerical result of the specific metric. | Decimal |
| **records_processed**| Total number of data rows handled in that specific run. | Integer |
| **alert_triggered** | Indicates if the system detected an anomaly (TRUE/FALSE). | Boolean |
| **alert_severity** | Impact level of the incident (Critical, High, Medium, Low). | String |
| **execution_status** | Final result of the workflow run (Success or Failed). | String |
