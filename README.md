# ⚡ Forecasting Great Britain's Energy Transition & Gas Demand

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-LightGBM%20%7C%20XGBoost-orange)
![Time Series](https://img.shields.io/badge/Time_Series-darts-success)
![Data Engineering](https://img.shields.io/badge/Data_Engineering-ETL%20%7C%20API-yellow)
![Data Manipulation](https://img.shields.io/badge/Data_Manipulation-Pandas-red)

## 📌 Project Overview
This project explores the dramatic shift in Great Britain's energy generation mix and develops a robust predictive model for natural gas generation demand. By analyzing high-frequency energy data and integrating granular weather telemetry, this pipeline quantifies the transition from fossil fuels to renewable energy sources and addresses the complex seasonal forecasting challenges faced by grid operators.

Accurate 7-day-ahead demand forecasting allows trading desks and grid operators to optimize gas storage withdrawal and fuel procurement strategies, directly reducing exposure to volatile intraday spot market prices and preventing costly under-nomination penalties.

## 🎯 Key Objectives
* **Automated Data Pipeline (ETL):** Extraction of raw energy generation data from the National Energy System Operator (NESO) API via SQL queries.
* **Domain-Specific Feature Engineering:** Calculation of the industry-standard **Composite Weather Variable (CWV)** based on the Uniform Network Code (UNC), integrating regional temperature, wind speed, and solar radiation from the Open-Meteo API.
* **Multivariate Time Series Forecasting:** Leveraging the `darts` library to construct temporal covariates and train advanced machine learning models for a 7-day forecast horizon.

## 🛠️ Technical Architecture & Stack

### 1. Data Acquisition & Cleansing
* **APIs:** NESO API (Energy Generation), Open-Meteo API (Weather Telemetry).
* **Transformations:** Dimensionality reduction, timeframe reshaping, type casting, and temporal aggregation (daily resampling to smooth intraday volatility).

### 2. Feature Engineering
Energy generation demand is highly sensitive to weather. Instead of using raw temperature, this project maps representative coordinates across **9 distinct UK Local Distribution Zones (LDZs)** to construct the CWV. External temporal covariates include:
* **Calendar Features:** Day of week, month, and weekend flags.
* **Holiday Effects:** Binary flags for Great Britain public holidays to capture distinct shifts in industrial and domestic consumption profiles.

### 3. Modeling Approach
The time series framework evaluates multiple algorithms to capture weekly and seasonal seasonality:
* **LightGBM (Champion Model)**
* **XGBoost**
* **SARIMAX**

## 📊 Results & Business Impact
The champion **LightGBM** model successfully captured the complex consumption patterns inherent in GB gas demand. 
* **Risk Mitigation:** Quantified variance (`Std: 423.64 MW`) and worst-case bounds (`Max: 1869.58 MW`), enabling the generation of empirical confidence intervals for capacity requirements.
* **System Balancing:** Enhanced predictive power natively reduces reliance on expensive Balancing Mechanism interventions, lowering overall operational costs during the energy transition.

## 🚀 Future Enhancements
1. **Probabilistic Forecasting:** Transition from point forecasts to quantile regression models (e.g., predicting 10th, 50th, and 90th percentiles) to accurately capture risk boundaries.
2. **Deep Learning Implementations:** Benchmark the LightGBM champion against neural architectures like the Temporal Fusion Transformer (TFT) or N-BEATS for extended seasonal horizons.
3. **Automated MLOps Pipeline:** Encapsulate the pipeline into a modular architecture using Prefect or Airflow, with automated model drift monitoring via MLflow.
