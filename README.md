# 📈 Bitcoin Price Regression Analysis (Time-Series ML)

![Python](https://img.shields.io/badge/Python-Time%20Series%20ML-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Feature%20Engineering-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?logo=numpy&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Regression-F7931E?logo=scikitlearn&logoColor=white)
![Time Series](https://img.shields.io/badge/Time--Series-Modeling-6A1B9A)
![Financial ML](https://img.shields.io/badge/Financial-ML-2E7D32)
![Feature Engineering](https://img.shields.io/badge/Feature-Engineering-00897B)
![Walk Forward Validation](https://img.shields.io/badge/Walk--Forward-Validation-1E88E5)
![Explainable Modeling](https://img.shields.io/badge/Explainable-Regression-795548)
![Quant Analytics](https://img.shields.io/badge/Quant-Analytics-FF7043)

A regression-based time-series project to predict **Bitcoin short-term returns** using historical market signals and engineered features, focusing on **time-series-safe validation**, **interpretability**, and **realistic evaluation**.

---

# 🎯 Project Goal

This project explores the question:

**Can Bitcoin’s next-day movement be predicted using regression models and time-series features?**

Instead of chasing unrealistic “perfect price prediction”, the project focuses on:

- Time-series safe validation (preventing data leakage)
- Feature engineering from market signals
- Model comparison with proper baselines
- Explainable modeling and interpretable features

---

# 🧩 Problem Definition

### Target Variable

The model predicts **next-day log return**.

log_return(t+1) = log( Price(t+1) / Price(t) )

### Why returns instead of price?

- Bitcoin prices are **non-stationary**
- Returns provide **more stable statistical properties**
- Better suited for regression and forecasting models

---

# 📂 Dataset

This project uses Bitcoin historical market data.

### Data Sources

- Bitcoin price and trading volume
- Optional macro signals such as:
  - S&P 500 return
  - VIX volatility index
  - USD index (DXY)
  - Interest rate indicators

Raw datasets are not included in this repository.  
Results can be reproduced by downloading the same data sources and running the notebook pipeline.

---

# 🔧 Feature Engineering

The model uses engineered features capturing **trend, momentum, and volatility**.

### Price Features

- Lagged log returns
- Moving averages (MA7, MA30)
- Rolling volatility (7-day and 30-day standard deviation)
- Momentum indicators

### Volume Features

- Volume change rate
- Rolling volume Z-score

### Optional Market Indicators

- S&P 500 return
- VIX change
- USD index movement
- Interest rate proxy

These features aim to capture **market dynamics influencing short-term Bitcoin movement**.

---

# 🧠 Modeling Workflow

The modeling pipeline follows a quantitative ML workflow:

Raw Data  
→ Feature Engineering  
→ Time-Series Train/Test Split  
→ Model Training  
→ Prediction  
→ Evaluation

Key steps include:

- log-return calculation
- rolling statistical features
- chronological data splitting
- regression model comparison
- performance evaluation

---

# 🤖 Models Used

### Baselines

- Naive baseline (Tomorrow = Today)
- Linear Regression

### Regularized Regression

- Ridge Regression
- Lasso Regression

These models evaluate:

- linear relationships
- feature regularization
- robustness against overfitting

---

# ✅ Evaluation Strategy

Random train/test splits cause **data leakage in time-series problems**.

Therefore the project uses:

### Time-Series Validation

- chronological train/test split
- no future information in training data

### Evaluation Metrics

Regression metrics:

- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- MAPE (optional)

Directional metric:

- Directional Accuracy (correct prediction of up/down movement)

---

# 📊 Key Results

Replace this section with final results after training.

| Model | MAE | RMSE | Direction Accuracy |
|------|-----|------|-------------------|
| Naive Baseline | - | - | - |
| Linear Regression | - | - | - |
| Ridge Regression | - | - | - |
| Lasso Regression | - | - | - |

Key takeaway:

The objective is not perfect prediction but:

- outperforming naive baselines
- identifying useful predictive signals
- maintaining realistic evaluation

---

# 📉 Example Prediction Visualization

Typical outputs from the model include:

- Actual vs Predicted returns
- rolling prediction performance
- feature importance (for linear models)

Example concept:

Actual BTC Return vs Predicted Return

These visualizations help evaluate **how closely models capture market dynamics**.

---

# 📌 Business / Financial Interpretation

Although simplified, similar approaches are used in:

- quantitative trading research
- crypto market analysis
- risk monitoring systems
- volatility forecasting

Key takeaway:

Even simple regression models can reveal **important predictive signals in financial time-series data**.

---

# ⚠️ Limitations

Bitcoin markets present several challenges:

- high volatility
- structural regime shifts
- macro shocks
- non-linear dynamics

Prediction accuracy may degrade over time.

This project is intended for **learning and portfolio demonstration**, not financial advice.

---

# 🗂️ Repository Structure

Bitcoin-Price-Regression-Analysis/

notebook/  
  Bitcoin Price Regression Analysis.ipynb  

src/ (future modularization)  
  data.py  
  features.py  
  train.py  
  evaluate.py  

reports/  
  figures/  

requirements.txt  
README.md  

---

# 🛠 Tools & Libraries

- Python
- Pandas
- NumPy
- Scikit-Learn
- Jupyter Notebook

---

# 📚 What This Project Demonstrates

This repository demonstrates skills in:

- time-series regression modeling
- financial feature engineering
- machine learning experimentation
- model evaluation and interpretation
- reproducible analytical workflow

---

# 🚀 Future Improvements

Possible extensions include:

- walk-forward validation
- XGBoost / Gradient Boosting models
- LSTM deep learning models
- crypto-specific market indicators
- trading strategy backtesting
