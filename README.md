![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-LightGBM%20%7C%20XGBoost-orange)
![Time Series](https://img.shields.io/badge/Time_Series-darts-success)
![Data Engineering](https://img.shields.io/badge/Data_Engineering-ETL%20%7C%20API-yellow)
![Data Manipulation](https://img.shields.io/badge/Data_Manipulation-Pandas-red)

# ⚡ Forecasting Great Britain's Energy Transition & Gas Demand
## 📌 Project Overview

As Great Britain accelerates its transition toward renewable energy, understanding and predicting natural gas demand is critical for assessing grid capacity risk. This project explores the shifting energy generation mix and develops a robust multivariate time series forecasting model. 

By extracting high-frequency generation data and engineering complex weather features across 9 UK energy zones, this repository provides a machine learning solution to a real-world energy transition challenge.

## 🎯 Business Value

*   **Quantifies Grid Capacity Risk:** Delivers accurate 7-day forward outlooks for natural gas generation, enabling better strategic balancing of the National Transmission System (NTS).
*   **Automated Data Integration:** Seamlessly bridges raw National Energy System Operator (NESO) SQL databases and Open-Meteo telemetry into an analytics-ready format.
*   **Industry-Standard Metrics:** Replaces basic temperature inputs with the Uniform Network Code (UNC) Composite Weather Variable (CWV), aligning model inputs with UK energy sector standards.

## 🏗️ Architecture & Data Pipeline

The ETL pipeline ensures that raw API data is robustly cleansed and transformed before modeling:

1.  **Extraction:** Automated API queries to the NESO database using SQL to pull the daily generation mix.
2.  **Transformation:** Dimensionality reduction, type casting, datetime indexing, and resampling to a daily aggregated frequency to smooth intraday volatility.
3.  **Integration:** Fetching historical and 7-day forecast weather telemetry (Mean Temperature, Max Wind Speed, Shortwave Radiation) using the Open-Meteo API.

## 🧠 Feature Engineering

Weather is the primary driver of energy demand. This project implements advanced, domain-specific feature engineering:

*   **Composite Weather Variable (CWV):** Engineered across 9 distinct Local Distribution Zones (LDZs) (e.g., South East, Scotland, Midlands). The calculation incorporates wind chill, solar radiation, and effective temperature memory, strictly adhering to UNC mathematical structures.
*   **Temporal Covariates:** Built temporal matrices including day of the week, month, weekend indicators, and Great Britain public holiday flags to capture behavioral and industrial consumption trends.

## 🤖 Modeling Strategy

Leveraging the darts ecosystem, the project treats the forecasting challenge as a multivariate time series problem. The pipeline evaluates multiple algorithms to optimize for Mean Absolute Error (MAE):

*   **LightGBM & XGBoost:** Tree-based machine learning models adept at capturing non-linear relationships between gas demand and complex weather interactions. 
*   **SARIMAX / AutoARIMA:** Statistical baselines to benchmark seasonality and auto-regressive properties against the machine learning estimators.

> **Note:** LightGBM proved highly effective in processing the engineered CWV features to forecast the 7-day horizon.

## 🚀 Getting Started

### Prerequisites
Ensure you have the necessary libraries installed via your package manager, including pandas, numpy, requests, darts, lightgbm, xgboost, scikit-learn, and matplotlib.

### Execution
To execute the full data extraction, engineering, and forecasting pipeline, clone the repository to your local machine and run the provided Jupyter Notebook.
