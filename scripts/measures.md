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

2. Total Critical Alerts
A strategic measure to isolate high-priority issues. It only counts alerts triggered with a 'Critical' severity level, helping teams prioritize urgent fixes.

Snippet de código
Total Critical Alerts = 
CALCULATE(
    COUNTROWS('data_monitoring'), 
    'data_monitoring'[alert_triggered] = "TRUE" && 
    'data_monitoring'[alert_severity] = "critical"
)
