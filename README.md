# week2-steel-energy-analysis
EDA, feature engineering, and baseline regression modeling on the Steel Industry Energy Consumption dataset.
# Steel Industry Energy Consumption Analysis
## Week 2 Internship Task

## Project Overview
This project focuses on performing Deep Exploratory Data Analysis (EDA), Feature Engineering, and Baseline Regression Modeling on the Steel Industry Energy Consumption Dataset.

The objective is to analyze energy consumption patterns, identify important features affecting energy usage, engineer new meaningful features, and build regression models to predict energy consumption.


# Dataset
Dataset Name:
Steel Industry Energy Consumption Dataset

Source:
UCI Machine Learning Repository

The dataset contains:
- Energy consumption readings
- Load types
- Power factors
- Date and time information



# Part 1: Exploratory Data Analysis & Feature Engineering

## Data Preprocessing
Performed:
- Converted date column into datetime format
- Extracted:
  - Hour of day
  - Day of week
  - Month
  - Weekday/Weekend feature

## Feature Engineering
Created new features:
- Power Factor Ratio
- High Load binary feature based on 75th percentile energy usage

# Exploratory Data Analysis

## High Load Detection Using 75th Percentile

A binary feature was created to identify high energy consumption periods. Rows where Usage kWh exceeded the 75th percentile threshold were marked as High Load = 1, while the remaining rows were marked as 0.

<img width="272" height="121" alt="75th percentile" src="https://github.com/user-attachments/assets/db77c871-dbb8-45b4-9c4c-74e87e368be7" />


This feature helps identify energy spike periods and can be useful for understanding unusual consumption patterns and improving prediction performance.

## Correlation Heatmap

The correlation analysis was performed to identify relationships between numerical features and energy consumption.

<img width="1167" height="839" alt="correlation" src="https://github.com/user-attachments/assets/71ee4e48-b696-4bc9-96bb-bf0c57638a20" />

This heatmap represents the correlation between numerical features in the dataset. It helps identify which features have the strongest relationship with energy consumption.


## Outlier Detection

Outliers in energy consumption were detected using the IQR method.

<img width="524" height="358" alt="boxplot" src="https://github.com/user-attachments/assets/632bf9b6-4aa6-4202-b6cb-669a9b90f696" />

This boxplot visualizes outliers in energy consumption using the IQR method. It highlights unusual high consumption values that may affect model performance.


## Energy Consumption by Load Type

This bar chart shows the average energy consumption for different load categories: Light Load, Medium Load, and Maximum Load.

<img width="617" height="356" alt="bar chart" src="https://github.com/user-attachments/assets/a36cb8d0-7fd7-48fb-b4db-0c260533d402" />


The visualization helps compare energy demand across different operating conditions. Maximum Load shows higher energy consumption compared to other load types, indicating that production intensity has a strong impact on power usage.


## Hourly Energy Usage Pattern

Energy usage trends were visualized based on different hours of the day.

<img width="403" height="212" alt="average ec by hr" src="https://github.com/user-attachments/assets/c7208d6d-49d4-4d4b-a911-6d89d086d4ff" />

This line chart shows the variation in average energy consumption throughout different hours of the day.

<img width="850" height="356" alt="linechart" src="https://github.com/user-attachments/assets/db0f9942-3c26-4626-9aec-37df92f5da19" />


The graph helps identify peak and low energy consumption periods. Higher usage during specific hours may indicate increased production activity or operational demand.


# Part 2: Baseline Regression Modeling

## Models Implemented

The following regression models were trained:

1. Linear Regression
2. Ridge Regression
3. Decision Tree Regressor
4. Random Forest Regressor


## Data Preparation

Performed:
- Removed date column
- Removed target leakage features
- Applied One-Hot Encoding on categorical variables
- Split dataset:
  - 80% Training
  - 20% Testing
- Random state = 42


# Model Performance Comparison

Evaluation metrics used:

- MAE
- RMSE
- R² Score
- 5-Fold Cross Validation RMSE


## Model Comparison Chart

<img width="646" height="359" alt="comparison models" src="https://github.com/user-attachments/assets/dbd28359-d402-4249-adfb-b8d705dfe0eb" />


# Best Model Prediction

The best performing model was selected based on the lowest RMSE and highest R² score.

Predicted vs Actual energy consumption:

<img width="779" height="620" alt="plots" src="https://github.com/user-attachments/assets/f38b82e2-5b8b-4a20-a34a-dff9113e764b" />

# Model Selection

Random Forest Regressor achieved the best performance among all tested models. It provided better prediction accuracy due to its ability to capture complex relationships between features.

Cross-validation results were also considered to ensure the model generalized well and did not overfit.



# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

