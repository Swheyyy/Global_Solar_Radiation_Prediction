# ☀️ Global Solar Radiation Prediction System Using Machine Learning Models

## Overview

Global Horizontal Irradiance (GHI) is one of the most important parameters for estimating solar energy production, photovoltaic system performance, and renewable energy planning. However, accurately predicting GHI is challenging because it is influenced by multiple meteorological factors such as cloud cover, air temperature, humidity, visibility, atmospheric pressure, and sunshine duration.

This project develops a machine learning-based prediction system that estimates daily Global Horizontal Irradiance using historical meteorological observations. Multiple ensemble learning algorithms were trained and evaluated to identify the model that provides the most accurate and reliable predictions for unseen future data.

---

# Problem Statement

Many weather stations and renewable energy applications require accurate estimates of Global Horizontal Irradiance for energy forecasting and planning. However, building a reliable prediction model is difficult due to several real-world challenges:

- Missing and incomplete meteorological observations.
- Missing target values caused by sensor outages.
- Data leakage from features directly derived from the target variable.
- Complex nonlinear relationships between weather parameters and solar irradiance.
- Temporal dependence between consecutive days, making random train-test splits unrealistic.

These challenges can significantly reduce prediction accuracy if they are not handled appropriately.

---

# Our Approach

This project addresses these challenges through a structured machine learning pipeline.

The workflow consists of:

- Aggregating raw meteorological observations into daily records.
- Cleaning and preprocessing the dataset.
- Removing records with unavailable target values.
- Eliminating data leakage features to ensure fair model training.
- Applying physically informed missing value handling for cloud-related observations.
- Creating engineered features that capture meteorological and seasonal patterns.
- Performing an 85:15 chronological train-test split to simulate real-world forecasting.
- Training and comparing Random Forest, XGBoost, LightGBM, and Average Ensemble models.
- Selecting the best-performing model based on prediction accuracy.

---

# Why This Project is Effective

Unlike traditional workflows that rely on a single model or random data splitting, this project emphasizes reliable real-world prediction.

The key strengths include:

- **Realistic evaluation:** A chronological train-test split ensures the model predicts future observations instead of randomly sampled data, preventing temporal data leakage.

- **Robust preprocessing:** Missing target values, cloud layer observations, and leakage features are handled using appropriate preprocessing strategies before model training.

- **Feature engineering:** Additional meteorological and temporal features improve the model's ability to learn complex atmospheric relationships.

- **Comprehensive model comparison:** Multiple ensemble learning algorithms are evaluated under identical training conditions to identify the most suitable model.

- **Reliable predictions:** Random Forest achieved the best overall performance, providing the lowest prediction error and highest generalization capability on unseen data.

---

# Machine Learning Models

The following regression models were trained and evaluated:

- Random Forest Regressor
- XGBoost Regressor
- LightGBM Regressor
- Average Ensemble

All models were trained using the same chronological training and testing strategy for fair comparison.

---

# Results

The Random Forest model produced the best overall performance on the chronological holdout dataset.

| Model | MAE | RMSE | R² |
|------|------:|------:|------:|
| Random Forest | **13.27** | **16.62** | **0.929** |
| Average Ensemble | 13.34 | 16.59 | 0.929 |
| LightGBM | 13.62 | 17.28 | 0.923 |
| XGBoost | 14.68 | 18.00 | 0.917 |

The results demonstrate that the Random Forest model provides accurate and consistent predictions while generalizing well to unseen future observations.

---

# Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- LightGBM
- Optuna
- Matplotlib
- SHAP
- Jupyter Notebook

---

# Applications

This project can support:

- Solar energy forecasting
- Photovoltaic system planning
- Renewable energy management
- Solar resource assessment
- Weather data analysis
- Research in solar radiation prediction

---

