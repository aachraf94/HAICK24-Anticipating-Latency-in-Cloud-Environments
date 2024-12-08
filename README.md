# HAICK24-Anticipating-Latency-in-Cloud-Environments


![Kaggle Competition](https://img.shields.io/badge/Kaggle-Competition-blue.svg)  
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  

This repository contains my solution for the **[Anticipating Latency in Cloud Environments](https://www.kaggle.com/competitions/anticipating-latency-in-cloud-environments)** Kaggle competition. The competition aimed to predict latency in cloud-native environments using machine learning models, with the evaluation metric being the **R² score**.  

## 🏆 Competition Objective  
The goal was to predict the latency for web server requests under various configurations and conditions in a cloud-native environment. Accurate predictions of latency are crucial for optimizing resource allocation and improving system performance.  

---

## 🛠️ Solution Overview  

### Key Steps:
1. **Data Preprocessing**:
   - Feature engineering:
     - Timestamp decomposition into year, month, day, hour, minute, and second.
     - Log transformations for CPU and RAM usage.
     - Interaction features between CPU and RAM.
   - Conversion of RAM limits to megabytes.
   - CPU type decomposition into brand, series, and model.
   - One-hot encoding for categorical variables.
   - Alignment of training and testing datasets.

2. **Exploratory Data Analysis**:
   - Correlation analysis to identify relationships between features and the target variable.

3. **Feature Preparation**:
   - Defined numerical and categorical preprocessing pipelines using `StandardScaler`, `PolynomialFeatures`, and `OneHotEncoder`.
   - Created a unified `ColumnTransformer` for feature transformation.

4. **Modeling**:
   - Hyperparameter tuning for `CatBoostRegressor` using `Optuna`.
   - Leveraged an ensemble of models:
     - **CatBoostRegressor** (tuned with the best parameters found using Optuna)
     - **XGBRegressor**
     - **RandomForestRegressor**
     - **GradientBoostingRegressor**
   - Created a `VotingRegressor` to combine predictions from multiple models.

5. **Validation**:
   - Used `TimeSeriesSplit` and `KFold` cross-validation to evaluate model performance.
   - Calculated mean R² scores across multiple folds.

6. **Prediction**:
   - Trained the final pipeline on the entire training data.
   - Predicted latencies on the testing data.
   - Prepared a submission file for Kaggle.

## Dependencies

Install the required Python packages using pip:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn optuna catboost xgboost pycaret