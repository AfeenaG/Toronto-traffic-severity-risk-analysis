# Predicting Severe Traffic Injuries in Toronto

### A Data-Driven Safety Analysis Using Logistic Regression

## Project Overview

Traffic collisions resulting in severe injuries and fatalities remain a major public safety challenge in Toronto. This project analyzes **over 10,000 collision records** from the City of Toronto Open Data Portal to identify the factors that most strongly predict **severe injury outcomes**.

Using **logistic regression models built in Python (JupyterLab)**, this study examines how **user characteristics, environmental conditions, and temporal factors** influence the likelihood that a collision results in a severe injury.

The results provide actionable insights that can support **transportation planners, public safety officials, and policy makers** working toward Toronto’s **Vision Zero goal of eliminating traffic fatalities and severe injuries.**

---

# Key Findings

### Vulnerable Road Users Face the Greatest Risk

Pedestrians, cyclists, moped drivers, and motorcyclists face **13–34 times higher odds** of severe injury compared to drivers.



### Age Significantly Increases Injury Severity

Older adults are much more vulnerable in collisions.

* Predicted probability of severe injury:

  * Age 25–29 → **74%**
  * Age 75–79 → **83%**

### Dusk Lighting Creates Dangerous Conditions

Collisions occurring during **dusk with artificial lighting** are nearly **twice as likely** to result in severe injury compared to daylight conditions.



### Rush Hour Increases Severity Risk

Morning commuting hours (12:00–14:59) have the **highest predicted probability of severe injuries**.



### Late Fall Months Show Higher Risk

The months **October, November, and December** show elevated predicted probabilities of severe collisions.


---

# Business Problem

Every year, Toronto records thousands of traffic collisions that result in severe injuries or fatalities. Vulnerable road users—particularly **pedestrians, cyclists, and older adults**—are disproportionately affected.

This project aims to identify **the strongest predictors of severe injury outcomes** by analyzing:

* user characteristics
* environmental conditions
* time-related factors

The goal is to provide **data-driven insights** that help city planners prioritize safety interventions such as infrastructure upgrades, enforcement strategies, and public awareness campaigns.

---

# Dataset

This analysis uses the **Toronto Motor Vehicle Collisions Involving Killed or Seriously Injured Persons dataset**.

**Source:** City of Toronto Open Data Portal
**Time Period:** 2006 – 2023
**Dataset Size:** 10,044 rows × 169 columns

Key feature groups used in the analysis include:

* `UserInvType_*` – involvement type (driver, pedestrian, cyclist, etc.)
* `UserAgeRange_*` – age categories
* `EnvLightingCondition_*` – lighting conditions
* `EnvRoadSurfaceCondition_*` – road surface conditions
* `TimePeakOffPeak_*` – peak vs off-peak hours
* `TimeMonth_*` – monthly variation
* `TimeRange_*` – time-of-day ranges

---

# Data Preparation

Several preprocessing steps were required to prepare the dataset for modeling.

**Cleaning and Feature Engineering**

* Renamed columns for clarity
* Removed records with missing critical fields
* Converted date and time values into usable features
* Created dummy variables for categorical variables
* Standardized categorical predictors
* Structured variables for logistic regression analysis

Baseline categories were defined for interpretation purposes (for example: **driver involvement, daylight conditions, dry road surface**).

---

# Analytical Approach

A **logistic regression model** was used to estimate the probability that a collision results in a **severe injury**.

Logistic regression was selected because the outcome variable is **binary**:

* Severe Injury (Fatal or Major)
* Non-Severe Injury

Models were built using **Python (JupyterLab) and the `statsmodels` library**.

Each variable was evaluated using four key statistical measures.

### P-Values

Determine whether the observed effect is statistically significant.

### Confidence Intervals

Measure the reliability and precision of estimated effects.

### Odds Ratios

Quantify how much more or less likely severe injury is relative to a baseline group.

### Predicted Probabilities

Translate statistical relationships into **real-world likelihoods** of severe injury.

---

# Analysis Structure

The analysis was conducted across **three main dimensions**.

## 1. User Factors

Key variables analyzed:

* involvement type
* age range

Findings show that **vulnerable road users** and **older adults** face significantly higher injury risk.

