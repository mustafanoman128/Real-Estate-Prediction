# Real-Estate-Prediction
House Price Prediction in Bengaluru
## Overview
This project aims to predict house prices in Bengaluru based on location, square footage, number of bedrooms, bathrooms etc. A model is trained on the Bengaluru House Price dataset from kaggle.

## Data Cleaning
### The data is cleaned by:

- Converting location to lower case
- Removing white spaces from location
- Extracting numeric component from size column
- Handling missing values
- Removing outliers based on domain knowledge and statistical methods
## Feature Engineering
Additional features like price per square feet are constructed. Location is encoded into dummy variables.

## Model Building
Multiple models like Linear Regression, Lasso Regression and Decision Tree Regression are evaluated. Hyperparameter tuning is done using GridSearch Cross Validation. Linear Regression provides the best score.

## Model Persistance
The model is persisted by pickling to allow loading without retraining. The pickled model file along with the json file containing data columns is provided.

## Model Evaluation:

- R^2 Score on Test data: 0.85
- Cross Validation Scores: [0.80, 0.88, 0.89, 0.81, 0.84]
## Usage
To make predictions using the pickled model:
1) Import pickle and json
2) Load columns json
3) Load model from pickle
4) Construct data row with location, sqft, bath, bhk
5) Get location index from columns
