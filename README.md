# Telecom Churn Prediction Case Study

## Overview

This project presents a comprehensive analysis of telecom customer churn. The goal is to predict customer churn by examining usage and recharge patterns over a four-month window. The analysis covers data preprocessing, exploratory data analysis (EDA), feature engineering, and predictive modeling to identify the key factors influencing customer attrition.

## Problem Statement

In the highly competitive telecom industry, customer retention is critical because acquiring new customers is significantly more expensive than retaining existing ones. This case study aims to:
- **Predict churn** using data from the first three months (good and action phases).
- **Identify key indicators** of churn to inform targeted retention strategies.

## Data Description

The dataset consists of customer-level data for four consecutive months, encoded as months 6, 7, 8, and 9. Key features include:
- **Call Minutes (MOU):** Incoming and outgoing call durations.
- **Data Usage:** 2G and 3G mobile internet usage.
- **Recharge Information:** Total, average, and maximum recharge amounts for mobile data.
- **Additional Metrics:** ARPU (Average Revenue Per User), customer tenure (derived from AON), and more.

## Methodology

The project was executed through the following steps:

1. **Data Preprocessing:**
   - **Categorization:** Columns were grouped into ID, Date, Categorical, and Numerical types.
   - **Missing Value Handling:** Missing values in recharge data were imputed (using 0 where appropriate) or dropped based on a predefined threshold.
   - **Data Type Conversions:** Date columns were converted to proper date types and numeric columns were ensured to be in the correct format.

2. **Exploratory Data Analysis (EDA):**
   - Analysis of recharge behavior, call minutes, and data usage.
   - Summary statistics and visualizations (e.g., distribution plots, boxplots) were used to identify patterns and outliers.

3. **Feature Engineering:**
   - **Derived Variables:** New variables (such as the difference between month 8 and the average of months 6 & 7) were created.
   - **High-Value Customer Filtering:** Customers with an average recharge amount in the first two months above the 70th percentile were identified for focused analysis.
  
4. **Churn Tagging:**
   - **Churn Definition:** Customers were labeled as churned if they showed no call activity and no data usage in month 9.
   - **Data Leakage Prevention:** Churn-phase columns (month 9) were removed after defining the target variable.

5. **Model Building and Evaluation:**
   - The dataset was split into training and testing sets using stratified sampling.
   - Multiple models were built (e.g., Logistic Regression with PCA and Random Forest) with hyperparameter tuning.
   - Model performance was evaluated using metrics such as ROC-AUC, sensitivity, and specificity.

6. **Conclusions and Recommendations:**
   - Key churn indicators were identified, including reduced call durations and significant changes in recharge behavior during the action phase.
   - Recommendations were made to improve customer retention.

## Installation & Requirements

To run this project, you will need:
- **Python 3.7+**
- The following Python packages:
  - numpy
  - pandas
  - matplotlib
  - seaborn
  - scikit-learn
  - imbalanced-learn

Install the required packages using:
```bash
pip install -r requirements.txt
