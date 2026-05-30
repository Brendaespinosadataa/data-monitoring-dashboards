# 📊 Data Monitoring & Operations Dashboard

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Looker Studio](https://img.shields.io/badge/Looker_Studio-4285F4?style=for-the-badge&logo=looker&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Power Query](https://img.shields.io/badge/Power_Query-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-FFB000?style=for-the-badge&logo=microsoft&logoColor=white)
![Data Analytics](https://img.shields.io/badge/Data_Analytics-0A66C2?style=for-the-badge&logo=databricks&logoColor=white)
![Business Intelligence](https://img.shields.io/badge/Business_Intelligence-1F4E79?style=for-the-badge)
![Data Observability](https://img.shields.io/badge/Data_Observability-6C63FF?style=for-the-badge)

## 📖 Project Description
This repository features a **Strategic Operations Dashboard** focused on Data Observability. It monitors automated workflows (n8n), tracking the health of data pipelines across Sales, Marketing, and Logistics. 

The goal is to identify failures, monitor data volume anomalies, and assess the business impact of technical issues.

## 📊 Dashboard Previews

### Strategic Operations View
This view provides deep insights into data throughput trends and anomaly detection.
![Strategic View](./images/dashboard1.0.png)

### Operational Detail View
A focused view on workflow reliability and real-time alert severity distribution.
![Operational View](./images/dashboard2.0.png)

## 📁 Repository Structure
* `data/`: Raw dataset (CSV format).
* `images/`: Dashboard screenshots and previews.
* `scripts/`: DAX measures and transformation logic.
* `docs/`: Additional documentation.

## 📋 Key Metrics & KPIs
* **Availability Rate:** % of successful workflow executions.
* **Incident Heatmap:** Failure frequency by workflow and department.
* **Data Integrity:** Monitoring `percentage_change` to find sudden data drops.
* **Critical Alert Count:** Summary of high-severity operational issues.

## 💡 Strategic Insights
* **Marketing Pipeline:** Highest frequency of "Volume Drop" alerts, usually occurring on Mondays.
* **Sales Impact:** Revenue metrics are directly affected by the `sales_monitoring` workflow uptime.
* **Operational Health:** 85% of alerts are categorized as "Critical" or "High," requiring immediate dev attention.

## 🛠️ Tech Stack
* **BI Tool:** Power BI / Looker Studio
* **Data Prep:** Power Query / SQL
* **Logic:** DAX for advanced time-intelligence.

---
*Created by Brenda Espinosa*
