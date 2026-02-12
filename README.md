# Vaccine Uptake Prediction — Classification ML Project

## Overview

This project builds an end-to-end machine learning classification pipeline to predict:

- Probability of receiving the H1N1 vaccine
- Probability of receiving the Seasonal flu vaccine

The goal is to help public health stakeholders identify individuals with lower vaccination likelihood and design targeted outreach strategies.

---

## Business Understanding

Vaccination uptake varies across demographics, risk perception, and socioeconomic factors. 

Predicting vaccine likelihood allows:
- Resource prioritization
- Targeted health campaigns
- Early intervention strategies
- Data-driven public health planning

This is a **multi-output binary classification problem**.

---

## Dataset Summary

- ~26,700 training observations
- 36 features per respondent
- 2 binary targets
- Mix of categorical and numeric variables
- Missing values handled via imputation

Feature categories include:
- Demographics
- Health indicators
- Risk perception
- Geographic region
- Employment information

---

## Modeling Approach

I followed a structured predictive modeling workflow:

1. Data understanding (EDA)
2. Train/validation split (stratified)
3. Preprocessing pipeline:
   - Median imputation (numeric)
   - Most frequent imputation (categorical)
   - One-hot encoding
   - Scaling (StandardScaler)
4. Baseline model: Logistic Regression
5. Hyperparameter tuning (GridSearchCV)
6. Ensemble model: Random Forest
7. Model comparison using ROC-AUC and F1

All preprocessing was implemented using `Pipeline` and `ColumnTransformer` to prevent data leakage.

---

## Evaluation Metrics

Due to class imbalance, I used:

- ROC-AUC (primary metric)
- F1 Score
- Accuracy (secondary)

Models were evaluated on validation data only.

---

## Results

- Tuned logistic regression improved over baseline.
- Random Forest captured nonlinear patterns and achieved strong performance.
- Both targets were predictably influenced by demographic and behavioral variables.

Key predictive features included:
- Age group
- Health worker status
- Risk perception
- Income level
- Geographic region

---

## Final Model

The final selected model was trained on the full training dataset and used to generate probability predictions for the test dataset.

Predictions are stored in:

