**Project Title:**
**HealthGap India — District Healthcare & Health Risk Analysis**

## Overview

**HealthGap India** is an end-to-end healthcare analytics project that evaluates district-level healthcare, nutrition, maternal and child health, and health-risk indicators across India.

The project transforms NFHS-5 district-level data into a structured analytical dataset, develops a direction-aware **HealthGap Score**, identifies district and state-level disparities, and presents the findings through an interactive Power BI dashboard.

## Business Problem

Healthcare performance varies significantly across districts and states. Decision-makers need a structured way to identify healthcare gaps, compare geographic performance, and prioritize areas requiring attention.

> **Which districts have the largest healthcare gaps, what factors are associated with those gaps, and where should healthcare improvement efforts be prioritized?**

This project addresses that problem by combining multiple healthcare indicators into a standardized district-level analytical framework.

## Key Business Questions

* Which districts have the highest and lowest overall healthcare performance?
* Which states perform better or worse relative to others?
* Which districts fall below their state average?
* Where are the largest healthcare disparities?
* Which healthcare indicators show the greatest variation across districts?
* What relationships exist between maternal, child, nutrition, and healthcare-access indicators?

## Dataset

**Source:** NFHS-5 India District Factsheet Data (2019–2021), Government of India.

### Dataset Structure

| Attribute              | Value |
| ---------------------- | ----: |
| District-level records |   706 |
| Unique districts       |   698 |
| States/UTs             |    36 |
| Original indicators    |   107 |
| Core indicators        |    50 |
| Supporting indicators  |    49 |
| Excluded indicators    |     8 |


Special values such as `*` and parenthesized estimates were handled according to the source data conventions.

## Methodology

1. Data loading and profiling
2. Data-quality assessment
3. Special-value handling
4. Column-name standardization
5. Data type conversion
6. Indicator categorization
7. Core/supporting indicator selection
8. Exploratory data analysis
9. KPI and direction framework
10. Direction-aware normalization
11. HealthGap Score calculation
12. District and state comparison
13. Business insight generation
14. Power BI dashboard development

## KPI Framework

The 50 core indicators were classified into three scoring directions:

* **Positive:** Higher values indicate better performance.
* **Negative:** Higher values indicate poor performance.
* **Context:** Indicators used for interpretation but excluded from the composite score.

The final framework contains:

* **27 Positive indicators**
* **15 Negative indicators**
* **8 Context indicators**

## HealthGap Score

The HealthGap Score is a **relative, direction-aware composite score from 0–100**.

For positive indicators:

`Score = (Value − Minimum) / (Maximum − Minimum) × 100`

For negative indicators, the scale is reversed so that better outcomes receive higher scores:

`Score = (Maximum − Value) / (Maximum − Minimum) × 100`

The district HealthGap Score is calculated as the mean of available scores across the **42 scored indicators**.

A minimum **80% indicator coverage** threshold was used for reliable ranking.

## Key Findings

* **693 of 706 districts** met the reliability threshold.
* District HealthGap Scores ranged from **39.23 to 80.28**.
* Average district score was approximately **62.10**.
* **361 districts** performed above their state average.
* **329 districts** performed below their state average.
* **Puducherry** had the highest state-level HealthGap Score.
* **Bihar** had the lowest state-level HealthGap Score.
* **Mahe (Puducherry)** had the highest reliable district score.
* **Tuensang (Nagaland)** had the lowest district score.
* Maternal Care and Institutional Births showed a **strong positive association (r = 0.599)**.
* Maternal Care and Child Stunting showed a **moderate negative association (r = -0.360)**.

> Correlations represent associations and do not establish causation.

## Recommendations

* Prioritize low-performing districts
* Integrate maternal and child-health monitoring
* Focus on within-state disparities
* Strengthen maternal-care pathways
* Use the model for prioritization, not causal decision-making

## Power BI Dashboard

The Power BI dashboard provides interactive analysis of:

* National healthcare performance
* State-level comparisons
* District rankings
* HealthGap Score
* District-vs-state performance
* Indicator-level healthcare gaps
* Geographic and healthcare-category analysis

## Tools & Technologies

* **Python**
* **Pandas**
* **NumPy**
* **Power Query**
* **Power BI**
* **Google Colab**
* **Git & GitHub**
* **Microsoft Word**

## Project Workflow

```text
Raw Healthcare Data
        ↓
Data Profiling
        ↓
Data Cleaning & Standardization
        ↓
Indicator Classification
        ↓
KPI Framework
        ↓
HealthGap Score
        ↓
District Ranking
        ↓
State-Level Analysis
        ↓
Power Query Transformation
        ↓
Power BI Data Model
        ↓
Interactive Dashboard
        ↓
Business Insights
        ↓
Recommendations
```

## Repository Structure

```text
HealthGap-India/
│
├── data/
│   ├── raw/
│   └── processed/ 
│           ├── healthgap_core_dataset.csv
│           ├── healthgap_supporting_dataset.csv
│           ├── healthgap_data_dictionary.csv
│           ├── healthgap_kpi_master.csv
│           ├── healthgap_district_scores.csv
│           ├── healthgap_state_summary.csv
│           ├── healthgap_indicator_master.csv
│           ├── healthgap_recommendations.csv
│           └── healthgap_priority_districts.csv
│
├── notebooks/
│   └── HealthGap_India.ipynb  
│   
├── powerbi/
│   └── HealthGap_India_Dashboard.pbix
│
├── documentation/
│   └── HealthGap_India_Project_Documentation.docx
│
├── README.md
└── .gitignore
```

## Limitations

* The HealthGap Score is a **relative analytical measure**, not a clinical or official healthcare index.
* Min-max normalization depends on the observed district-level range.
* Some indicators contain suppressed or low-sample observations.
* Correlation analysis does not imply causation.
* Context indicators are excluded from the composite score.
* The analysis uses NFHS-5 data from **2019–2021** and therefore does not represent current healthcare conditions.

## Future Improvements

* Incorporate newer healthcare datasets for time-series analysis.
* Add district-level socioeconomic and infrastructure variables.
* Develop predictive models for identifying high-risk districts.
* Introduce configurable indicator weights based on stakeholder priorities.
* Add geospatial mapping and district-level drill-through analysis.
* Compare NFHS-4 and NFHS-5 to measure changes over time.

## Author

**Bhuvaneshwari Kongathi**

Aspiring Data Analyst | Healthcare Analytics | Python | SQL | Power BI
