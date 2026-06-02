# 🏥 Insurance Analytics Dashboard

> **Branch Performance & Sales Intelligence Platform** — An end-to-end analytics project tracking policy performance, brokerage revenue, and branch-level KPIs using Excel, SQL, Power BI, and Tableau.

---

## 📌 Project Overview

The Insurance Analytics Dashboard provides complete visibility into policy performance, brokerage activity, and account executive productivity across branches. It enables underwriters, claims teams, and executives to make informed, data-driven decisions.

### 🎯 Problem Statement

The organization lacked a unified view to track branch-level performance in real-time. Key challenges included:

- 📂 Fragmented data across Excel sheets and CRM systems
- 🎯 No clear alignment between individual targets and actual achievements
- 📉 Inability to track meetings, opportunities, and win ratios
- 🔍 Limited visibility into branch-level KPIs like invoice count and conversion ratios
- 🚨 Difficulty identifying top performers and lagging opportunities

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| ![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat-square&logo=microsoft-excel&logoColor=white) | Data cleaning, transformation & initial dashboard |
| ![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white) | Database setup, normalization & KPI queries |
| ![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black) | Interactive dashboard development |
| ![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat-square&logo=tableau&logoColor=white) | Advanced data visualization |

---

## 📊 Key KPIs Tracked

- 💰 **Total Brokerage Revenue** — across branches and product groups
- 📋 **Policy Status** — Active vs Inactive policies
- 🔄 **Renewal Rate** — New, Cross-Sell, and Renewal breakdown
- 👤 **Account Executive Performance** — individual targets vs achievement
- 🏢 **Branch-Level Analysis** — Ahmedabad and other branches
- 📦 **Product Group Performance** — Marine, Fire, Liability, Employee Benefits, Engineering

---

## 🔍 Data Sources

| Table | Description |
|-------|-------------|
| **Brokerage** | Client-wise policy brokerage records |
| **Target Sheets** | Branch and executive-level targets |
| **Invoice Reports** | Invoice count and amounts |
| **Meetings Data** | CRM meetings and opportunity stages |
| **CRM Opportunities** | Sales funnel and conversion tracking |

---

## 🔑 Key SQL Queries

### Total Brokerage by Product Group
```sql
SELECT product_group, 
       ROUND(SUM(Amount), 2) AS total_brokerage
FROM brokerage
GROUP BY product_group
ORDER BY total_brokerage DESC;
```

### Active vs Inactive Policy Count
```sql
SELECT policy_status, 
       COUNT(*) AS policy_count,
       ROUND(SUM(Amount), 2) AS total_amount
FROM brokerage
GROUP BY policy_status;
```

### Top Performing Account Executives
```sql
SELECT exe_name,
       COUNT(*) AS total_policies,
       ROUND(SUM(Amount), 2) AS total_brokerage
FROM brokerage
GROUP BY exe_name
ORDER BY total_brokerage DESC
LIMIT 5;
```

### Revenue by Business Type
```sql
SELECT income_class,
       COUNT(*) AS count,
       ROUND(SUM(Amount), 2) AS total_revenue
FROM brokerage
GROUP BY income_class
ORDER BY total_revenue DESC;
```

---

## 📅 Project Timeline

| Date | Task |
|------|------|
| Week 1 | Project Kick-off & Data Understanding |
| Week 2 | Data Cleaning & Excel Dashboard |
| Week 3 | SQL Integration & KPI Implementation |
| Week 4 | Power BI & Tableau Dashboard Development |
| Week 5 | QA, Validation & Final Presentation |

---

## 💡 Key Insights

- 🏆 **Marine** and **Employee Benefits** are the top revenue-generating product groups
- 📈 **Renewal** policies make up the majority of brokerage income
- 🏢 **Ahmedabad branch** handles the highest volume of policies
- 🔁 **Cross-sell** opportunities show strong revenue potential in Global Client Network

---

## 👤 Author

**Chandu Manikanta**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/polnati-chandu-manikanta-narasimha-0b4802259)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=flat-square&logo=github&logoColor=white)](https://github.com/chandu2627)

---

<p align="center">⭐ If you found this project helpful, please give it a star!</p>
