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

A regression-based time-series project to predict **Bitcoin short-term returns** using historical market signals and engineered features.  
The project focuses on **time-series-safe validation**, **interpretable modeling**, and **realistic evaluation**.

---

# 🎯 Project Goal

This project explores the question:

**Can Bitcoin’s next-day movement be predicted using regression models and time-series features?**

Instead of chasing unrealistic “perfect price prediction”, the project emphasizes:

- Time-series safe validation (preventing data leakage)
- Feature engineering from market signals
- Model comparison with baselines
- Explainable modeling and interpretable results

---

# 🧩 Problem Definition

### Target Variable

The model predicts **next-day log return**.

log_return(t+1) = log( Price(t+1) / Price(t) )

### Why returns instead of price?

- Bitcoin prices are **non-stationary**
- Returns provide **more stable statistical properties**
- Better suited for regression modeling

---

# 📂 Dataset

This project uses Bitcoin historical market data.

### Data Sources

- Bitcoin price and trading volume
- Optional macro indicators such as:
  - S&P 500 return
  - VIX volatility index
  - USD index (DXY)
  - Interest rate indicators

Raw datasets are not included in this repository.  
Results can be reproduced by downloading the same data sources and running the notebook.

---

# 🔧 Feature Engineering

Features are designed to capture **momentum, trend, and volatility**.

### Price-based Features

- Lagged log returns
- Moving averages (MA7, MA30)
- Rolling volatility (7-day and 30-day standard deviation)
- Momentum indicators

### Volume-based Features

- Volume change rate
- Rolling volume Z-score

### Optional Market Signals

- S&P 500 return
- VIX change
- USD index movement
- Interest rate proxy

These signals help capture **market dynamics influencing short-term Bitcoin movement**.

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
- regularization effects
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

(Replace this section with final results)

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

Example evaluation visualization:

Actual Return vs Predicted Return

This chart helps illustrate how closely the model captures short-term market movements.

You can generate prediction charts from the notebook and place them in:

reports/figures/

Then reference them in this README.

---

# 🔎 Feature Importance (Interpretability)

Linear and regularized regression models allow us to interpret the influence of features.

Important predictive signals may include:

- Lagged returns
- Rolling volatility
- Volume changes
- Market momentum indicators

These signals help explain **what drives short-term Bitcoin movement**.

---

# ▶️ How to Run the Project

### 1. Install dependencies

pip install -r requirements.txt

### 2. Launch Jupyter Notebook

jupyter notebook

### 3. Run the notebook

Open:

notebook/Bitcoin Price Regression Analysis.ipynb

and execute all cells to reproduce the analysis.

---

# 📌 Business / Financial Interpretation

Although simplified, similar techniques are used in:

- quantitative trading research
- crypto market analysis
- risk monitoring systems
- volatility forecasting

Even simple regression models can reveal **meaningful predictive signals in financial time-series data**.

---

# ⚠️ Limitations

Bitcoin markets are challenging due to:

- high volatility
- regime shifts
- macro shocks
- non-linear market behavior

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
- model evaluation
- interpretable modeling
- reproducible analytical workflows

---

# 🚀 Future Improvements

Possible extensions include:

- walk-forward validation
- XGBoost / Gradient Boosting models
- LSTM deep learning models
- crypto-specific indicators
- trading strategy backtesting
