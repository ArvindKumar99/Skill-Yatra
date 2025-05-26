# 🚀 Skill Yatra – Sales Analytics Dashboard

Welcome to **Skill Yatra**, a fictitious ed-tech company created for this data analytics project. Skill Yatra sells professional courses and employs a team of Sales Representatives and Senior Sales Reps. This project simulates their operations by analyzing their sales performance, shift patterns, and rep demographics.

---

## 🔍 Project Overview

This project demonstrates a complete data pipeline from **data creation in Excel**, **ETL processing using Alteryx Designer**, to **dashboard visualization in Power BI**. It showcases how raw data can be transformed into dynamic insights for business decision-making.

---

## 🧰 Tools & Technologies Used

| Tool             | Purpose                                      |
|------------------|----------------------------------------------|
| **Excel**         | Created synthetic datasets (1000 sales records) |
| **Alteryx Designer** | Data blending, transformation, and ETL         |
| **Power BI**      | Interactive dashboard & KPIs visualization |
| **GitHub**        | Project version control & documentation     |

---

## 📁 Data Sources

All datasets were manually created in **Excel** and exported as CSV files:

1. **`Raw_data`**
2.   Sales transactions (Employee ID, Number Dialled, Call Duration, Call Status, Sales Amount)
3.   Sales Rep details (Employee ID, Name, Age, Designation)
4.   Time dimension (Employee ID, Date, Shift Timings)

These were cleaned, joined, and transformed using **Alteryx Designer** to produce a unified dataset for dashboarding.

---

## 🔄 ETL Process with Alteryx

The Alteryx workflow (`ETL_SkillYatra_workflow`) performs:

- Data cleaning & formatting
- Joins across Rep ID and Date fields
- Creation of calculated fields (e.g., shift categorization)
- Exporting the final dataset: `SkillYatra_ETL`

---

## 📊 Power BI Dashboard Highlights

The Power BI file (`SkillYatra_dashboard.pbix`) includes:

- **Sales by Rep, Region, Designation, and Shift**
- **Cards** for:
  - `Total Sales` (ignores all filters)
  - `Rep Sales` (responds to slicers)
- **Pie Charts and Gauge Chart** for:
  - individual sales to team sales
- **Trend Graph** for:
  - Sales `trends` based on `call durations` 
- **Slicers & Filters** for:
  - `Rep Name`
- Clean and intuitive layout for interactive exploration

---

## ⚙️ Measures Created in Power BI

```DAX
Total_Sales = CALCULATE(SUM(sales[Amount]), ALL(sales))

Rep_Sales = SUM(sales[Amount])
