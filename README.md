📊 Employee Attendance vs Productivity Analysis

**An Excel & Power Query-driven HR analytics dashboard uncovering the relationship between employee attendance, sick leaves, and productivity across departments.**

Overview

This project analyzes an HR dataset of **100,000 employees** to understand whether — and how — **attendance patterns and sick leave usage** relate to **employee productivity (performance score)**. The company had noticed that some employees were frequently absent, but had no formal, data-driven way of knowing whether this was actually hurting performance, or which departments needed HR intervention.

Using **MS Excel and Power Query**, the raw HR data was cleaned, transformed, and modeled into an interactive, single-page dashboard with slicers, KPIs, and department-level breakdowns that management can use for decision-making — without needing to read a single spreadsheet row.

Business Problem

- Attendance data and performance data were tracked separately and never analyzed together.
- Management could not answer: *Is absenteeism actually hurting productivity? Which departments and risk bands need the most attention?*
- Existing reporting was static, manual, and non-interactive — making it slow to spot patterns or act on them.

**Goal:** Build a single interactive dashboard that lets HR/management filter by department, job title, gender, and attendance risk band, and instantly see attendance, performance, and sick-leave trends.

Dataset

| Detail | Description |
|---|---|
| **Source** | Kaggle — Employee Attendance & Productivity dataset |
| **Volume** | 100,000 employee records |
| **Format** | Raw CSV → cleaned & modeled in Excel |
| **Key Columns** | `Employee_ID`, `Department`, `Gender`, `Age`, `Job_Title`, `Hire_Date`, `Years_At_Company`, `Performance_Score`, `Monthly_Salary`, `Work_Hours_Per_Week`, `Projects_Handled`, `Overtime_Hours`, `Sick_Days`, `Risk_Band`, `Attendance_Rate`, `Remote_Work_Frequency`, `Team_Size`, `Training_Hours`, `Promotions`, `Employee_Satisfaction_Score` |
| **Departments Covered** | Customer Support, Engineering, Finance, HR, IT, Legal, Marketing, Operations, Sales |
| **Job Titles** | Analyst, Consultant, Developer, Engineer, Manager, Specialist, Technician |
| **Risk Bands** | Critical, High, Medium, Low (calculated from attendance rate) |

`Attendance_Rate` was engineered from raw absence data using the formula:
```
Attendance_Rate = ((520 − Total_Absent_Hours) / 520) × 100
```
(520 represents standard annual working hours used as the attendance baseline.)

Tools & Technologies

- **MS Excel 2024** — data modeling, pivot tables, dashboard design
- **Power Query** — data cleaning, transformation, error handling
- **Pivot Tables & Pivot Charts** — aggregation and visualization
- **Slicers** — interactive filtering (Department, Gender, Job Title, Risk Band, Performance Score)
- **DAX-style calculated fields / Excel formulas** — KPI and risk-band calculations

Project Workflow

1. **Data Collection** — Sourced raw employee attendance dataset from Kaggle.
2. **Data Cleaning (Power Query)** — Removed duplicates, handled missing/incorrect values, standardized data types.
3. **Data Transformation** — Engineered `Attendance_Rate` and `Risk_Band` fields from raw absence data.
4. **Data Modeling** — Structured cleaned data into a `Raw_Data` table feeding multiple pivot tables.
5. **Analysis (Pivot Tables)** — Built department-wise performance, attendance, sick-days, and risk-band summaries.
6. **Visualization** — Created bar charts, line charts, and horizontal bar charts for each metric.
7. **Dashboard Assembly** — Combined all visuals into a single dark-themed dashboard with KPI cards and slicers.
8. **Testing & Finalization** — Verified slicer interactivity and KPI accuracy before finalizing.

## 🖥️ Dashboard Preview

![Dashboard Overview](Images/dashboard_overview.png)

*Interactive Excel dashboard — filterable by Department, Job Title, Gender, Risk Band, and Performance Score.*

## 📌 Key KPIs

| Metric | Value |
|---|---|
| Total Employees | **100,000** |
| Average Performance Score | **3.00** / 5 |
| Average Satisfaction Score | **3.00** / 5 |
| Average Attendance Rate | **97.30%** |
| Average Sick Days | **7.02 days** |

## 💡 Key Insights

1. **Attendance rate is remarkably consistent across departments** (98.63%–98.67%), meaning attendance alone is not a differentiator of department performance — the gaps lie elsewhere.
2. **Performance scores are also tightly clustered** (2.98–3.01 across departments), with Marketing and Operations scoring marginally highest (3.01) and Engineering, IT, and Legal marginally lowest (2.98).
3. **Attendance risk band does not strongly predict performance.** Average performance score by risk band comes out nearly identical:
   - Critical risk: ~3.02 avg. performance (6,729 employees)
   - Medium risk: ~3.00 avg. performance (26,447 employees)
   - Low risk: ~2.99 avg. performance (26,764 employees)
   - High risk: ~2.99 avg. performance (40,060 employees)
   - This challenges the assumption that "high attendance risk = low productivity" — the data suggests other factors (training, workload, engagement) likely play a bigger role than raw attendance.
4. **High risk band is the largest group** (40,060 employees, 40% of the workforce), making it the segment with the greatest *volume* impact even though its average performance isn't the lowest — a strong candidate for proactive HR attention.
5. **Sick days average 7.01 per employee** against an average performance score of 3.00 — sick leave alone doesn't appear to be dragging performance down at the aggregate level, but department-level drill-down (via slicers) can surface outliers.

> 💬 *Takeaway for HR:* Because attendance and risk band show only a weak relationship with performance in this dataset, HR strategy should look beyond attendance monitoring alone — e.g., training hours, workload (overtime/projects handled), and engagement/satisfaction scores — to meaningfully improve productivity.

## 🧩 Excel Skills Demonstrated

- Power Query for ETL (Extract, Transform, Load)
- Complex Excel formulas (attendance rate calculation, array formulas)
- Pivot Tables & Pivot Charts for multi-dimensional analysis
- Interactive Slicers for cross-filtering multiple visuals
- Dashboard design principles (KPI cards, consistent theming, layout hierarchy)
- Working with large datasets (100K rows) efficiently in Excel

## 📂 Repository Structure

```
Employee-Attendance-vs-Productivity-Analysis/
│
├── README.md                                        # Project documentation (this file)
│
├── Dashboard/
│   └── Employee_Attendance_Productivity_Dashboard.xlsx   # Full Excel workbook (raw data + pivots + dashboard)
│
├── Documentation/
│   ├── Project_Report.docx                          # Detailed project report (abstract, methodology, conclusion)
│   └── Project_Presentation.pptx                     # Slide deck summary of the project
│
└── Images/
    └── dashboard_overview.png                        # Dashboard screenshot for quick preview
```

## 🚀 How to Use This Project

1. Clone or download this repository.
2. Open `Dashboard/Employee_Attendance_Productivity_Dashboard.xlsx` in Excel (2016 or later, Power Query support required).
3. Use the slicers on the right (Department, Gender, Job Title, Risk Band, Performance Score) to explore the data interactively.
4. Refer to `Documentation/Project_Report.docx` for the full write-up, or `Project_Presentation.pptx` for a quick walkthrough.

## 🔮 Future Improvements

- Rebuild the dashboard in **Power BI** for richer interactivity and web publishing.
- Add **real-time data refresh** via Power Query connections.
- Apply **predictive analytics / ML** to forecast attendance risk and its downstream productivity impact.
- Introduce **drill-through pages** for employee-level root-cause analysis.
- Design a **mobile-friendly** version of the dashboard.

## 👩‍💻 Author

**Kamatchi Keerthika**
Data Analyst | SQL • Excel • Power BI • Tableau • Python
📍 Chennai, India

*This project is part of a self-directed data analytics portfolio built to demonstrate end-to-end HR analytics capability — from raw data to business-ready insights.*

---

⭐ If you found this project useful or interesting, consider starring the repository!
