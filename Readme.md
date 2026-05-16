# 🌾 Indian Crop Yield Prediction
### Machine learning model predicting crop yields across Indian states using climatic and agricultural features (1997–2020)

---

## 🏆 Results at a Glance

| Model | R² | MAE | RMSE |
|---|---|---|---|
| Linear Regression | 0.197 | 4.649 | 9.358 |
| SVR (RBF Kernel) | 0.325 | 2.858 | 8.582 |
| **Gradient Boosting** | **0.931** | **1.171** | **2.734** |

> **Gradient Boosting achieved R² = 0.93 — a 70% reduction in RMSE over the Linear Regression baseline**

---

## 📌 Problem Statement

Indian agricultural productivity is shaped by a complex mix of climate variability, soil conditions, input usage, and regional diversity — making crop yield highly uncertain and difficult to plan around.

Inaccurate yield forecasting affects farmers, supply chains, and government food policy alike. This project builds a data-driven predictive framework using 23 years of state-level data to identify the key determinants of crop yield and predict output with high accuracy.

---

## 📂 Dataset

- **Source:** Kaggle (scraped from government agricultural records)
- **Coverage:** 1997–2020 | 30 Indian states | Multiple crop types and seasons
- **Features:** Area harvested, annual rainfall, fertilizer usage, pesticide usage, crop type, season, state
- **Target:** Crop yield (tonnes per hectare)

---

## 🔬 Methodology

1. **Data Collection** — State-level Indian crop dataset (1997–2020)
2. **Data Exploration** — Shape, dtypes, missing values, statistical summary
3. **Data Preprocessing** — Null imputation (median), IQR-based outlier removal, whitespace stripping
4. **Feature Engineering** — Crop category (Food vs Commercial), soil type mapping by state, season consolidation, one-hot encoding, label encoding
5. **Exploratory Data Analysis** — Yield distributions, state-wise trends, seasonal patterns, correlation heatmap
6. **Hypothesis Testing** — Pearson correlation and Levene's test to validate climate and input drivers
7. **Train-Test Split** — 80/20 split with StandardScaler applied
8. **Model Training** — Linear Regression · SVR (RBF) · Gradient Boosting Regressor
9. **Model Evaluation** — R², MAE, MSE, RMSE with Actual vs Predicted plots
10. **Feature Importance** — Top drivers of yield identified via Gradient Boosting importance scores

---

## 📊 Key Findings

### Hypothesis Testing Results

| Hypothesis | Test | Result |
|---|---|---|
| H1: Rainfall significantly affects crop yield | Pearson Correlation | ✅ Rejected H₀ |
| H2: Fertilizer & pesticide usage improve yield | Pearson Correlation | ✅ Rejected H₀ |
| H3: Commercial crops show greater yield volatility than food crops | Levene's Test | ✅ Rejected H₀ |

### Other Insights
- **Crop type and region** were the strongest predictors of yield (top feature importance)
- **Commercial crops** showed significantly higher yield volatility than food crops across states
- **Alluvial soil states** (Punjab, Haryana, UP) consistently outperformed other soil types in average yield
- The non-linear complexity of yield data explains why Gradient Boosting outperformed Linear Regression by such a large margin

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Data Processing | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn (LinearRegression, SVR, GradientBoostingRegressor) |
| Statistical Testing | SciPy (Pearsonr, Levene) |
| Environment | Jupyter Notebook |

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/crop-yield-prediction.git
cd crop-yield-prediction

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch the notebook
jupyter notebook crop_yield_prediction.ipynb
```

> Make sure `crop_yield.csv` is in the same directory as the notebook before running.

---

## 📁 Repository Structure

```
crop-yield-prediction/
│
├── README.md
├── crop_yield_prediction.ipynb   ← Main analysis notebook
├── requirements.txt
└── assets/
    └── screenshots/              ← Charts and visualisations
```

