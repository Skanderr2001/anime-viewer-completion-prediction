# Anime Viewership Completion Prediction Using Machine Learning

## Project Overview

This project builds a complete machine learning pipeline to predict the number of users who complete watching an anime series. The prediction is based on anime metadata and user engagement statistics. The objective is to understand viewer retention behavior on streaming platforms and identify key factors influencing completion.

This project was developed as part of the Applied Machine Learning module in the MSc Data Science and Business Analytics program.

**Author:** Skander Radhouane

---

## Problem Statement

Many viewers start an anime but do not finish it. Predicting completion counts helps streaming platforms and production studios understand content performance and viewer engagement.

**Target Variable:**  
Completed number of users who finished watching an anime

---

## Dataset Description

The dataset contains 14,952 anime titles. Each record represents one anime with metadata and engagement metrics.

### Feature Groups

**Engagement Metrics**
- Members  
- Watching  
- On Hold  
- Dropped  
- Favorites  

**Rating Information**
- Score  
- Age Rating  

**Content Information**
- Genres  
- Type  
- Episodes  
- Duration  

**Release Information**
- Premiered Season and Year  
- Aired Dates  

**Production Metadata**
- Studios  
- Producers  
- Source  

**Target Variable**
- Completed

---

## Data Preprocessing

Key preprocessing steps applied:

- Removed identifier and text heavy columns such as anime id, name, synopsis, and licensors  
- Converted duration text into numeric minutes  
- Split premiered into season and year  
- Created binary feature indicating whether the anime finished airing  
- Multi hot encoding for genres  
- One hot encoding for categorical variables  
- Median imputation for missing numeric values  

Final dataset contained 4,846 numeric features.

---

## Exploratory Data Analysis

Main insights:

- Completed variable was highly right skewed and log transformed  
- Strong linear relationship between Members and Completed  
- Higher rated anime tend to have higher completion counts  
- Engagement variables showed highest correlation with completion  

---

## Models Trained

Four regression models were trained and evaluated:

| Model | R2 Score |
|-------|----------|
| Linear Regression | Negative R2 confirming non linearity |
| Ridge Regression | 0.858 |
| Gradient Boosting Regressor | 0.970 |
| Random Forest Regressor | **0.979** |

Random Forest Regressor achieved the best performance.

---

## Model Evaluation

**Best Model:** Random Forest Regressor  
**Test R2 Score:** 0.979  
**RMSE:** 0.389 on log scale  

Small train test gap confirms strong generalization.

---

## Model Interpretation

Most important features:

- Members  
- Dropped  
- Watching  
- On Hold  
- Score  

Viewer engagement and audience size are the strongest drivers of completion prediction.

---

## Tools and Libraries

- Python  
- Pandas  
- NumPy  
- Scikit learn  
- Matplotlib  
- Seaborn  

---

## How to Run

1. Open the notebook file `anime code.ipynb`  
2. Install required Python libraries  
3. Run all cells sequentially  

---

## Results Summary

The project demonstrates a full machine learning workflow including data preprocessing, feature engineering, exploratory analysis, model training, evaluation, and interpretation. Results show that viewer completion behavior is mainly driven by audience size and engagement metrics.

---

## Author

Skander Radhouane  
MSc Data Science and Business Analytics Student
