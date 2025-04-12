# Chromium-Infusion-and-Glucose-Response-in-Hospitalized-Patients-with-Severe-Insulin-Resistance
Statistical analysis of a retrospective study on chromium infusion in insulin-resistant patients (n=488). Results showed a significant drop in blood glucose post-infusion (p &lt; 0.001), no change in insulin rates, and GLMs/ARIMA models highlighted time as a key predictor.

## Statistical Analysis Plan (SAP)
**NOTE:** Only the Statistical Analysis Plan (SAP) and the code used for the data analysis are posted on this repository. The Statistical Analysis Report and the dataset used will not be posted.

## Introduction and Background
**This Statistical Analysis Plan (SAP)** outlines the methods used to analyze the data, addressing the primary and secondary research questions related to glucose and insulin levels over time, their association with various patient characteristics, and changes before and after chromium infusion. The analysis will employ various statistical methods to estimate model parameters, test hypotheses, and assess the relationship between variables. All data analysis will be conducted using R (version 4.3.2).

## Data Overview
The merged dataset contains 488 observations across 36 variables for each patient. Key variables include:
**Blood.glucose:** Measured in mg/dL.
**Insulin.units.hr:** Units of insulin administered per hour.
**Age_yr, Sex, weight_kg:** Patient demographics.
**Datetime:** Time and date of blood glucose and insulin measurements.
**Pre-insulin_use:** Whether the patient used insulin prior to the study.

## Scientific Questions
1. Does chromium infusion significantly lower blood glucose levels in hospitalized patients with severe insulin resistance?

2. Does chromium infusion lead to a significant change in insulin infusion rates?
What are the key demographic factors influencing glucose and insulin levels before and after chromium infusion?

## Statistical Methods
**Descriptive Statistics:**
Descriptive statistics will be used to summarize demographic variables, including age, sex, and weight. The mean age of the participants was 52.21 years, and the mean weight was 107.81 kg. The median A1C value is 5.55. The dataset also includes 4 insulin users and 3 non-insulin users.

## Exploratory Data Analysis (EDA):
EDA will involve visualizing blood glucose levels and insulin infusion rates over time using line plots and boxplots. Trends over time will be explored using scatterplot smoothers to visualize the relationship between variables such as insulin infusion rates and blood glucose levels.

## Hypothesis Testing:
The analysis will include hypothesis testing to assess the relationship between insulin use and blood glucose levels. A Welch two-sample t-test will be performed to compare blood glucose levels between insulin users and non-users. The preliminary results suggest a significant difference in mean blood glucose levels between the two groups (t = -2.9747, p = 0.01298), with insulin users having a mean glucose of 154 mg/dL and non-insulin users 267 mg/dL.
ANOVA will be used to explore if blood glucose levels differ significantly based on insulin use across the dataset. Preliminary results show no significant differences based on the pre_insulin_use factor (p = 0.25).

## Regression Analysis:
We will use generalized linear models (GLMs) to analyze the relationship between blood glucose and insulin units per hour with patient characteristics as predictors:
GLM for blood glucose levels: A Gaussian family will be used to model blood glucose as a function of Datetime, Insulin.units.hr, Age_yr, weight_kg, and Sex.
Preliminary results suggest that Datetime and Insulin.units.hr are approaching significance (p = 0.0569 and p = 0.0803, respectively).
GLM for insulin units per hour: Similarly, a GLM will model insulin infusion rates as a function of Datetime, Blood.glucose, Age_yr, weight_kg, and Sex.
Preliminary analysis indicates a non-significant relationship between blood glucose and insulin infusion rates (p = 0.2959).


## Time Series Analysis:
ARIMA modeling will be used to model blood glucose levels over time for a single patient and predict future values. A first-order differencing (ARIMA(0,1,0)) model was chosen based on preliminary analysis, which produced an AIC of 210.87 and a training RMSE of 160.46.

## Model Diagnostics:
R-squared and residual diagnostics will be performed to assess the goodness of fit for the regression models. For example, the model for blood glucose had an R-squared of 0.6368, indicating that approximately 63.7% of the variability in blood glucose levels is explained by the predictors in the model.
AIC (Akaike Information Criterion) will be used to compare the fit of the different models, with lower AIC values indicating a better fit.

## Handling Missing Data:
Missing data will be handled by removing any rows with missing blood glucose or insulin data.
The dataset will be analyzed based on available cases, and any missing data will be acknowledged in the reporting.

## Statistical Significance and P-values
A p-value of 0.05 will be considered the threshold for statistical significance for all tests unless stated otherwise.
For regression models, confidence intervals will be computed for all coefficient estimates.
All statistical tests will be two-sided.

## Software
All statistical analyses will be conducted using R version 4.3.2. The following R packages will be used:
tidyverse for data manipulation and visualization.
lme4 for mixed-effects modeling.
forecast for time series analysis.
stats for hypothesis testing.

This SAP outlines the statistical methods and analysis approach for understanding the relationship between blood glucose levels, insulin units per hour, and various demographic variables. The results of initial exploratory analyses, regression models, and hypothesis tests will be used to guide the final analysis. The study aims to provide insights into factors influencing glucose and insulin levels, adjusting for key covariates, and evaluating the impact of chromium infusion on these variables.
