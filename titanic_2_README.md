# Titanic Survival Analysis

## Overview
This project explores the Titanic dataset to identify which passenger characteristics were the most significant predictors of survival. The analysis covers exploratory data analysis (EDA), feature selection, and classification modeling.

## Dataset
- **Source:** [Kaggle Titanic Dataset](https://www.kaggle.com/competitions/titanic)
- 891 passengers, 12 variables
- Target variable: `Survived` (0 = did not survive, 1 = survived)

## Methodology

### 1. Data Preprocessing
- Imputed missing values in `Age` with median, `Embarked` with mode
- Encoded categorical variables using one-hot encoding (`Sex`, `Embarked`)
- Standardized numerical features using `StandardScaler`

### 2. Exploratory Data Analysis
- Correlation analysis between features and the target variable
- Visualizations: survival rate by gender, age distribution, fare distribution

### 3. Feature Selection
- Correlation-based filtering (threshold: |r| > 0.2)
- Random Forest feature importance to confirm variable relevance
- Final selected features: `Sex`, `Fare`, `Age`

### 4. Modeling
Four models were built and compared:

| Model | Accuracy | F1 (Survived) |
|---|---|---|
| Logistic Regression | 79.3% | 0.741 |
| Logistic Regression (balanced) | 81.0% | 0.785 |
| Random Forest (all features) | 79.9% | 0.750 |
| **Random Forest (top 3 features)** | **81.6%** | **0.770** |

## Key Findings
- Gender was the strongest predictor of survival — female passengers had a significantly higher survival rate
- Higher fare (a proxy for passenger class and socioeconomic status) was associated with better survival odds
- Age contributed meaningful predictive power despite its weak standalone correlation with survival
- A simplified Random Forest model with just 3 features outperformed more complex alternatives

## Technologies
- Python 3.12
- pandas, NumPy
- scikit-learn
- matplotlib, seaborn
