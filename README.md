# AP_MSCS634_Assignment
# Advanced Big Data and Data Mining

# Overview

This lab explores multiple regression techniques using the Diabetes Dataset from sklearn.datasets. The objective is to understand how different regression models behave, compare their predictive performance, and examine how regularization techniques help reduce overfitting and improve generalization.

The following models were implemented and evaluated:

Simple Linear Regression
Multiple Linear Regression
Polynomial Regression
Ridge Regression
Lasso Regression
Model performance was evaluated using:
Mean Absolute Error (MAE)
Mean quared Error (MSE)
Root Mean Squared Error (RMSE)
R² Score

Multiple visualizations were created to analyze prediction behavior and model complexity.

# Dataset Description

The Diabetes Dataset contains 442 samples and 10 standardized health-related features including:
Age,Sex,BMI,Blood Pressure,Serum measurements (s1–s6)

The target variable represents a quantitative measure of disease progression one year after baseline.
The dataset contains no missing values, and features are already normalized.


# Data Exploration

Checked dataset dimensions and summary statistics.
Verified absence of missing values.
Visualized the distribution of the target variable using a histogram.

The target variable shows moderate spread with no extreme skewness.

# Simple Linear Regression (BMI → Target)

A simple regression model was built using BMI as the only predictor.
Performance:
R² ≈ 0.23

BMI alone explains approximately 23% of the variance in disease progression, indicating that the problem is multi-factorial.

A regression line visualization confirmed a weak-to-moderate linear relationship.

# Multiple Linear Regression

All 10 features were used to predict disease progression.
Performance:
R² ≈ 0.45

Using multiple physiological features significantly improves prediction accuracy. This confirms that disease progression depends on multiple correlated health variables.
An “Actual vs Predicted” scatter plot showed stronger alignment compared to simple regression.

# Polynomial Regression

Polynomial features (degree = 2) were added to introduce non-linearity.

Performance:

R² ≈ 0.41

Performance slightly decreased compared to multiple regression. This suggests that:
The dataset does not contain strong nonlinear patterns.
Adding complexity can introduce mild overfitting.
A separate visualization comparing polynomial degrees demonstrated the bias–variance tradeoff:
Higher degrees increased training R².
Test R² stabilized or declined.
This clearly illustrated overfitting behavior.

# Regularization (Ridge & Lasso)

To control model complexity and reduce overfitting, Ridge and Lasso regression were applied.

Ridge Regression

R² ≈ 0.42

Shrinks coefficients but retains all features.

Lasso Regression

R² ≈ 0.47 (Best performing model)

Performs feature selection by driving some coefficients to zero.

Key Insight:
Lasso produced the highest R² score, suggesting that eliminating less important features improves generalization.

An alpha vs R² visualization demonstrated how increasing regularization strength impacts model performance.

# Model Comparison
Model	                  R² Score
Simple Linear	           0.23
Multiple Linear	           0.45
Polynomial (Degree 2)	   0.41
Ridge	                   0.42
Lasso	                   0.47

Best Model: Lasso Regression

This indicates that moderate regularization and implicit feature selection improve predictive performance.

# Key Insights

Disease progression is influenced by multiple physiological factors.
Increasing model complexity does not guarantee better performance.
Polynomial expansion can introduce overfitting if nonlinear structure is weak.
Regularization improves generalization.
Lasso can outperform Ridge by eliminating irrelevant features.

# Challenges & Decisions

Care was taken to avoid data leakage during polynomial transformation.
Different alpha values were tested to analyze regularization strength.
Visualization was used extensively to interpret model behavior rather than relying solely on metrics.

# Conclusion

This lab demonstrates how regression models evolve from simple to more complex forms and highlights the importance of:

Bias–variance tradeoff
Overfitting control
Regularization techniques
Model comparison

Among all models tested, Lasso Regression achieved the best generalization performance, indicating that feature selection and controlled model complexity are critical for predictive modeling.