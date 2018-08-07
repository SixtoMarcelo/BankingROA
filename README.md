# BankingROA
Explanatory variables predicting bank ROAs

Key predictors:
Net Interest Margin %
Loan to Deposit Ratio %
Deposit Growth Rate %
Cost of Funds %
Ops Exp / Ops Rev %
Charge-Offs / Avg Loans %
1-yr and 5-yr CD Rate %

Captured 3 key periods:
Q1 2007 Pre-Recession
Q1 2009 Recession
Q1 2018 Recovery

Arbitrary Filtering:
Entities/Banks with less than 50% predictors available
Predictors/Financial measures with more than 25% missingness
Correlation of .8 was used as a cutoff

Imputation, Transformation, Sampling:
Stratified median imputation based on time period strata
As part of the original design, external variables, were evaluated for near zero variance and consequently dropped
For ROAA (our response) 100 was added, this allows negatives to be log transformed
Feature engineering, divided loans by deposits for effect
Divided 70/30 training/test, used 10-fold CV with 10 repetitions on the train

Tuned Models:
Multivariate Adaptive Regression Spline (MARS)
Elastic Net
SVM (Radial and Linear)
Partial Least Squares (PLS)
Ridge Regression
Linear Model with PCA Pre-Processing
Linear Regression
