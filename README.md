# House Prices - Advanced Regression Techniques

This repository contains my work for the Kaggle competition "[House Prices: Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)". The goal of this project is to predict the final sale prices of homes in Ames, Iowa using a dataset of 79 features that describe various aspects of the houses.


## Table of Contents

1. [Competition Overview](#competition-overview)
2. [Project Structure](#project-structure)
3. [Methods Used](#methods-used)
4. [Feature Engineering](#feature-engineering)
5. [Modeling Techniques](#modeling-techniques)
6. [Results](#results)
7. [How to Run](#how-to-run)


## Competition Overview

The competition is centered around predicting home prices based on a variety of house features, from square footage to neighborhood location. This dataset provides an excellent playground to explore creative feature engineering and experiment with different regression techniques.


## Project Structure

```bash
House-Prices/
│
├── data/                         # Contains the dataset files
│   ├── train.csv                 # Training dataset
│   ├── test.csv                  # Test dataset
│
├── reports/                      # R scripts
│   ├── house-prices.Rmd          # R script for model training
│
├── environment.yaml              # Dependencies for setting up the environment
│
└── README.md                     # This file
```


## Methods

- **Language**: R
- **Libraries**: `missForest`, `ggplot2`, `dplyr`, `caret`, `glmnet`, `splines`, `gam`, `MASS`, `rpart`, `rpart.plot`, `gbm`
- **Data Visualization**: Created visualizations using `ggplot2` to explore the relationships between features and target variable (SalePrice).
- **Imputation**: Handled missing data using the `missForest` library for non-parametric missing value imputation.
- **Modeling Framework**: Regression techniques such as random forest, gradient boosting, and elastic net were implemented using `caret` and `gbm`.


## Feature Engineering

1. **Handling Missing Values**: Used `missForest` to impute missing data.
2. **Creating New Features**: Engineered new features, such as interaction terms between location and square footage, and polynomial features for continuous variables.
3. **Encoding Categorical Variables**: Applied one-hot encoding for categorical variables.
4. **Normalization**: Some numeric variables were scaled or normalized to ensure models perform optimally.


## Modeling Techniques

1. **Linear Models**: Used `glmnet` for Lasso and Ridge regression to identify the most important features.
2. **Tree-based Models**: Applied `rpart` for decision trees and used `rpart.plot` for visualizing the decision tree structures.
3. **Ensemble Methods**:
   - **Random Forest**: Built with `randomForest` package to capture complex non-linear relationships.
   - **Gradient Boosting**: Implemented using `gbm` to enhance predictive power with boosting techniques.
4. **Generalized Additive Models (GAM)**: Used the `gam` library to fit smooth terms for continuous predictors.
