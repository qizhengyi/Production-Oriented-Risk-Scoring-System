# Financial ML Forecasting Pipeline (SQL + PyTorch)
**Production-oriented regression & Transformer models for structured financial time-series**

## Overview
This project builds a **production-style machine learning pipeline** for **financial forecasting on structured time-series data**.  
It is engineered from the perspective of a **Financial Machine Learning Engineer (MLE)**: focus on **data ingestion from SQL**, **robust feature pipelines**, **baseline vs deep model benchmarking**, and **deployment-relevant evaluation** (stability, latency, maintainability).

Instead of treating deep learning as a default, the project implements **strong regression baselines** and a **Transformer-based regressor (PyTorch)**, then quantifies when the added complexity is justified.

---

## Problem Statement (Finance)
Financial systems often require **continuous-value predictions** to support risk, pricing, and analytics decisions, such as:
- spread / yield forecasting
- volatility proxy estimation
- liquidity or risk signal prediction
- macro/market indicator forecasting

In practice, the data is:
- **stored in relational tables** (warehouse / Postgres / SQLite)
- **noisy and regime-shifting**
- constrained by **latency and monitoring needs**

**Goal:**  
Build a forecasting pipeline that produces **stable predictions** and provides a **clear decision framework** for choosing between classical regression and Transformer models under real constraints.

---

## What This Project Delivers
- A reproducible pipeline from **SQL → features → models → evaluation**
- Side-by-side comparison:
  - **Regression baselines** (Linear/Ridge/Lasso)
  - **Transformer regressor** (PyTorch) for non-linear temporal dependencies
- Metrics and analysis aligned with deployment:
  - **MAE / MSE**
  - **walk-forward / time-based splits**
  - **stability across market regimes**
  - optional: inference latency profiling

---

## Tech Stack
**Core**
- Python
- PyTorch (Transformer regression)
- SQL (PostgreSQL / SQLite)

**Data & ML**
- Pandas, NumPy (feature engineering)
- scikit-learn (baselines, metrics, preprocessing)

**Analysis**
- Matplotlib (plots)
- (Optional) MLflow / Weights & Biases (experiment tracking)

---

## Data Sources (Recommended Finance Options)
You can plug in any structured financial dataset. Typical choices:
- FRED (SOFR, CPI, unemployment, yield curve series)
- Treasury yield curve data
- equity index / ETF OHLCV data (e.g., SPY, QQQ)
- FX rates and macro spreads

The repository supports:
- `CSV → SQL` import (for realism)
- or direct querying from an existing SQL database

---

## Project Structure
```text
.
├── data/
│   ├── raw/
│   └── processed/
├── sql/
│   ├── schema.sql
│   └── extract_features.sql
├── src/
│   ├── data/
│   │   ├── build_dataset.py
│   │   └── feature_engineering.py
│   ├── models/
│   │   ├── baselines.py
│   │   └── transformer_regressor.py
│   ├── training/
│   │   ├── train.py
│   │   └── evaluate.py
│   └── utils/
│       ├── config.py
│       └── metrics.py
├── notebooks/
│   └── eda.ipynb
├── requirements.txt
└── README.md
