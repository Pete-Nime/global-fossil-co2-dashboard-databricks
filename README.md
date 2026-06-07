# 🌍 Global Fossil CO₂ Emissions Analysis Dashboard (Databricks SQL)

## 📌 Project Overview

This project analyzes global fossil fuel carbon dioxide (CO₂) emissions using Databricks SQL and interactive dashboards.

The objective was to transform raw emissions data into meaningful business intelligence insights by applying SQL analytics, KPI design, data exploration, and dashboard development techniques.

The final solution provides:

- Executive-level KPI reporting
- Global emissions trend analysis
- Country-level emission comparisons
- Per-capita emission analysis
- Historical emissions growth insights
- Interactive country-level exploration

This project demonstrates practical Data Analyst and Business Intelligence skills using Databricks SQL.

---

# 🎯 Project Goals

The purpose of this project was to:

- Learn Databricks SQL
- Practice real-world SQL analytics
- Build professional dashboards
- Develop KPI-driven reporting
- Explore global climate datasets
- Create portfolio-ready Business Intelligence solutions

---

# 🌎 Why This Project Matters

Climate change is one of the most important global challenges facing humanity.

Governments, businesses, environmental organizations, and researchers rely on emissions data to:

- Monitor environmental impact
- Track sustainability targets
- Identify major emission sources
- Compare country performance
- Support policy decisions
- Understand long-term climate trends

This dashboard provides a clear and visual way to understand these trends.

---

# 🛠 Tools & Technologies Used

| Tool | Purpose |
|--------|---------|
| Databricks SQL | Data analysis and querying |
| Databricks Dashboards | Interactive dashboard creation |
| SQL | Data manipulation and analytics |
| GitHub | Version control and portfolio showcase |
| LinkedIn | Professional project presentation |

---

# 📂 Dataset Overview

The dataset contains global fossil fuel emissions data.

### Key Fields

| Column |
|----------|
| country |
| year |
| total_emissions |
| per_capita_emissions |
| coal_emissions |
| oil_emissions |
| gas_emissions |
| cement_emissions |
| flaring_emissions |
| other_emissions |
| historical_period |
| country_type |

The dataset covers:

- Hundreds of countries
- Historical emission records
- Multiple emission sources
- Global and country-level statistics

---

# 📊 Dashboard Structure

The dashboard consists of three professionally designed pages.

---

# Page 1 — Executive Overview

## Purpose

Provide a high-level summary of global emissions performance.

---

## KPI 1 — Global CO₂ Emissions

Displays total global fossil fuel emissions for 2021.

### Result

37,124 MtCO₂

---

## KPI 2 — Global CO₂ Per Capita

Displays average emissions per person globally.

### Result

4.69 tCO₂/person

---

## KPI 3 — Highest Emitting Country

Identifies the largest contributor to global emissions.

### Result

China

11,472 MtCO₂

---

## Supporting Visualizations

### Largest Emission Sources

Compares:

- Coal
- Oil
- Gas

Purpose:

Identify which fossil fuel contributes the most emissions globally.

---

### Top 10 CO₂ Emitting Countries (2021)

Ranks countries by total emissions.

Purpose:

Identify the largest contributors to global emissions.

---

### Global CO₂ Emissions Trend (1750–2021)

Shows historical emissions growth over time.

Purpose:

Understand long-term climate impact.

---

# Page 2 — Emission Analysis

## Purpose

Analyze historical and comparative emissions trends.

---

## Top 10 CO₂ Emitters Per Capita (2021)

Displays countries producing the highest emissions per person.

Purpose:

Measure environmental intensity rather than total emissions.

---

## Global CO₂ Growth by Decade

Shows average emissions growth by decade.

Purpose:

Understand long-term acceleration in emissions.

---

## Average Emissions by Historical Period

Compares:

- Pre Industrial
- Industrial Growth
- Modern Era
- Climate Era

Purpose:

Understand emissions across major historical periods.

---

# Page 3 — Country Details

## Purpose

Provide country-level exploration and detailed analysis.

---

## Interactive Country Filter

Allows users to select individual countries.

Examples:

- China
- USA
- Australia
- India
- Germany

---

## Top 20 CO₂ Emitting Countries Table

Displays:

- Total emissions
- Per-capita emissions
- Coal emissions
- Oil emissions
- Gas emissions

Purpose:

Enable detailed country-level analysis.

---

## Countries with Largest Emission Growth

Displays countries with the largest increase in emissions over time.

Purpose:

Identify rapidly growing emitters.

---

# SQL Techniques Used

---

## 1. Data Filtering

```sql
SELECT *
FROM globalimpact.co2_dashboard
WHERE year = 2021;
```

### Purpose

Limits analysis to a specific reporting year.

---

## 2. Excluding Aggregate Records

