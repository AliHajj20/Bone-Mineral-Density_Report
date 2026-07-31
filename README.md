# Bone-Mineral-Density_Report
The Bone Mineral Density Study is a longitudinal investigation designed to identify risk factors associated with osteoporosis. 
The dataset includes information from 10,000 individuals. 
This project aims to analyze the data using appropriate statistical and computational methods to determine the key predictors influencing bone mineral density (BMD) and contributing to osteoporosis risk.

# Overview

This project explores predictive modeling of bone mineral density (BMD) score using a large tabular dataset (10,000 observations, 31 variables including biochemical markers, genetic variants (SNPs), and lifestyle factors). Three supervised regression models — Linear Regression (Elastic Net), Random Forest, and K-Nearest Neighbours (KNN) — are trained, tuned, and compared using the tidymodels framework in R to identify which predictors most strongly influence bone mineral density and which modeling approach best captures the relationship between predictors and outcome.

# Workflow:

1- Data import: using the **read_tsv()** function

2- Exploratory analysis: Full scatterplot matrix using the **ggpairs()** function.

3- Train/test split — 75/25 split with 5-fold cross-validation (vfold_cv) for hyperparameter tuning.

## Linear Regression
4- Linear regression model implementation: 
i- define the type of model
ii- set engine of model (computational backend of the model)
iii- create the engine of the model, by defining the outcome vacriable (bone_mineral_density_score)
iv- used the step_dummy() function to convert categorical predictors into numeric dummy variables, making them suitable for models like linear regression.
v- applied step_normalize() to normalize all numeric predictor variables, for the purpose of ensuring all predictors have the same scale
vi- created the workflow that includes the model type with its engine and the recipe in a single object.
vii- performed hyperparameter tuning. I defined the grid of combinations of penalty and mixture values (3 values each) that will be tested during hyperparameter tuning to find the best model. Using cross-validation, I evaluated all parameter combinations to determine their effect on model performance, measured by RMSE and R². The best-performing model, selected based on the lowest RMSE, had penalty = 0 and mixture = 0.05, achieving an RMSE of 0.447 and an R² of 0.999998, indicating excellent predictive accuracy.
viii- Fitted the developed model with the best parameters on the training data
ix- Used the fitted model to perform predictions on the testing subset.
The following plot represents the predictions: 

