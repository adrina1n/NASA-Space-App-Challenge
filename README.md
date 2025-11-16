# NASA Space Apps Challenge - Exoplanet Classification

This project was developed for the NASA Space Apps Challenge. Its goal is to classify exoplanet candidates from NASA’s TOI, KOI, and K2 datasets into “Confirmed”, “Candidate”, or “False Positive” categories using data fusion, feature engineering, and ensemble models. We focused on the algorithms and did not develop any dashboard or front-end.


## Repository Contents

- NASA_Stacking.ipynb – Combines multiple models into a stacked ensemble.
- NASA_Hack.ipynb – Progressive approach: trains and evaluates each model before stacking.


## Project Overview

Both notebooks implement several base learners (XGB, LGBM, Neural Networks, Logistic Regression, etc.) into a meta-model to maximize classification performance.

- *NASA_Stacking.ipynb*:
    - Combines 7 base models via StackingClassifier
    - Encoding
    - Data cleaning and missing value handling
    - Feature engineering (physical quantities, ratios, log transforms)
    - Correlation checks to avoid multicollinearity
    - Training was not fully completed, so no final KPIs are available.

- *NASA_Hack.ipynb*:
  - Same as above for some parts
  - Trains each model individually first
  - Train/validation/test split
  - Computes KPI metrics for each step
  - Final stacking uses 4 base models


- *Notes*
   - Hyperparameters were chosen manually (not optimized via RandomSearch)
   - Some missing-value features heavily influenced XGBoost in NASA_Hack.ipynb
