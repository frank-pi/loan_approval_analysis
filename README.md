# Loan Approval Prediction

This repository contains a Jupyter Notebook that builds a **machine learning pipeline for predicting loan approval outcomes** based on applicant and financial data.

## Project Overview

The notebook covers the complete data science workflow:

- Data loading from CSV files
- Data preprocessing and cleaning  
  - Data type correction  
  - Outlier handling (clipping)  
  - Missing values and duplicate removal  
- Exploratory Data Analysis (EDA) and visualizations
- Feature engineering
- Model training and evaluation  
  - Logistic Regression (with feature scaling)  
  - Random Forest  
  - Confusion matrices and ROC curves  
  - Stratified K-Fold cross-validation

## Dataset

The project uses CSV files loaded from a local `data/` directory.

Expected files (as used in the notebook):

- `data/loans_modified.csv`
- `data/loans_feature.csv`

Paths can be adjusted directly in the notebook if needed.

## Requirements

- Python 3.10 or newer
- Jupyter Notebook / JupyterLab or VS Code with notebook support

Required Python packages:

- numpy  
- pandas  
- matplotlib  
- seaborn  
- scikit-learn  

Example setup:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -U pip
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
