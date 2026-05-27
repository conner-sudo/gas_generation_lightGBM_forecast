# ⚡ Forecasting Great Britain's Energy Transition & Gas Demand

![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue) ![Machine Learning: LightGBM | XGBoost](https://img.shields.io/badge/Machine%20Learning-LightGBM%20%7C%20XGBoost-yellow) ![Time Series: darts](https://img.shields.io/badge/Time%20Series-darts-green) ![Data Engineering: ETL | API](https://img.shields.io/badge/Data%20Engineering-ETL%20%7C%20API-lightblue) ![Data Manipulation: Pandas](https://img.shields.io/badge/Data%20Manipulation-Pandas-purple)

> **Multivariate time series forecasting pipeline** that delivers 7-day forward outlooks for natural gas generation across Great Britain's National Transmission System — built on LightGBM with industry-standard UNC weather features engineered across 9 energy zones.

---

## 🚀 Why This Project Stands Out

| What I Did | Why It Matters |
|---|---|
| Replaced raw temperature with the UNC Composite Weather Variable (CWV) | Aligns model inputs with UK energy sector standards; the CWV incorporates wind chill, solar radiation, and effective temperature memory — materially more predictive than simple temperature |
| Engineered features across 9 distinct Local Distribution Zones (LDZs) | Energy demand is regional; a single national weather feature would mask the spatial variation that drives grid-level decisions |
| Built a full ETL pipeline connecting NESO SQL databases to Open-Meteo telemetry | Demonstrates production-level data engineering, not just modelling — raw API data is automatically cleansed, resampled, and integrated before it touches a model |
| Benchmarked LightGBM and XGBoost against SARIMAX/AutoARIMA baselines | Shows rigorous model selection rather than defaulting to a trendy algorithm |

---

## 📌 Project Overview

As Great Britain accelerates its transition toward renewable energy, understanding and predicting natural gas demand is critical for assessing grid capacity risk. This project explores the shifting energy generation mix and develops a robust multivariate time series forecasting model.

By extracting high-frequency generation data and engineering complex weather features across 9 UK energy zones, this repository provides a machine learning solution to a real-world energy transition challenge.

---

## 🏗️ Architecture & Data Pipeline

The ETL pipeline ensures that raw API data is robustly cleansed and transformed before modelling:

1. **Extraction:** Automated API queries to the NESO database using SQL to pull the daily generation mix.
2. **Transformation:** Dimensionality reduction, type casting, datetime indexing, and resampling to a daily aggregated frequency to smooth intraday volatility.
3. **Integration:** Fetching historical and 7-day forecast weather telemetry (Mean Temperature, Max Wind Speed, Shortwave Radiation) using the Open-Meteo API.

---

## 🧠 Feature Engineering

Weather is the primary driver of energy demand. This project implements advanced, domain-specific feature engineering:

- **Composite Weather Variable (CWV):** Engineered across 9 distinct Local Distribution Zones (LDZs) (e.g., South East, Scotland, Midlands). The calculation incorporates wind chill, solar radiation, and effective temperature memory, strictly adhering to UNC mathematical structures.
- **Temporal Covariates:** Day of week, month, weekend indicators, and Great Britain public holiday flags to capture behavioural and industrial consumption trends.

---

## 🤖 Modelling Strategy

Leveraging the `darts` ecosystem, the project treats the forecasting challenge as a multivariate time series problem. Multiple algorithms are evaluated to optimise for Mean Absolute Error (MAE):

| Model | Role |
|---|---|
| **LightGBM** | Primary model — best performance; captures non-linear weather × demand interactions |
| **XGBoost** | Secondary tree-based challenger |
| **SARIMAX / AutoARIMA** | Statistical baselines benchmarking seasonality and auto-regressive properties |

LightGBM outperforms all other models and is developed in further detail to minimise MAE.

---

## 🎯 Business Value

- **Quantifies Grid Capacity Risk:** Delivers accurate 7-day forward outlooks for natural gas generation, enabling better strategic balancing of the National Transmission System (NTS).
- **Automated Data Integration:** Seamlessly bridges raw NESO SQL databases and Open-Meteo telemetry into an analytics-ready format.
- **Industry-Standard Metrics:** Replaces basic temperature inputs with the UNC Composite Weather Variable (CWV), aligning model inputs with UK energy sector standards.

---

## 🗂️ Repository Structure

```
├── etl/
│   ├── extract_neso.py       # NESO API queries via SQL
│   ├── transform.py          # Resampling, type casting, datetime indexing
│   └── integrate_weather.py  # Open-Meteo API integration
├── features/
│   ├── cwv.py                # UNC Composite Weather Variable calculation
│   └── temporal.py           # Holiday flags, day-of-week, month matrices
├── models/
│   ├── lightgbm_model.py     # Primary forecasting model
│   ├── xgboost_model.py      # Challenger model
│   └── baselines.py          # SARIMAX / AutoARIMA benchmarks
└── notebooks/                # EDA, model evaluation, and MAE comparisons
```
