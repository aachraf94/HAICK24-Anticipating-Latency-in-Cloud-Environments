# HAICK24-Anticipating-Latency-in-Cloud-Environments


![Kaggle Competition](https://img.shields.io/badge/Kaggle-Competition-blue.svg)  
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  

This repository contains my solution for the **[Anticipating Latency in Cloud Environments](https://www.kaggle.com/competitions/anticipating-latency-in-cloud-environments)** Kaggle competition. The competition aimed to predict latency in cloud-native environments using machine learning models, with the evaluation metric being the **R² score**.  

## 🏆 Competition Objective  
The goal was to predict the latency for web server requests under various configurations and conditions in a cloud-native environment. Accurate predictions of latency are crucial for optimizing resource allocation and improving system performance.  

---

## 🛠️ Solution Overview  

### 1. **Data Preprocessing**  
- **Handling Missing Values**: Missing values were imputed using domain-specific techniques.  
- **Feature Engineering**: Generated new features, including interaction terms and aggregations, to capture critical patterns.  
- **Encoding Categorical Variables**: Categorical features were encoded using target encoding for better predictive power.  

### 2. **Modeling**  
I experimented with various machine learning models:  
- **XGBoost**  
- **CatBoost**  
- **Random Forest**  
- **Gradient Boosting**  

After tuning hyperparameters using **Optuna**, I achieved the best results with **CatBoostRegressor**.  

**Key Hyperparameters for CatBoost**:  