# 📊 Sales Prediction using Advertising Data

> Predicting future sales from TV, Radio & Newspaper advertising spend using Machine Learning regression models.

---

## 📁 Project Structure

```
sales_prediction/
├── data/
│   └── Advertising.csv          # Dataset (200 records)
├── outputs/
│   ├── 01_eda_analysis.png       # Exploratory Data Analysis plots
│   ├── 02_model_comparison.png   # Model performance comparison
│   ├── 03_impact_analysis.png    # Feature importance & impact
│   └── predictions_with_actuals.csv
├── models/
│   ├── scaler.pkl
│   ├── linear_regression.pkl
│   ├── ridge_regression.pkl
│   ├── lasso_regression.pkl
│   └── random_forest.pkl
├── Sales_Prediction.ipynb        # Full Jupyter Notebook
├── sales_prediction.py           # Standalone Python script
└── README.md
```

---

## 📋 Dataset

| Column    | Description                         |
|-----------|-------------------------------------|
| TV        | TV advertising budget (in $1000s)   |
| Radio     | Radio advertising budget (in $1000s)|
| Newspaper | Newspaper advertising budget ($1000s)|
| Sales     | Product sales (in 1000 units) — **Target** |

- **200** observations, **no missing values**
- Source: Classic ISLR Advertising dataset

---

## 🔧 Methodology

### 1. Data Cleaning & Feature Engineering
- Dropped unnamed index column
- Created `Total_Ad_Spend` (sum of all channels)
- Created `TV_Ratio` and `Radio_Ratio` (channel proportions)
- Created `TV_Radio_Interaction` (multiplicative synergy feature)
- Labeled `Budget_Tier` (Low / Medium / High / Very High)

### 2. Models Used
| Model | Type |
|-------|------|
| Linear Regression | Baseline regression |
| Ridge Regression | L2-regularized regression |
| Lasso Regression | L1-regularized regression |
| Random Forest | Ensemble tree-based model |

### 3. Evaluation Metrics
- **R²** (coefficient of determination)
- **MAE** (Mean Absolute Error)
- **RMSE** (Root Mean Squared Error)
- **5-Fold Cross Validation R²**

---

## 📈 Results

| Model | R² | CV R² | MAE | RMSE |
|---|---|---|---|---|
| Linear Regression | 0.9742 | 0.9536 | 0.672 | 0.902 |
| Ridge Regression | 0.9734 | 0.9533 | 0.679 | 0.915 |
| Lasso Regression | 0.9732 | 0.9531 | 0.672 | 0.919 |
| **Random Forest** | **0.9890** | **0.9858** | **0.465** | **0.589** |

✅ **Best Model: Random Forest** with R² = 0.989 (explains **98.9%** of sales variance)

<img width="2386" height="1537" alt="01_eda_analysis" src="https://github.com/user-attachments/assets/09683d22-b0f7-4027-b2ce-ed0cf48528b9" />

<img width="2083" height="1624" alt="02_model_comparison" src="https://github.com/user-attachments/assets/2854edce-ab86-41ce-9976-123e36dbd200" />

<img width="2384" height="742" alt="03_impact_analysis" src="https://github.com/user-attachments/assets/b5c62cee-157e-453d-b0bb-bf759e995607" />


---

## 💡 Business Insights

1. **📺 TV advertising has the HIGHEST impact** on sales (correlation: 0.78). Every $1K increase in TV spend results in ~0.87 more units sold.
2. **📻 Radio is the 2nd most effective channel** with strong ROI per dollar spent.
3. **📰 Newspaper shows the LOWEST impact** (correlation: 0.23) — budget should be reallocated to TV/Radio.
4. **🔗 TV + Radio combination** is the most powerful strategy — their interaction was a significant predictor.
5. **💰 Budget strategy:**
   - *Low budget* → Prioritise Radio (best ROI)
   - *High budget* → Lead with TV, supplement with Radio
   - *Underperforming markets* → Reduce Newspaper allocation

---

## 🚀 How to Run

### Option 1: Jupyter Notebook
```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
jupyter notebook Sales_Prediction.ipynb
```

### Option 2: Python Script
```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
python sales_prediction.py
```

---

## 🛠️ Technologies Used

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.8-red)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-purple)

---

## 👨‍💻 Author

Anosh S

Machine Learning & Data Analytics Enthusiast

Internship Project — Sales Prediction using Advertising Data
