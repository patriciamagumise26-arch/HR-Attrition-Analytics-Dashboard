 HR Attrition Analytics Dashboard

A Power BI dashboard analyzing employee attrition across a 1,480-person workforce — built to identify which departments, roles, and working conditions are most associated with employees leaving.

## Summary

Using employee-level HR records, this dashboard surfaces where attrition risk concentrates so an HR or people-analytics team could prioritize retention efforts. Headline findings from the underlying data:

- **Overall attrition rate: 16.1%** across 1,480 employees.
- **Overtime is the strongest single signal**: employees working overtime leave at **30.6%**, nearly 3x the rate of those who don't (**10.4%**).
- **Younger employees are the highest flight risk**: the 18–25 age group has a **35.8%** attrition rate, dropping to **9.1%** for 36–45 year-olds before ticking back up slightly for 55+.
- **Sales has the highest departmental attrition (20.7%)**, followed by Human Resources (19.0%) and Research & Development (13.8%) — even though R&D is by far the largest department (967 of 1,480 employees).
- **Job satisfaction tracks inversely with attrition**: employees who rate satisfaction lowest (1/4) leave at 22.9%, compared to 11.3% for the most satisfied (4/4).

## Dashboard contents

Single-page report (1280×720) with 15 visuals:

| Visual | Shows |
|---|---|
| KPI cards (×5) | Total employees, average age, average monthly income, average years at company, overall attrition rate |
| Area chart | Attrition count by years at company (tenure trend) |
| Column chart | Attrition count by age group |
| Bar chart | Attrition count by job role |
| Bar chart | Attrition count by salary slab |
| Treemap | Attrition count by gender |
| Donut chart | Attrition count by education field |
| Pivot table | Attrition count by job role × job satisfaction |
| Slicer | Filter by department |

## Dataset

The workbook (`data/HR_Data.xlsx`) is structured as a small star schema:

- **HR_Data** (fact table, 1,480 rows) — one row per employee: demographics (age, gender, marital status), job details (role, department, job level, overtime), compensation (monthly income, salary slab, daily/hourly/monthly rate), satisfaction scores (job, environment, relationship, work-life balance — each 1–4), tenure fields (years at company, years in current role, years since last promotion, years with current manager), and the target field, `Attrition` (Yes/No).
- **Departments**, **Jobs**, **Education** — lookup tables joined to the fact table by ID, mapping numeric codes to readable labels (e.g., Department 1001 → "Research & Development").

This is a synthetic/public HR dataset (a version of the well-known IBM Watson Analytics employee-attrition dataset) 

**Data quality note:** the raw `Gender` column contains three distinct values instead of two — `Male`, `Female`, and `"Female"` (with literal stray quote characters from a source-formatting issue). 

## Tools

- **Power BI Desktop** — data modeling, DAX measures, report visuals
- **Power Query** — data shaping/cleaning from the source workbook
- **Excel** — source data



## How to view

1. Download `HR_Attrition_Analytics_Dashboard.pbix`.
2. Open it in [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/downloads) (free, Windows only).
3. The dashboard opens directly to the report page — use the Department slicer to filter.

## Author

**Patricia Magumise** — MS Applied Data Science, Clarkson University
[GitHub](https://github.com/patriciamagumise26-arch)
