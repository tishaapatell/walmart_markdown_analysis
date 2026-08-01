# Walmart Markdown & Promotion Effectiveness Analysis

**Tech stack:** SQL · Python · Tableau

Analysis of Walmart promotional markdowns across 45 stores to measure the true sales impact of markdown spend, isolate it from store- and department-level noise, and recommend where budget should be reallocated.

---

## Overview

Retailers pour money into promotional markdowns without always knowing which departments actually return value on that spend. This project integrates real Walmart sales data, builds a fixed-effects regression to separate the genuine effect of markdowns from underlying store and department differences, and translates the results into a Tableau dashboard for budget decisions.

## Data

- **Three integrated sources** of real Walmart sales data
- **45 stores** covered
- **420K+ records** after joining and cleaning

Source tables were merged in SQL, then loaded into Python for modeling.

## Methodology

1. **Data integration (SQL):** Joined three raw sources into a single analysis-ready table, resolving keys across stores, departments, and time.
2. **Cleaning & preparation (Python):** Handled missing values, standardized fields, and structured the panel for regression.
3. **Fixed-effects regression (Python):** Modeled sales as a function of promotional markdowns while controlling for store and department fixed effects. This isolates the true markdown effect rather than attributing it to structural differences between stores or departments.
   - Explanatory power rose from **R² = 0.06** (naive model) to **R² = 0.68** (fixed-effects model).
4. **ROI analysis:** Quantified markdown ROI by department — return in sales per markdown dollar ranged from **$1.24 down to near $0**.
5. **Visualization (Tableau):** Built a dashboard surfacing markdown ROI by department and recommending budget reallocation toward the highest-return departments.

## Key Findings

- Controlling for store and department fixed effects more than **10x'd** the model's explanatory power (R² 0.06 → 0.68), showing that most raw variation was structural, not driven by markdowns.
- Markdown effectiveness varies dramatically by department: the best returned **$1.24 in sales per markdown dollar**, while others returned **close to nothing**.
- Reallocating markdown budget toward the highest-return departments is the clearest lever for improving overall promotional ROI.

## Tableau Dashboard

The Tableau dashboard lets stakeholders:

- Compare markdown ROI across departments at a glance
- Identify high- and low-return departments
- Explore the recommended budget reallocation

## Requirements

- Python 3.x (pandas, statsmodels / linearmodels, numpy)
- A SQL environment for the integration step
- Tableau Desktop (or Tableau Public) to open the dashboard
