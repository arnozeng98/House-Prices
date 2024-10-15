# House Prices - Advanced Regression Techniques

This repository contains my work for the Kaggle competition "[House Prices: Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)". The goal of this project is to predict the final sale prices of homes in Ames, Iowa using a dataset of 79 features that describe various aspects of the houses.


## Table of Contents

1. [Competition Overview](#competition-overview)
2. [Project Structure](#project-structure)
3. [Methods](#methods)
4. [Feature Engineering](#feature-engineering)
5. [Modeling Techniques](#modeling-techniques)
6. [Results](#results)
7. [How to Run](#how-to-run)
8. [Citation](#citation)


## Competition Overview

![housesbanner](https://storage.googleapis.com/kaggle-media/competitions/House%20Prices/kaggle_5407_media_housesbanner.png)

Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.

With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.

### Practice Skills

- Creative feature engineering
- Advanced regression techniques like random forest and gradient boosting

### Acknowledgments

The [Ames Housing dataset](https://www.amstat.org/publications/jse/v19n3/decock.pdf) was compiled by Dean De Cock for use in data science education. It's an incredible alternative for data scientists looking for a modernized and expanded version of the often cited Boston Housing dataset. 

Photo by [Tom Thain](https://unsplash.com/@tthfilms) on Unsplash.

### Evaluation

#### Goal
It is your job to predict the sales price for each house. For each Id in the test set, you must predict the value of the SalePrice variable. 

#### Metric
Submissions are evaluated on [Root-Mean-Squared-Error (RMSE)](https://en.wikipedia.org/wiki/Root_mean_square_deviation) between the logarithm of the predicted value and the logarithm of the observed sales price. (Taking logs means that errors in predicting expensive houses and cheap houses will affect the result equally.)

#### Submission File Format
The file should contain a header and have the following format:

```csv
Id,SalePrice
1461,169000.1
1462,187724.1233
1463,175221
etc.
```

You can download an example submission file (sample_submission.csv) on the [Data page](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data).

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

## Citation

Anna Montoya, DataCanary. (2016). House Prices - Advanced Regression Techniques. Kaggle. <br/>
https://kaggle.com/competitions/house-prices-advanced-regression-techniques
