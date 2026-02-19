# 🧠 Advanced DAX Measures Documentation

This document details the advanced business logic and DAX formulas developed for the **Data Operations & Monitoring Dashboard**. These measures power the trend analysis, KPIs, and percentage change indicators.

---

## 🚀 Key Performance Indicators (KPIs)

### 1. Total Records Processed (Life-to-Date)
Aggregates the total volume of data rows handled across all monitored pipelines.
```dax
Total Records Processed = SUM('data_monitoring'[records_processed])
```

---
### 2. Total Alerts Triggered
A count of all incidents where the monitoring system detected an anomaly.

```
Total Alerts Triggered = 
CALCULATE(
    COUNTROWS('data_monitoring'), 
    'data_monitoring'[alert_triggered] = "TRUE"
)
```
---

### 3. Volume Processed (Last 30 Days)
Filters the record sum for the most recent 30-day window to monitor short-term throughput.

```
Snippet de código
Volume 30D = 
CALCULATE(
    [Total Records Processed],
    DATESINPERIOD('data_monitoring'[execution_date], MAX('data_monitoring'[execution_date]), -30, DAY)
)
```

---

### 📈 Trend & Analysis Measures
### 4. Percentage Change (%)
Calculates the growth or drop in record volume compared to the previous execution. Essential for detecting silent data loss.

```
% Change in Records = 
VAR CurrentValue = [Total Records Processed]
VAR PreviousValue = 
    CALCULATE(
        [Total Records Processed], 
        DATEADD('data_monitoring'[execution_date], -1, DAY)
    )
RETURN
    DIVIDE(CurrentValue - PreviousValue, PreviousValue, 0)
```

---
*Created by Brenda Espinosa*

