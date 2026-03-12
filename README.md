# 📉 Customer Churn Prediction System

> End-to-end ML pipeline to predict telecom customer churn using **XGBoost** and **Random Forest**, with SMOTE oversampling and a Power BI-ready output layer.

---

## 🏆 Results

| Model | AUC-ROC |
|---|---|
| XGBoost (tuned) | **0.91** |
| Random Forest | 0.88 |

---

## 🗂 Project Structure

```
churn-prediction/
├── src/
│   ├── pipeline.py        # Main ML pipeline (train + evaluate + export)
│   └── visualize.py       # Feature importance & Power BI chart exports
├── models/                # Saved .pkl model + metrics.json (auto-generated)
├── outputs/               # churn_segments.csv, powerbi_churn_report.csv (auto-generated)
│   └── plots/             # PNG charts for dashboards
├── requirements.txt
└── README.md
```

---

## ⚙️ Setup

```bash
git clone <your-repo-url>
cd churn-prediction
pip install -r requirements.txt
```

---

## 🚀 Run

```bash
# Train models + generate churn segments
python src/pipeline.py

# Generate visualizations + Power BI export
python src/visualize.py
```

---

## 🔧 Key Techniques

| Step | Details |
|---|---|
| **Feature Engineering** | ChargesPerMonth, SupportCallRate, IsPremiumCustomer, IsLongTermCustomer |
| **Class Imbalance** | SMOTE (Synthetic Minority Oversampling) — balances churned vs retained |
| **Models** | XGBoost (300 estimators, lr=0.05) · Random Forest (200 trees, balanced weights) |
| **Hyperparameters** | Subsample=0.8, colsample_bytree=0.8, max_depth=6 |
| **Evaluation** | AUC-ROC, Precision/Recall, Confusion Matrix |

---

## 📊 Power BI Dashboard

After running the pipeline, import `outputs/powerbi_churn_report.csv` into Power BI.

Included fields:
- `ChurnProbability` — model score (0–1)
- `RiskSegment` — Low / Medium / High Risk
- `RetentionPriority` — Immediate Action / Monitor / Healthy
- `EstimatedLTV` — projected 12-month value adjusted for churn risk

---

## 📦 Tech Stack

`Python` · `Scikit-learn` · `XGBoost` · `imbalanced-learn (SMOTE)` · `Pandas` · `Matplotlib` · `Power BI`
