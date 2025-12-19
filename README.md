## Overview
This project demonstrates an applied, end-to-end AI data science workflow that combines deep learning (PyTorch), traditional regression, and SQL-based data engineering to solve a realistic prediction problem on structured, real-world data.
The core objective is to show how modern data scientists and machine learning engineers can go beyond toy models, integrating data extraction, feature engineering, model comparison, and evaluation into a production-oriented pipeline.
Instead of treating deep learning and regression as competing approaches, this project uses Transformer-based models and classical regression side by side, highlighting when advanced models provide incremental value and when simpler models remain competitive.
## Problem Statement
In many real-world business and financial scenarios—such as demand forecasting, risk estimation, or time-dependent KPI prediction—data is:
Tabular or time-series in nature
Noisy, incomplete, and non-stationary
Stored in relational databases rather than clean CSVs
This project addresses the problem of:
Predicting a continuous target variable from historical, structured data while balancing model accuracy, interpretability, and deployment feasibility.
## Solution Approach
The project is structured as a realistic DS / MLE pipeline:
Data Acquisition
Data is sourced from public datasets or relational tables.
SQL is used to simulate production-style data extraction and joins.
Feature Engineering
Time-dependent features (lags, rolling statistics).
Normalization and missing-value handling.
Structured feature vectors suitable for both regression and deep models.
Modeling
Baseline regression models (Linear / Ridge / Lasso) for interpretability.
Transformer-based regression model implemented in PyTorch to capture temporal dependencies and non-linear patterns.
Unified training and evaluation framework for fair comparison.
Evaluation
Metrics such as MSE and MAE.
Performance comparison between classical and deep models.
Analysis of model stability and overfitting.
