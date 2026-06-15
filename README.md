# 🛡️ Insurance Analytics Dashboard
**Sales & Renewal Performance Dashboard** — An end-to-end analytics project tracking insurance sales funnel performance, renewal rates, and cross-sell opportunities using SQL, Power BI, and Tableau.

---

## 📌 Project Overview
Built during my Data Analyst Internship at **AI Variant**, this project analyzes 5,000+ insurance sales and renewal records to track funnel performance, identify drop-off stages, and surface cross-sell opportunities for business growth.

---

## 🎯 Problem Statement
Insurance sales teams often struggle to identify:
- 📉 Where leads drop off in the sales funnel
- 🔄 Which customers are likely to renew vs. lapse
- 💰 What's driving (or hurting) revenue contribution and conversion rate
- 🎯 Which customer segments offer the best cross-sell opportunities

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| SQL | KPI calculation — conversion rate, renewal rate, revenue contribution |
| Power BI (DAX, Data Modeling) | Interactive funnel and performance dashboard |
| Tableau | Alternate dashboard for cross-platform reporting |

---

## 📊 Dataset

| Field | Details |
|-------|---------|
| Records | 5,000+ sales and renewal records |
| Fields | Customer ID, policy type, sales stage, renewal status, revenue, lead source |
| Source | AI Variant internship dataset |

---

## 🔑 Key Analysis

### 1. Conversion & Renewal Rate (SQL)
```sql
SELECT 
    ROUND(SUM(CASE WHEN status = 'Converted' THEN 1 ELSE 0 END) 
        / COUNT(*) * 100, 2) AS conversion_rate,
    ROUND(SUM(CASE WHEN renewal_status = 'Renewed' THEN 1 ELSE 0 END) 
        / COUNT(*) * 100, 2) AS renewal_rate
FROM insurance_sales;
```

### 2. Revenue Contribution by Policy Type
```sql
SELECT policy_type,
       SUM(revenue) AS total_revenue,
       ROUND(SUM(revenue) / (SELECT SUM(revenue) FROM insurance_sales) * 100, 2) AS revenue_pct
FROM insurance_sales
GROUP BY policy_type
ORDER BY total_revenue DESC;
```

---

## 💡 Key Insights

- 📊 Tracked conversion rate, renewal rate, and revenue contribution across the sales funnel
- 🔻 Identified key drop-off stages in the lead-to-customer pipeline
- 🔄 Surfaced cross-sell opportunities through EDA and trend analysis on customer segments
- 📈 Delivered stakeholder dashboards for pipeline tracking, lead prioritization, and performance monitoring

---

## 📋 Dashboard Features

- KPI Cards: Conversion Rate, Renewal Rate, Total Revenue, Active Policies
- Funnel Chart: Lead-to-customer conversion stages
- Bar Chart: Revenue by Policy Type
- Trend Analysis: Renewal trends over time
- Slicers: Policy type, lead source, region

---

## 📁 Repository Files

| File | Description |
|------|-------------|
| insurance_sales_data.csv | Raw sales and renewal dataset |
| Insurance_Analysis.sql | SQL queries for KPI calculations |
| Insurance_Dashboard.pbix | Power BI dashboard file |
| Insurance_Dashboard_Tableau.twbx | Tableau dashboard file |
| Insurance_Dashboard.pdf | Dashboard PDF export |

---

## 👤 Author
**Chandu Manikanta**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?logo=linkedin)](https://www.linkedin.com/in/chandumanikanta/) [![GitHub](https://img.shields.io/badge/GitHub-black?logo=github)](https://github.com/chandu2627)