```sql
SELECT *
FROM globalimpact.co2_dashboard
WHERE country NOT IN ('Global', 'International Transport');
```

### Purpose

Prevents global totals from distorting country comparisons.

---

## 3. Sorting Results

```sql
SELECT country, total_emissions
FROM globalimpact.co2_dashboard
ORDER BY total_emissions DESC;
```

### Purpose

Ranks countries from highest to lowest emissions.

---

## 4. Top N Analysis

```sql
SELECT country, total_emissions
FROM globalimpact.co2_dashboard
ORDER BY total_emissions DESC
LIMIT 10;
```

### Purpose

Returns the Top 10 emitting countries.

---

## 5. Aggregation Functions

```sql
SELECT
    SUM(total_emissions) AS global_emissions
FROM globalimpact.co2_dashboard
WHERE country = 'Global';
```

### Purpose

Calculates overall emissions totals.

---

## 6. Average Calculations

```sql
SELECT
    AVG(total_emissions) AS avg_emissions
FROM globalimpact.co2_dashboard;
```

### Purpose

Calculates average emissions.

---

## 7. Common Table Expressions (CTEs)

```sql
WITH emissions_2021 AS (
    SELECT *
    FROM globalimpact.co2_dashboard
    WHERE year = 2021
)
SELECT *
FROM emissions_2021;
```

### Purpose

Creates reusable query logic.

---

## 8. Joins

```sql
WITH emissions_2021 AS (
    SELECT country, total_emissions
    FROM globalimpact.co2_dashboard
    WHERE year = 2021
),
emissions_2000 AS (
    SELECT country, total_emissions
    FROM globalimpact.co2_dashboard
    WHERE year = 2000
)

SELECT
    e21.country,
    e21.total_emissions - e00.total_emissions AS growth
FROM emissions_2021 e21
JOIN emissions_2000 e00
ON e21.country = e00.country;
```

### Purpose

Compares emissions across years.

---

## 9. Growth Analysis

```sql
ROUND(
    e21.total_emissions -
    e00.total_emissions,
    0
) AS growth
```

### Purpose

Measures emission increases over time.

---

## 10. Data Quality Checks

```sql
SELECT *
FROM globalimpact.co2_dashboard
WHERE total_emissions IS NOT NULL;
```

### Purpose

Removes incomplete records.

---

# 🔍 Key Insights Discovered

## Largest Emission Source

Coal remains the largest contributor to global fossil fuel emissions.

---

## Highest Emitting Country

China is currently the world's largest emitter.

---

## Highest Per-Capita Emitters

Several smaller countries produce significantly higher emissions per person than many larger economies.

---

## Historical Trend

Global emissions accelerated rapidly following the Industrial Revolution.

---

## Modern Growth

The majority of emissions growth occurred after 1950.

---

# 💡 Skills Demonstrated

## Databricks

- SQL Editor
- Query Development
- Dashboard Building
- KPI Design
- Interactive Filters
- Dashboard Pages
- Data Exploration

---

## SQL

- SELECT
- WHERE
- ORDER BY
- LIMIT
- SUM
- AVG
- ROUND
- CTEs
- JOINs
- Aggregations

---

## Data Analytics

- KPI Development
- Trend Analysis
- Comparative Analysis
- Ranking Analysis
- Dashboard Storytelling
- Data Visualization

---

# 📚 What I Learned

Through this project I learned:

- How Databricks SQL differs from traditional SQL environments.
- How to transform raw data into actionable insights.
- How to design executive-level KPIs.
- How to structure multi-page dashboards.
- How to perform historical trend analysis.
- How to create interactive dashboards.
- How to communicate insights effectively through visualization.

---

# 🚀 Future Improvements

Potential future enhancements include:

- Geographic map visualizations
- Carbon intensity calculations
- Renewable energy comparisons
- Forecasting future emissions
- Machine Learning prediction models
- Automated dashboard refreshes

---

# 🏆 Project Outcome

This project successfully transformed raw global emissions data into a professional Databricks dashboard consisting of:

✅ 3 Dashboard Pages

✅ Executive KPI Reporting

✅ Interactive Country Filtering

✅ Historical Trend Analysis

✅ Top Emitter Analysis

✅ Country-Level Exploration

✅ Business Intelligence Storytelling

✅ Portfolio-Ready Dashboard
https://dbc-3019ec54-2294.cloud.databricks.com/dashboardsv3/01f1609937d01423954e5bcdb176c959/published?o=7474648734023344


---

# 👨‍💻 Author

**Peter Nime**

Data Analyst | Data Scientist | AI & Data Engineering Enthusiast

### Connect With Me

- GitHub: https://github.com/pete-nime
- LinkedIn: https://www.linkedin.com/in/peter-nime/
- Company: Areca Tech Limited

---

*"Turning data into insights and insights into action."*
