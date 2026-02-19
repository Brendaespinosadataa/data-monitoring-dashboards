# 🧠 DAX Measures Documentation

This document outlines the core business logic and DAX (Data Analysis Expressions) used to power the **Data Monitoring & Operations Dashboard**. These measures ensure accurate tracking of pipeline reliability and system performance.

---

## 📊 Core Performance Metrics

### 1. Overall Success Rate
This is the primary health indicator. It calculates the percentage of successful executions against the total number of attempts across all workflows.

```dax
Overall Success Rate = 
DIVIDE(
    CALCULATE(
        COUNTROWS('data_monitoring'), 
        'data_monitoring'[execution_status] = "success"
    ),
    COUNTROWS('data_monitoring'),
    0
)

---

### 2. Total Critical Alerts
A strategic measure to isolate high-priority issues. It only counts alerts triggered with a 'Critical' severity level, helping teams prioritize urgent fixes.

Snippet de código
Total Critical Alerts = 
CALCULATE(
    COUNTROWS('data_monitoring'), 
    'data_monitoring'[alert_triggered] = "TRUE" && 
    'data_monitoring'[alert_severity] = "critical"
)

---

### 3. Total Records Processed
A volume metric used to monitor data throughput. It helps identify "silent failures" where a script might succeed but process zero or fewer records than expected.

Snippet de código
Total Records Processed = SUM('data_monitoring'[records_processed])

---

🎨 Visual Logic & Formatting
Severity Color Coding
To maintain a professional DataOps look and feel, conditional formatting was applied based on the following logic:
Status/Severity,Hex Code,Visual Indicator
Critical,#D64550,🔴 High Risk
High,#EA9022,🟠 Immediate Attention
Medium,#FBC131,🟡 Monitor Closely
Success,#27AE60,🟢 Healthy

---

Dynamic Titles
Titles were customized to reflect the strategic nature of the data, moving away from raw column names (e.g., using "Incident Distribution" instead of "Count of Alerts").

🛠️ Data Transformation Note
All raw data was processed via Power Query to ensure correct data types (DateTime for execution dates and Boolean for alert flags) before applying the measures above.

Created by Brenda Espinosa
