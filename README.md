Credit Risk Modeling in Python 2022

Udemy course - by 365 Careers

1. Explore Data
+   convert string to numeric
+   date, date difference
+   dummy variables for Discrete Variables
+   null values
+   data prep for PD model
    - define dependent variable 
    - split training and testing dataset
    - data preparation
    - Weight of Evidence
        * discrete variable: use WoE to create subcategories for original variable. Group some subcategories that have similar WoE together 
        * continuous variable: cut all data points of a continuous variable into equal chunk. Calculate WoE for each chunk. Again, group those with similar WoE together

2. PD model
+ Create PD model
    - use all discrete and continuous variables that we have preprocessed as independent variables. 
    - regress using Logistic Regression
    - regress using Logistic Regression with multivariate p-value: use p-values to select variables that have significant explanatory
    - regress using Logistic Regression with multivariate p-value 2: use shortlisted variables only
    - save PD model
+ Model validation
    - use coefficients of Logistic Regression model 2 to predict probability of default of test dataset
    - validate model accuracy
        * confusion matrix
        * Area Under the Curve
        * Gini
        * Kolmogorov-Smirnov
+ Scorecard & Cut Off
    - Scorecard: based on coefficient of regression model 
    - Credit Score: compute credit score for each customer, using above Scorecard
    - Compute PD from Credit Score
    - Choose cut off point

3. PD model monitoring
+ Population Stability Index (PSI)
    - Preprocess the data like in the workbook 1 "Explore Data", but for the new data
    - Compute Scorecard for the new data
+ PSI calculation
+ PSI interpretaion

4. LGD & EAD model, Expected Loss
+ Data Prep: working on only defaulted customers
    - null value for those independent variables
    - Dependent variables
        * compute LGD
        * compute EAD
+ LGD model
    - Stage 1: Logistic Regression: regress on whether the recorvery rate is 0 or not
        * Split train & test
        * Logistic Regression
        * Validate model
            + Predict
            + Compare predict vs actual
            + Confusion Matrix
            + ROC curve
        * Save stage 1 model
    - Stage 2: Linear Regression: for those actual recovery rate is greater than 0, regress their recovery rate
        * Split train & test
        * Logistic Regression
        * Validate model
            + Predict
            + Compare predict vs actual
            + Correlation between predict vs actual
            + evaluat residual
        * Save stage 2 model
    - Combine Stage 1 & Stage 2 model
        * use Stage 2 model to predict recovery rate of test data of Stage 1
        * multiply predict value of Stage 1 with the predicted value of the above --> yield overall LGD
+ EAD model
    - Split train & test
    - Linear Regression
    - Validate model
        * Predict
        * Compare predict vs actual
        * Correlation between predict vs actual
        * evaluat residual
    - Save stage 2 model
+ Expected Loss: for all customers in the portfolio
    - Predict LGD
        * use LGD stage 1 model to predict recovery rate stage 1
        * use LGD stage 2 model to predict recovery rate stage 2
        * multiply the 2 predictions to get recovery rate
    - Predict EAD
        * Predict CCF
        * CCF * funded amount = EAD
    - Predict PD 
        * use PD model: Logistic Regression model 2, saved from workbook 2 "PD Model"
    - Compute EL