# 🌍 Project 1: GeoAI — Water & Land Cover Classification

> Remote Sensing · Ensemble Learning · Explainable AI  
> Terminal34 Data Science Bootcamp — Cohort S2024

---

## 📋 Overview

This project applies machine learning to classify **water and land cover pixels** from satellite imagery using the MODIS Lake Powell dataset. It covers the full data science lifecycle: data loading, exploratory analysis, feature engineering, model training, evaluation, and explainability.

---

## 🗂️ Dataset

| Property | Value |
|----------|-------|
| Source | [NASA CISTO — Hugging Face](https://huggingface.co/datasets/nasa-cisto-data-science-group/modis-lake-powell-toy-dataset) |
| File | `MODIS_multiclass_dataset.csv` |
| Samples | 12,000 (filtered to Land/Water classes) |
| Features | 7 spectral bands (b1–b7) + engineered features |
| Target | `label` — 0.0 = Land, 1.0 = Water |

---

## 🚀 Project Structure

```
project_1_geoai/
│
├── streamlit_app.py          # Hugging Face Space app
├── project_1_geoai_colab.ipynb  # Google Colab notebook
├── requirements.txt          # Python dependencies
└── README.md                 # This file
```

---

## 📊 Tasks Completed

1. **Import Libraries** — pandas, numpy, scikit-learn, shap, matplotlib, seaborn
2. **Load Dataset** — from Hugging Face, filtered to Land/Water only
3. **EDA (7 Visualizations)**
   - Class distribution bar chart
   - Descriptive statistics heatmap
   - Feature distributions by class (KDE)
   - Correlation matrix
   - Boxplots by class
   - Pairplot (top 4 features)
   - Class balance pie chart
4. **Feature Engineering** — ratio, product interaction, log transforms
5. **Data Split** — 80/20 stratified split + StandardScaler
6. **Model Training** — 4 classification models
7. **Evaluation** — accuracy, ROC-AUC, confusion matrix, ROC curves
8. **Explainable AI** — SHAP TreeExplainer (summary, importance, waterfall)

---

## 🤖 Models

| Model | Accuracy | ROC-AUC |
|-------|----------|---------|
| Logistic Regression | 0.9417 | 0.9753 |
| Decision Tree | 0.9654 | 0.9833 |
| **Random Forest** ⭐ | **0.9775** | **0.9974** |
| Gradient Boosting | 0.9700 | 0.9969 |

> Best model: **Random Forest** with ROC-AUC of 0.9974

---

## 🔍 Explainable AI

SHAP (SHapley Additive exPlanations) was used to interpret the Random Forest model:
- **Summary plot** — feature impact distribution across all predictions
- **Bar plot** — mean absolute SHAP value per feature
- **Waterfall plot** — individual prediction explanation (top 10 features)

---

## ▶️ How to Run

### Google Colab
Open `project_1_geoai_colab.ipynb` and run all cells. Dependencies install automatically.

### Locally
```bash
pip install -r requirements.txt
streamlit run streamlit_app.py
```

### Hugging Face Space
The app is deployed at: `https://huggingface.co/spaces/[your-username]/[your-space-name]`

---

## 📦 Requirements

```
streamlit>=1.35.0
pandas>=2.0.0
numpy>=1.26.0
matplotlib>=3.8.0
seaborn>=0.13.0
scikit-learn>=1.4.0
shap>=0.45.0
datasets>=2.19.0
```

---

## 👤 Author

**Terminal34 Data Science Bootcamp — Cohort S2024**  
Module 5: Ensemble Learning & GeoAI

---

*Dataset provided by NASA CISTO Data Science Group via Hugging Face.*
