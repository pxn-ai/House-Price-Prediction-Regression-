<p align="center">
  <img src="header_banner.png" alt="House Price Prediction Banner" width="600"/>
</p>

# 🏠 House Price Prediction | Advanced Regression

A machine learning project tackling the [Kaggle House Prices](https://www.kaggle.com/c/house-prices-advanced-regression-techniques) competition. This solution achieves **~98.2% prediction accuracy** using an ensemble of XGBoost, Random Forest, and Neural Networks.

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-1.x-189B1C)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-1.x-F7931E?logo=scikit-learn&logoColor=white)

---

## 📌 Project Overview

Predicting house prices from 79 explanatory variables describing residential properties in Ames, Iowa. The goal was to build an interpretable, high-accuracy regression model that captures both linear relationships and complex feature interactions.

> **Note:** The provided training dataset was split into **60% training, 20% cross-validation, and 20% test** subsets. All performance metrics reported here are evaluated on this held-out test portion — not the Kaggle competition test set.

### Tech Stack
- **Languages:** Python 3
- **ML/DL:** XGBoost, Random Forest, TensorFlow/Keras
- **Analysis:** Pandas, NumPy, SHAP, Matplotlib, Seaborn

---

## 🏆 Model Performance

| Model | CV RMSE (Log) | Accuracy | Role in Ensemble |
|:------|:-------------:|:--------:|:-----------------|
| **XGBoost (Tuned)** | **0.02176** | **~98.2%** | Primary predictor (65%) |
| Random Forest | 0.02492 | ~97.5% | Stability anchor (25%) |
| Neural Network | 0.22728 | ~78.0% | Pattern diversity (10%) |

The final submission uses a **weighted ensemble** combining all three models, with XGBoost contributing the most due to its exceptional precision on this dataset.

---

## 🔍 Feature Engineering & Key Insights

### Top Price Drivers

The SHAP analysis and feature importance studies revealed clear patterns in what drives house values:

| Feature | Correlation | Insight |
|:--------|:-----------:|:--------|
| **OverallQual** | 0.82 | Material and finish quality is the #1 predictor |
| **TotalSF** | 0.78 | Custom engineered feature outperforms individual floor metrics |
| **Neighborhood** | High | Location encodes significant price signals |
| **Age** | -0.59 | Older homes depreciate unless recently remodeled |

### Top 15 Features (XGBoost Importance)

![Feature Importance](Feature%20Importance.png)

### SHAP Value Analysis

Understanding how each feature pushes predictions higher or lower:

![SHAP Summary](SHAP%20Summary.png)

---

## 📊 Model Diagnostics

### Residual Analysis

The XGBoost residuals show no systematic bias — errors are randomly distributed around zero across all price ranges:

![Residual Plot](Residual%20Plot.png)

---

## 📁 Repository Structure

```
.
├── Predict_House_Prices.ipynb    # Main notebook with full analysis
├── Predict_House_Prices.html     # Exported HTML version
├── Feature Importance.png        # XGBoost feature rankings
├── SHAP Summary.png              # SHAP value impact plot
├── Residual Plot.png             # Prediction error analysis
└── house-prices-advanced.../     # Kaggle dataset files
    ├── train.csv
    ├── test.csv
    └── data_description.txt
```

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy scikit-learn xgboost tensorflow shap matplotlib seaborn
```

### Running the Analysis

1. Clone the repository
2. Open `Predict_House_Prices.ipynb` in Jupyter
3. Run all cells to reproduce the analysis and predictions

---

## 💡 Key Takeaways

1. **Quality over quantity** — Overall material quality dominates size metrics as a price predictor
2. **Smart feature engineering pays off** — Combining floor areas into `TotalSF` significantly improved model performance
3. **Ensemble diversity matters** — Even a weaker neural network adds value by capturing different patterns
4. **Location is king** — Neighborhood encoding confirmed the real estate mantra: "Location, location, location"

---

## 📝 License

This project is for educational purposes as part of the Kaggle competition.

---

<p align="center">
  <i>Built with 💻 and ☕ for the Kaggle House Prices Challenge</i>
</p>
