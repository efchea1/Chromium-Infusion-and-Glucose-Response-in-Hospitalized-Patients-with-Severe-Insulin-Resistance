# Chromium Infusion & Glucose Response in Hospitalized Patients

## Overview
This project analyzes a retrospective dataset (n = 488) to evaluate the effect of chromium infusion on blood glucose levels in patients with severe insulin resistance. The analysis uses GLMs, t-tests, ANOVA, and ARIMA time series modeling to understand treatment effects over time.

## Objectives
- Assess the impact of chromium infusion on glucose and insulin levels
- Explore associations with demographic covariates
- Model temporal trends using regression and ARIMA approaches

## Dataset
- **Sample size**: 488 observations across 36 variables
- **Key variables**:
  - `Blood.glucose` (mg/dL)
  - `Insulin.units.hr`
  - `Datetime`
  - Demographics: Age, Sex, Weight, Pre-insulin use

## Methods
- **Hypothesis Testing**: Welch t-test & ANOVA for group comparisons
- **Regression Models**: GLMs for glucose and insulin levels
- **Time Series Analysis**: ARIMA(0,1,0) for intra-patient glucose modeling
- **Diagnostics**: R-squared, AIC, residual plots

## Key Findings
- Chromium infusion significantly reduced blood glucose (p < 0.001)
- No significant change in insulin units/hr post-infusion
- Time and insulin dosage were near-significant predictors in GLM (p ≈ 0.06)
- ARIMA model achieved RMSE ≈ 160 for individual-level glucose prediction

## Tools Used
- R 4.3.2
- Packages: `tidyverse`, `lme4`, `forecast`, `stats`

## Repository Contents
- `Case_Study2.Rmd`: Full statistical code and results
- `README.md`: Summary of methods and findings
- `SAP_Report.md`: Detailed Statistical Analysis Plan

## Author
**Emmanuel Fle Chea**  
[GitHub](https://github.com/efchea1) | [LinkedIn](https://linkedin.com/in/emmanuel-fle-chea-ba0669129)
