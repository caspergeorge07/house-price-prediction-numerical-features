# Predicting House Prices in a Messy Market
## Numerical Features Edition

## Project Overview

This project develops a numerical-only machine learning workflow for predicting residential house prices using the Ames Housing dataset.

The goal is to predict `SalePrice` using only measurable numerical property characteristics such as:
- living area
- basement size
- garage size
- lot size
- year built
- number of bathrooms
- construction quality

The project follows a full data science workflow including:
- exploratory data analysis (EDA)
- data cleaning
- feature engineering
- regression modelling
- cross-validation
- error analysis

---

# Dataset

Dataset: Ames Housing Dataset

Competition:
House Prices - Advanced Regression Techniques

The project uses:
- `train.csv`
- `test.csv`

Only numerical (`int64` and `float64`) features were retained in line with the assignment requirements.

---

# Project Structure

```text
house-price-project/
│
├── data/
│   ├── raw/
│   │   ├── train.csv
│   │   └── test.csv
│   │
│   └── processed/
│
├── notebooks/
│   └── ndubuaku_george_house_price_assignment.ipynb
│
├── reports/
│
├── images/
│
├── models/
│
├── README.md
└── requirements.txt
```

---

# Exploratory Data Analysis

The EDA focused on:
- numerical feature selection
- SalePrice distribution analysis
- correlation analysis
- scatter plot analysis
- missing value analysis
- outlier investigation
- multicollinearity detection

Top correlated numerical features included:
- OverallQual
- GrLivArea
- GarageCars
- GarageArea
- TotalBsmtSF

---

# Data Cleaning

Missing values were handled using domain-aware reasoning.

Examples:
- missing garage values were treated as no garage,
- missing basement values were treated as no basement,
- LotFrontage was imputed using the median.

Outliers were reviewed carefully rather than automatically removed.

---

# Feature Engineering

New numerical features created:
- TotalSF
- HouseAge
- YearsSinceRemodel
- TotalBathrooms
- TotalPorchSF
- HasGarage
- HasBasement

`SalePrice` was log-transformed to reduce skewness and improve regression performance.

---

# Modelling

Models used:
- Linear Regression
- Ridge Regression

Workflow features:
- train-validation split
- cross-validation
- scaling inside sklearn pipelines
- Ridge hyperparameter tuning

---

# Results

| Model | CV RMSE |
|---|---|
| Linear Regression | ~0.1287 |
| Ridge Regression | ~0.1283 |

The final Ridge Regression model outperformed the assignment target RMSE of `0.16`.

---

# Key Findings

- House quality and living area were the strongest predictors of sale price.
- Log transformation significantly improved target distribution symmetry.
- Feature engineering improved model performance.
- Ridge Regression slightly outperformed standard Linear Regression.
- Numerical-only modelling performed strongly despite exclusion of categorical variables.

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

# How to Run

## 1. Clone the Repository

```bash
git clone <your-repository-link>
```

---

## 2. Create Environment

```bash
conda create -n houseprice python=3.11 -y
conda activate houseprice
```

---

## 3. Install Requirements

```bash
pip install -r requirements.txt
```

---

## 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:
```text
notebooks/ndubuaku_george_house_price_assignment.ipynb
```

---

# Author

Ndubuaku George Ekwueme

MSc Data Science — Coventry University