---

## 2. Environmental Factors

Key variables analyzed:

* lighting conditions
* road surface conditions

The most dangerous environmental condition observed was **dusk with artificial lighting**.

Packed snow and non-standard road surfaces also increased risk levels.

---

## 3. Time-Based Factors

Key variables analyzed:

* peak vs off-peak hours
* month of year
* time-of-day ranges
* seasonal variation

Morning commuting hours showed the **highest probability of severe injury outcomes**.

---

# Visualization Examples

The analysis includes several charts used to communicate findings.

### Predicted Probability of Severe Injury by Age

Older adults show steadily increasing injury risk.
![User](Images/User01-Predictive%20Probability%20of%20Severe%20Injury%20By%20Age%20Range_Redo.png)
### Relative Odds by Involvement Type

Pedestrians, cyclists, and motorcyclists face dramatically higher odds of severe injury.

![User](Images/User02-Relative%20Odds%20Of%20Severe%20Injury%20By%20Involvement%20Type.png)

### Lighting Condition Impact

Dusk lighting conditions significantly increase injury severity risk.
![Environment](Images/Env1-Impact%20of%20Lighting%20Condition%20on%20Severity%20Odds_Redo.png)

### Time-of-Day Risk Patterns

Morning rush hour exhibits the highest predicted probabilities of severe injury.

![Rush Hour](Images/Time01-Predicted%20Probability%20of%20Severe%20Injury%20by%20Time%20of%20Day_Redo.png)
### Month Patterns

![Months](Images/Time02-Predicted%20Probability%20of%20Severe%20Injury%20by%20Month_Redo.png)
---

# Managerial Insights

The findings suggest several **targeted safety interventions**.

### Infrastructure Improvements

* Protected cycling lanes
* pedestrian-priority zones
* improved intersection lighting

### Senior Safety Initiatives

* longer pedestrian crossing times
* senior-focused mobility programs
* targeted education campaigns

### Peak Hour Safety Measures

* enhanced enforcement during rush hour
* congestion management strategies

### Seasonal Safety Campaigns

* fall and winter driver awareness programs
* winter road maintenance improvements

These interventions support Toronto’s **Vision Zero strategy**, which aims to eliminate severe traffic injuries and fatalities.

---

# Project Structure

```text
toronto-traffic-injury-risk-analysis
│
├── README.md
├── data
│   └── TorontoCity_traffic_collisions_KPI_Modified.csv
│
├── notebooks
│   ├── data_cleaning.ipynb
│   ├── feature_engineering.ipynb
│   ├── logistic_regression_models.ipynb
│
├── visualizations
│   ├── age_probability_chart.png
│   ├── involvement_odds_chart.png
│   ├── lighting_condition_chart.png
│   ├── road_surface_probability_chart.png
│   ├── month_probability_chart.png
│   └── time_of_day_probability_chart.png
│
├── outputs
│   ├── model_results.csv
│   ├── predicted_probabilities.csv
│   └── statistical_tables.xlsx
│
└── report
    └── full_analysis_report.pdf
```

---

# Tools and Technologies

Python
JupyterLab
Pandas
Statsmodels
NumPy
Matplotlib / Visualization Libraries

---

# Data and Code Availability

All code, datasets, and outputs used in this analysis are available in the repository.

Additional supporting files can be accessed here:

https://drive.google.com/drive/folders/1t6MoUdou-3VU8HN0dL1emab5bXMtExD1

---

# Conclusion

This study demonstrates how **statistical modeling and data analysis can identify the strongest predictors of severe traffic injuries**.

By translating collision data into actionable insights, the project supports **evidence-based safety interventions** that can reduce the risk faced by Toronto’s most vulnerable road users.

The results reinforce the importance of:

* safer infrastructure
* targeted enforcement
* improved lighting
* protection for pedestrians and cyclists
* senior-friendly transportation design

Together, these strategies contribute to the long-term objective of **eliminating severe traffic injuries across the city.**

---

# Author

Afeena Gafoor: Graduate Student – **Business Analytics and Artificial Intelligence**

This project demonstrates skills in:

* statistical modeling
* logistic regression
* data cleaning and feature engineering
* predictive analytics
* data-driven policy insights
