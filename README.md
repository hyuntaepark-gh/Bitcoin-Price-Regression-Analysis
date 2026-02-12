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

> A regression-based time-series project to predict **Bitcoin short-term returns** using historical market signals and engineered features, focusing on **time-series-safe validation**, **interpretability**, and **realistic evaluation**.

---

## 🎯 Project Goal

This project answers:

**“Can we predict Bitcoin’s next-day movement using regression models and time-series features?”**

Instead of chasing unrealistic “perfect price prediction,” this project emphasizes:

- Time-series safe validation (**no data leakage**)
- Feature engineering + interpretability
- Baseline comparison + realistic evaluation
- Reproducible workflow

---

## 🧩 Problem Definition

### Target Variable
We predict **next-day log return**:

\[
y_{t+1} = \log\left(\frac{Price_{t+1}}{Price_t}\right)
\]

Why returns instead of raw price?

- Bitcoin price is **non-stationary**
- Returns are more stable for regression modeling
- Easier to evaluate **direction + volatility**

---

## 📂 Dataset

This project uses Bitcoin historical price data and optional macro/market indicators.

### Data Sources
- Bitcoin price & volume: public crypto market data
- Macro indicators (optional): U.S. market signals (e.g., SP500, VIX, DXY, rates)

> ⚠️ Raw data is not included in this repository.  
> You can reproduce results by downloading the same sources and following the notebook steps.

---

## 🔧 Feature Engineering

Features are designed to capture **momentum**, **trend**, and **volatility**.

### Price-based Features
- Lagged log returns
- Moving averages (MA7, MA30)
- Rolling volatility (7-day, 30-day std)
- Momentum indicators (RSI-style signals)

### Volume-based Features
- Volume change rate
- Rolling volume z-score

### Macro / Market Features (optional)
- SP500 return
- VIX change
- USD Index (DXY)
- Interest rate proxy

---

## 🧠 Models Used

This project compares multiple regression models:

### Baselines
- Naive baseline: **Tomorrow = Today**
- Linear Regression

### Regularized Regression
- Ridge Regression
- Lasso Regression

### Non-linear Models (optional)
- Random Forest Regressor
- Gradient Boosting / XGBoost (if added)

---

## ✅ Evaluation Strategy (Time-Series Safe)

Random train/test split can cause **data leakage** in time-series problems.

### Validation Method
- Chronological split (train → test by time)
- Walk-forward (rolling) evaluation (recommended extension)

### Metrics
Regression metrics:
- MAE
- RMSE
- MAPE (optional)

Directional metric:
- **Directional Accuracy** (up/down correctness)

---

## 📊 Key Results (Placeholder)

> Replace this section with your final results after training.

| Model | MAE | RMSE | Direction Accuracy |
|------|-----|------|-------------------|
| Naive Baseline | - | - | - |
| Linear Regression | - | - | - |
| Ridge | - | - | - |
| Lasso | - | - | - |

📌 **Takeaway:**  
The goal is not “perfect prediction,” but **measurable improvement over baseline + explainable drivers**.

---

## 📌 Business Interpretation

This project demonstrates how regression modeling can support:

- Risk monitoring
- Trend detection
- Decision support
- Scenario analysis (what signals drive BTC movement?)

---

## 🔍 What This Project Demonstrates

- Time-series regression modeling
- Feature engineering for financial data
- Model comparison (baseline → regularization → non-linear)
- Proper validation to prevent leakage
- Business-focused interpretation and evaluation

---

## ⚠️ Limitations

Bitcoin markets are highly volatile and influenced by external events.

- Regime shifts happen frequently
- Macro indicators may lag or be incomplete
- Prediction accuracy can degrade over time

This project is intended for **learning and portfolio demonstration**, not financial advice.

---

## 🗂️ Repository Structure (Recommended Upgrade)

```

Bitcoin-Price-Regression-Analysis/
│
├── notebooks/
│   └── bitcoin_regression.ipynb
│
├── src/                     # (optional)
│   ├── data.py
│   ├── features.py
│   ├── train.py
│   └── evaluate.py
│
├── reports/
│   └── figures/
│
├── requirements.txt
└── README.md

```
