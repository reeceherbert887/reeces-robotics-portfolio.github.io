---
layout: default
title: Assignment Checklist
permalink: /course-projects/data-analysis-assignment2/assignment-checklist/
---

# Data Analysis and Visualisation Assignment Checklist

## Project Information

| Item | Details |
|---|---|
| Module | 551672 Data Analysis and Visualisation |
| Assessment | Task 2 - LightHR AI Model Development |
| Dataset | LightHR recruitment dataset |
| Target variable | Was hired within 6 months |
| Main aim | Explore, model, explain, and fairness-test hiring prediction data |

## Assessment Breakdown

| Section | Weighting | Main Requirement | Portfolio Status |
|---|---:|---|---|
| Task A | 20 marks | Initial exploration using association rule mining and K-Medoids | Complete |
| Task B | 10 marks | Classification model building, tuning, validation, and comparison | Complete |
| Task C | 10 marks | Explainability analysis using SHAP and LIME | Complete |
| Task D | 20 marks | Fairness testing using group and individual fairness metrics | Complete |

## Task A - Initial Exploration Checklist

- [x] Load LightHR dataset
- [x] Inspect column names and data types
- [x] Identify numerical and categorical variables
- [x] Check missing values
- [x] Visualise hiring outcome distribution
- [x] Explore gender vs hiring
- [x] Explore education vs hiring
- [x] Explore income vs hiring
- [x] Prepare data for association rule mining
- [x] Discretise age and income into categories
- [x] One-hot encode categorical values
- [x] Generate frequent itemsets using Apriori
- [x] Generate association rules using support, confidence, and lift
- [x] Prepare data for K-Medoids clustering
- [x] Encode categorical columns
- [x] Scale features
- [x] Apply K-Medoids clustering
- [x] Interpret cluster patterns

## Task B - Prediction Model Checklist

- [x] Define feature matrix and target variable
- [x] Split data into training and testing sets
- [x] Train Decision Tree classifier
- [x] Train Random Forest classifier
- [x] Train XGBoost classifier
- [x] Compare training and test accuracy
- [x] Apply cross-validation
- [x] Compare cross-validation mean and standard deviation
- [x] Use confusion matrix for model evaluation
- [x] Select best model for later explainability and fairness analysis

## Task C - Explainability Checklist

- [x] Calculate model feature importance
- [x] Apply SHAP for global explanation
- [x] Generate SHAP bee-swarm plot
- [x] Generate SHAP feature importance plot
- [x] Apply LIME to 10 selected test records
- [x] Save LIME HTML explanations
- [x] Summarise local LIME patterns
- [x] Compare SHAP and LIME findings

## Task D - Fairness Testing Checklist

- [x] Choose protected attribute for main fairness testing
- [x] Evaluate dataset-level group fairness
- [x] Evaluate model-level group fairness
- [x] Calculate Statistical Parity Difference
- [x] Calculate Disparate Impact
- [x] Evaluate individual fairness using similar applicant consistency
- [x] Compare dataset fairness against model fairness
- [x] Summarise fairness findings clearly

## Rubric Tracker

| Rubric Area | Full Marks Requirement | Evidence Included |
|---|---|---|
| Initial exploration | Association rules, K-Medoids, preprocessing | Task A file |
| Prediction model | Several classifiers, hyperparameters, cross-validation | Task B file |
| Explainability | SHAP and LIME analysis | Task C file |
| Fairness testing | Group and individual fairness metrics | Task D file |

## Final Submission Checks

- [x] Report written and structured
- [x] Code notebook included
- [x] Dataset included
- [x] Figures generated
- [x] Fairness summary exported
- [x] LIME explanations saved
- [x] Markdown portfolio files created
