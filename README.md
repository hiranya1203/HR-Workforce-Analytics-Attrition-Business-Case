# HR-Workforce-Analytics-Attrition-Business-Case
This project focuses on identifyin the root causes fo employee attrition, quantifying the financial impact, and delivering 3 actionable recommendations with a projected 754% ROI.
---

## Project Overview

This project analyses IBM's HR Analytics dataset (1,470 employees) to answer a real business problem:

**"The company has a 16.1% employee attrition rate — above the 10–12% industry average. Why are employees leaving, how much is it costing, and what can we do about it?"**

Unlike a standard data analysis project, this is built as a **Business Analyst deliverable** — the output is a business case with recommendations and ROI, not just charts.

---
## Tools Used

| Tool | What I used it for |
|---|---|
| **SQL** (MySQL Workbench) | Attrition analysis, root cause queries, cost calculations |
| **Excel** (Google Sheets) | Cost model, what-if scenario calculator, pivot table |
| **Tableau** (Tableau Desktop) | Interactive 3-view attrition dashboard |
| **PowerPoint** | 14-slide executive business case presentation |

---
## Dataset

- **Name:** IBM HR Analytics Employee Attrition Dataset
- **Source:** [Kaggle Link](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Size:** 1,470 employees | 35 columns
- **Departments:** Sales, Research & Development, Human Resources

> No Python cleaning required — the dataset is already clean. Analysis starts directly in SQL.

---
## SQL Analysis — 5 Queries

### Query 1 — Overall Picture
Calculated total employees, attrition count, attrition rate %, average salary, age, and tenure across the full workforce.

**Key result:** 237 out of 1,470 employees left — a 16.1% attrition rate costing $13.8M annually.

### Query 2 — Department & Job Role Breakdown
Grouped attrition by department and job role with average salary and job satisfaction per group.

| Department | Attrition Rate | Avg Salary |
|---|---|---|
| Sales | 20.6% | $8,846 |
| Human Resources | 19.0% | $11,163 |
| Research & Development | 13.8% | $9,078 |

**Highest risk job role:** Sales Representative at **39.8%** attrition.

### Query 3 — Root Cause Analysis
Broke down attrition by 3 key factors using separate GROUP BY queries combined with UNION ALL.

| Factor | Group | Attrition Rate |
|---|---|---|
| Age Group | Under 25 | 39.2% |
| Overtime | Works Overtime | 30.5% |
| Overtime | No Overtime | 10.4% |
| Job Satisfaction | Score 1 (lowest) | 22.8% |
| Job Satisfaction | Score 4 (highest) | 11.3% |

### Query 4 — Cost of Attrition Per Department
Calculated replacement cost (6 months salary) and productivity loss (3 months salary) per leaver, grouped by department.

- Cost per leaver: **$58,527**
- Total annual cost: **$13,870,899**

### Query 5 — Promotion Gap Analysis
Analysed whether years since last promotion correlates with attrition. Employees who had not been promoted in longer periods showed higher attrition rates.

---
## Excel — Cost Model

Built in Google Sheets with 2 sheets:

**Sheet 1 — Attrition Cost Calculator**

Input cells (yellow) feed into calculated outputs:

| Input | Value |
|---|---|
| Total Employees | 1,470 |
| Current Attrition Rate | 16.1% |
| Avg Monthly Salary | $6,503 |
| Replacement Cost Factor | 6 months |
| Productivity Loss Factor | 3 months |

| Output | Value |
|---|---|
| Employees Lost Per Year | 237 |
| Cost Per Leaver | $58,527 |
| Total Annual Cost | $13,870,899 |

**What-If Scenario Table:**

| Target Rate | Employees Saved | Money Saved |
|---|---|---|
| 14% | 31 | $1,814,337 |
| 13% | 46 | $2,692,242 |
| 11% | 75 | $4,389,525 |

**Sheet 2 — Department Pivot**
Pivot table from SQL output showing attrition rate, average salary, and headcount per department with conditional formatting (red/yellow/green).

---
## Tableau Dashboard

**3 views published on Tableau Public:**

**View 1 — Overview**
KPI cards (1,470 employees | 237 left | 16.1% rate) + attrition by department bar chart

**View 2 — Root Cause Analysis**
Attrition by Overtime | Job Satisfaction | Age Group — all colour coded red to green

**View 3 — Department Heatmap**
Job Role vs Department matrix showing attrition rate — Sales Representative (red, 39.8%) stands out clearly

> **Live Dashboard:** [https://public.tableau.com/views/hr_dashboard_17777123419810/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link]

---
## PowerPoint Business Case — 14 Slides

| Slide | Content |
|---|---|
| 1 | Title slide |
| 2 |  The Business Problem |
| 3 | Key Numbers at a Glance |
| 4 | Attrition by Department |
| 5 |Root Cause Analysis table |
| 6 | Cost of Attrition + what-if scenarios |
| 7 | At-Risk Employee Profile |
| 8 | 3 Recommendations |
| 9 | Expected Business Impact + ROI |
| 10 | Summary & Conclusion |
| 11 |Risks & Limitations | 
| 12 | Data Sources & Tools Used | 

---

## Key Business Insights

1. **Overtime is the #1 driver** — employees who work overtime leave at 30.5% vs 10.4% for others — 3x the rate
2. **Under-25s are the highest risk group** — 39.2% attrition, nearly double the company average
3. **Sales department needs urgent attention** — 20.6% attrition, Sales Representatives at 39.8%
4. **Low job satisfaction predicts leaving** — score 1 employees leave at 22.8% vs 11.3% for score 4
5. **Cost is $13.8M per year** — reducing attrition by just 5% saves $4.3M annually

---
## 3 Recommendations

| # | Recommendation | Owner | Timeline | Impact |
|---|---|---|---|---|
| 1 | Overtime Policy — cap mandatory OT, offer comp-off days | Department Managers + HR | 30 days | Reduce attrition ~2% |
| 2 | New Employee Support — 12-month buddy/mentor programme | HR Learning Team | 60 days | Reduce attrition ~2% |
| 3 | Satisfaction Surveys — quarterly anonymous surveys + action plans | HR Business Partners | 45 days | Reduce attrition ~1% |

**Projected ROI:** $4,389,525 savings ÷ ~$500,000 cost = **754% return in Year 1**

---
## Assumptions

- Replacement cost = 6 months of monthly salary (industry standard)
- Productivity loss = 3 months of monthly salary
- Industry attrition benchmark = 10–12%
- Dataset is synthetic (IBM simulation) — directional findings are valid

---

## Author

** P. Hiranya **


