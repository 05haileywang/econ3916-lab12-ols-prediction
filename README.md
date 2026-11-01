# econ3916-lab12-ols-prediction

# Lab 12: Predictive Modeling — The Same Machinery, A New Scorecard

## Overview
This lab explores the difference between using ordinary least squares (OLS) regression for estimation and prediction. Using the California Housing dataset, I compared different methods of estimating regression coefficients, examined how adding predictors affects R-squared, and evaluated model performance using training and test data.

## Methods
- Used the California Housing dataset containing 20,640 observations
- Compared OLS regression coefficients calculated using the closed-form solution, statsmodels, and scikit-learn
- Added random noise variables to examine how R-squared and adjusted R-squared change
- Split the dataset into 80% training data and 20% test data
- Evaluated predictive performance using root mean squared error (RMSE)
- Compared models using median household income alone and all eight available predictors
- Examined how censoring of house values affects regression estimates and prediction accuracy

## Key Findings

**OLS Estimation:** All three methods produced the same regression coefficients. A $10,000 increase in median household income was associated with an approximately $41,794 increase in median house value.

**R-squared:** Adding random noise variables increased in-sample R-squared, even though these variables did not provide meaningful information. This demonstrated why R-squared alone is not a reliable measure of predictive performance.

**Prediction:** The model using only median household income had a test RMSE of 0.8421 ($84,210), compared to 0.7456 ($74,560) for the model using all eight predictors. Including additional predictors reduced test RMSE by approximately $9,650.

**Estimation vs. Prediction:** A statistically significant regression coefficient does not necessarily mean that a model will predict new observations accurately. Estimation focuses on understanding relationships between variables, while prediction focuses on minimizing errors on unseen data.

## Reflection

This lab demonstrated the importance of choosing the appropriate evaluation method based on the purpose of the regression. While R-squared and statistical significance can help us understand relationships within a dataset, they do not necessarily indicate how accurately a model will predict new observations. I also learned that adding more predictors can improve in-sample fit without improving predictive accuracy. Using a separate test set provides a better way to evaluate how well a model generalizes to new data.
