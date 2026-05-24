![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-LightGBM%20%7C%20XGBoost-orange)
![Time Series](https://img.shields.io/badge/Time_Series-darts-success)
![Data Engineering](https://img.shields.io/badge/Data_Engineering-ETL%20%7C%20API-yellow)
![Data Manipulation](https://img.shields.io/badge/Data_Manipulation-Pandas-red)

# ⚡ Forecasting Great Britain's Energy Transition & Gas Demand

## 📌 Project Overview
This portfolio site showcases high-impact data science applications created by **Conner Spear**, a First Class Honours Mathematics graduate from the University of Brighton. Grounded in rigorous statistical modeling, probability theory, and machine learning architectures, these projects are tailored to turn massive operational datasets into executive intelligence. 

Leveraging enterprise data stacks (R, Python, SQL, Azure, and GCP), the core focus is bridging advanced theoretical frameworks—such as Multivariate Time Series Forecasting, Support Vector Machines (SVM), and Generalized Additive Models (GAM)—with actionable commercial value in the energy and utility sectors.

### Key Expertise:
* **Production-Grade ETL Pipelines:** Automated high-frequency API ingestion, custom domain-specific feature engineering (such as Composite Weather Variables), and secure cloud transformations.
* **Advanced Mathematical Modeling:** Implementation of regression, time-series, and classification algorithms mapped directly back to system balancing risks and grid capacity challenges.
* **End-to-End MLOps & App Deployment:** Building and serving robust containerized analytic frameworks via production ecosystems like R/Shiny and cloud analytics platforms.

---

## 1. High-Performance Multivariate Time Series: UK Gas Demand Forecasting Pipeline
### ⚙️ Architecture & Technical Scope:
* **Data Ingestion (NESO API):** Engineered an automated, high-frequency SQL pipeline hitting the National Energy System Operator (NESO) API to ingest rolling multi-year records of real-time electricity and gas grid balancing telemetry.
* **UNC Feature Engineering (Composite Weather Variable):** Translated complex legal and physical logic from the Uniform Network Code (UNC) into an atomic, vector-parallelized Python function. Mapped geolocation arrays across 9 discrete UK Local Distribution Zones (LDZs) utilizing API weather feeds (Mean Temperature, Max Wind Speed, Shortwave Radiation) to compute dynamic wind chill and thermal memory effects.
* **Model Benchmark Framework (darts):** Developed a chronological validation framework evaluating baseline SARIMAX networks, penalized Ridge Regression filters, and advanced gradient boosted ensembles (XGBoost and LightGBM) on complex past and future covariate tracking structures.

### 📈 Core Optimizations & Backtesting:
* **Annual Scale Lag Transformations:** Integrated a deep multi-horizon historical matrix (including custom 365-day transformations) to bypass absolute error variance and isolate structural seasonal shifts.
* **Rolling Historical Backtest Validation:** Evaluated pipeline longevity across 62 non-overlapping rolling windows spanning a continuous 14-month validation era to ensure stability under volatile conditions without target data leaks.

| Transition Season / Era | Mean Operational MAE | Core Volatility Driver Identification |
| :--- | :--- | :--- |
| **Summer Trough (Jun–Jul)** | ~1,800 MW | Highly predictable structural baseload under solar suppression. |
| **Spring Ramp-Down (Apr–May)** | ~2,250 MW | Gradual ambient warming; typical network decompression. |
| **Deep Winter (Jan–Feb)** | ~3,300 MW | Cold snap anomalies driving non-linear peaking plant utilization. |
| **Autumn Onset (October)** | **~4,200 MW** | **Transition Phase Shock:** absolute short-term lags lag network steps. |

---

## 2. Risk Quantification: Pipeline Resilience Probability Modeling
### ⚙️ Architecture & Technical Scope:
* **Stochastic Route Optimization:** Re-engineered the probability engine assessing pipeline resilience across the National Transmission System (NTS) network grid to calculate exact transmission path limits under complex disruption matrices.
* **Poisson-Binomial Mathematical Expansion:** Swapped brittle, assumption-heavy classical binomial metrics for a rigorous Poisson-binomial distribution module inside R. This setup handles heterogeneous failure parameters across active pipeline junctions simultaneously, reducing high-dimensional variance down to predictable operational ranges.
* **Interactive Executive Intelligence (Shiny Interface):** Wrapped the operational mathematical script into an enterprise R/Shiny application dashboard. This interface allows grid controllers to stress-test real-time failure contingencies and visually plot continuous asset risk profiles across map clusters during emergency routing scenarios.

---

## 3. Advanced Diagnostic Classification: Diagnostic Engine Tuning
### ⚙️ Architecture & Technical Scope:
* **Hyperparameter Constellation Grid:** Built an automated machine learning script in Python using custom cost functions and exhaustive spatial grid evaluations to fine-tune a Support Vector Machine (SVM) architecture.
* **Optimal Boundary Regularization:** Optimized standard scalar margins to construct non-linear boundary kernels (RBF). This approach eliminated multi-collinear cross-talk and automated noise reduction across dense multi-dimensional patient arrays.
* **Empirical Validation Success:** Achieved a **99.1% diagnostic accuracy rate** on target testing boundaries. This model effectively minimizes false-negative profiles, ensuring dependable classification within sensitive clinical risk boundaries.

---

## 4. Human Behavior Modeling: Lifestyle Stress Predictor Web App
### ⚙️ Architecture & Technical Scope:
* **Advanced Distribution Mechanics:** Designed a predictive architecture tracking individual health trends by isolating self-reporting bias patterns. This implementation addresses highly skewed, non-negative target metrics bounded strictly between 0 and 1.
* **One-Inflated Beta GAM Formulation:** Built and parameterized a One-Inflated Beta Generalized Additive Model (GAM) to handle extreme zero-to-one limits. The model fits smooth cubic regression splines to extract underlying multi-variable trends without over-correcting for localized noise anomalies.
* **Statistical Performance Metrics:** The model achieved an outstanding **0.81 R² explanatory score**. This step successfully mapped complex health interactions while preserving mathematical precision across volatile, self-reported survey domains.

---

## 🧳 Technical Toolkit & Enterprise Stack

| Competency Area | Specialized Frameworks, Tools & Distributions |
| :--- | :--- |
| **Statistical & ML Frameworks** | Regression Analysis, Stochastic Processes, Support Vector Machines (SVM), Beta GAMs, XGBoost, LightGBM, ARIMA, Prophet, Time-Series Forecasting |
| **Languages & Systems** | R, Python, SQL, Git versioning ecosystem |
| **Cloud Computing & BI** | Microsoft Azure cloud infrastructure, Google Cloud Platform (GCP), Power BI visualization, Tableau legacy migrations |
| **Advanced Packages & MLOps**| darts, scikit-learn, mgcv, Shiny, tidyverse, pandas, NumPy, lightgbm |
