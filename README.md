# HR Analytics Dashboard — Workforce Intelligence & Employee Explorer

![Tableau](https://img.shields.io/badge/Tableau-Desktop-blue?style=flat-square&logo=tableau)
![Dataset](https://img.shields.io/badge/Dataset-Synthetic-lightgrey?style=flat-square)
![Status](https://img.shields.io/badge/Status-Published-brightgreen?style=flat-square)
![Records](https://img.shields.io/badge/Records-8%2C950-teal?style=flat-square)

> An interactive, two-page Tableau dashboard built to answer real HR business questions — covering workforce composition, pay equity, attrition analysis, and individual employee exploration across a synthetic dataset of 8,950 records.

**[View Live Dashboard on Tableau Public →](https://public.tableau.com/app/profile/pratik.rajaram.more/viz/HRDashboard1_17755059903640/HRDashboard)**

---

## Overview

This project simulates the kind of HR analytics work done inside People Analytics and Workforce Intelligence teams. Rather than building a generic chart collection, the dashboard was designed around specific business questions — the kind an HR Director, CHRO, or Operations Manager would actually ask.

The dataset is entirely synthetic, generated using ChatGPT and Python's Faker library, and is intended for portfolio and learning purposes only.

---

## Dashboard Preview

### Page 1 — Overview
![HR Dashboard Overview](Overview.png)

> Workforce KPIs, hiring vs. attrition trends, department headcount, geographic distribution, demographic breakdowns, pay equity by education and gender, and age vs. salary scatter by job role.

### Page 2 — Employee Explorer
![HR Dashboard Details](Details.png)

> Full 8,950-record employee table with 8 cascading filter panels — enabling any employee segment to be isolated in under 10 seconds.

---

## User Story

> *As an HR manager, I want a comprehensive dashboard to analyze human resources data, providing both summary views for high-level insights and detailed employee records for in-depth analysis.*

---

## Requirements

### Summary View
The summary view is divided into three main sections: Overview, Demographics, and Income Analysis.

#### Overview
- Display the total number of hired employees, active employees, and terminated employees.
- Visualize the total number of hired and terminated employees over the years.
- Present a breakdown of total employees by department and job titles.
- Compare total employees between headquarters (HQ) and branches (New York is the HQ).
- Show the distribution of employees by city and state.

#### Demographics
- Present the gender ratio in the company.
- Visualize the distribution of employees across age groups and education levels.
- Show the total number of employees within each age group.
- Show the total number of employees within each education level.
- Present the correlation between employees's educational backgrounds and their performance ratings.

#### Income
- Compare salaries across different education levels for both genders to identify any discrepancies or patterns.
- Present how the age correlates with the salary for employees in each department.

### Employee Records View
- Provide a comprehensive list of all employees with necessary information such as name, department, position, gender, age, education, and salary.
- Users should be able to filter the list based on any of the available columns.

---

## Key Findings (Simulated Data)

| Finding | Detail |
|---|---|
| Gender pay gap at Bachelor's level | $74K avg (male) vs $66K avg (female) — 11% gap |
| Highest attrition department | Operations: 301 of 1,000 total exits (30%) |
| HQ vs Branch split | HQ carries 70% of headcount vs 30% across 5 branch states |
| Highest paid role | Finance Manager at ~$120K — no gender overlap at that tier |
| Education vs performance | PhD holders show highest concentration of Excellent ratings |

---

## Technical Features

### Page 1 — Overview Dashboard
| Feature | Detail |
|---|---|
| KPI Cards | Active employees, total hired, total terminated |
| Trend Chart | Hired vs. terminated over time (dual-line area chart) |
| Department Bar Chart | Headcount + attrition side-by-side with custom tooltip |
| Location Map | US state-level geographic distribution + HQ vs. Branch bar |
| Gender Donut Charts | Split by male / female with department filter |
| Education x Age Matrix | Bubble matrix — size encodes headcount |
| Education x Performance Matrix | Square heatmap with highlight encoding |
| Salary by Education + Gender | Diverging bar — male vs. female avg salary per education tier |
| Age vs Salary Scatter | Scatter plot by job role with labeled data points |

### Page 2 — Employee Explorer
| Feature | Detail |
|---|---|
| Full Record Table | 8,950 rows — ID, demographics, role, location, salary, status, tenure |
| Cascading Filter Panels | 8 column-level filter panels: Name, Age Group, Gender, Education, Job Title, Department, Location, Salary Range, Status, Tenure |
| Salary Range Slider | Continuous parameter control ($51K–$149K) |
| Tenure Slider | 0–11 years |
| Column Header Arrows | Click any header to expand/collapse that column's filter panel |

### Advanced Tableau Techniques Used
- **Dashboard Actions** — cross-filter interactions between all charts on Page 1
- **Calculated Fields** — custom salary aggregations, attrition rate calculations, gender pay gap computation
- **Custom Tooltips** — nested bar charts inside hover tooltips (department drill-down)
- **Parameter Controls** — salary range and tenure sliders on the Details page
- **Toggle Filter Panel** — Show/Hide filter bar using a boolean parameter + button action
- **Navigation Buttons** — seamless page switching between Overview and Details

---

## Dataset

| Attribute | Detail |
|---|---|
| Source | Synthetic — generated via ChatGPT prompting + Python Faker library |
| Records | 8,950 employees |
| Fields | Employee ID, Full Name, Gender, Age, Education Level, Department, Job Title, Salary, Location (City, State, HQ/Branch), Hire Date, Termination Date, Employment Status, Performance Rating |
| Purpose | Portfolio and learning only — no real employee data |

### Dataset Fields

```
EmployeeID       | Unique identifier
FullName         | Synthetic name (Faker)
Gender           | Male / Female
Age              | 22–65
EducationLevel   | High School / Bachelor / Master / PhD
Department       | Operations / Sales / Customer Service / IT / Marketing / Finance / HR
JobTitle         | Role within department
Salary           | Annual salary (USD)
City             | US city
State            | US state
Location         | HQ or Branch
HireDate         | Date of hire
TermDate         | Date of termination (null if active)
Status           | Active / Terminated
PerformanceRating| Excellent / Good / Satisfactory / Needs Improvement
```

---

## How to Use the Dashboard

### Overview Page
1. **Click any chart** to cross-filter the entire dashboard
2. **Toggle the filter panel** (top right) to show/hide Gender, Status, Location, and Hire Date slicers
3. **Hover over department bars** to see a nested breakdown by job title inside the tooltip
4. **Hover over map dots** to see city-level headcount

### Details Page
1. **Click any column header arrow** to expand that column's filter panel
2. **Use the salary slider** to filter by compensation range
3. **Use the tenure slider** to isolate employees by length of service
4. **Combine multiple filters** to isolate any employee segment in under 10 seconds

---

## Project Structure

```
hr-analytics-dashboard/
├── README.md
├── assets/
│   ├── overview.png          # Screenshot — Page 1
│   ├── details.png           # Screenshot — Page 2
│   ├── details_filters.png   # Screenshot — filter panel expanded
│   └── tooltip_preview.png   # Screenshot — custom tooltip
├── data/
│   └── hr_dataset.csv        # Synthetic employee dataset
└── dashboard/
    └── HR_Dashboard.twbx     # Packaged Tableau workbook
```

---

## Tools & Technologies

| Tool | Usage |
|---|---|
| Tableau Desktop | Dashboard design, calculated fields, actions, parameters |
| Tableau Public | Publishing and hosting |
| Python (Faker) | Synthetic dataset generation |
| ChatGPT | Dataset schema design and content generation |
| Excel | Initial data review and cleaning |

---

## Author

**Pratik More**
MS Business Analytics — University of Colorado Denver (Expected May 2026)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-pratikm0105-blue?style=flat-square&logo=linkedin)](https://linkedin.com/in/pratikm0105/)
[![Tableau Public](https://img.shields.io/badge/Tableau%20Public-Portfolio-orange?style=flat-square&logo=tableau)](https://public.tableau.com/app/profile/pratik.rajaram.more)
[![GitHub](https://img.shields.io/badge/GitHub-pratikmore-black?style=flat-square&logo=github)](https://github.com/pratikmore)

---

## Disclaimer

All data in this project is entirely synthetic and artificially generated for portfolio and educational purposes. It does not represent any real individuals, organizations, or employment records.
