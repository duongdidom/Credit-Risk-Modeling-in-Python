Credit Risk Modeling in Python 2022

Udemy course - by 365 Careers

1. Explore Data
├── convert string to numeric
├── date, date difference
├── dummy variables for Discrete Variables
├── null values
├── data prep for PD model
│   ├── define dependent variable 
│   ├── split training and testing dataset
│   ├── data preparation
│   ├── Weight of Evidence
│   │   ├── discrete variable: use WoE to create subcategories for original variable. Group some subcategories that have similar WoE together 
│   │   ├── continuous variable: cut all data points of a continuous variable into equal chunk. Calculate WoE for each chunk. Again, group those with similar WoE together

2. PD model
├── Create PD model
│   ├── use all discrete and continuous variables that we have preprocessed as independent variables. 
│   ├── regress using Logistic Regression
│   ├── regress using Logistic Regression with multivariate p-value: use p-values to select variables that have significant explanatory
│   ├── regress using Logistic Regression with multivariate p-value 2: use shortlisted variables only
├── Model validation
│   ├── use coefficients of Logistic Regression model 2 to predict probability of default of test dataset
│   ├── validate model accuracy
│   │   ├── confusion matrix
│   │   ├── Area Under the Curve
│   │   ├── Gini
│   │   ├── Kolmogorov-Smirnov
├── Scorecard & Cut Off
│   ├── Scorecard: based on coefficient of regression model 
│   ├── Credit Score: compute credit score for each customer, using above Scorecard
│   ├── Compute PD from Credit Score
│   ├── Choose cut off point


