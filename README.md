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

# Flask Server using Pycharm
## Server.py
Flask server that handles HTTP requests
Exposes APIs for:
- Getting location names 
- Predicting house prices

Uses util.py for actual prediction logic

Configures CORS to allow cross-origin API requests

Key responsibilities:
- Creating Flask application
- Defining APIs for client requests
- Importing util to get required data for response
- Enabling CORS for browser security

## Util.py
Handles actual logic for house price prediction using saved model
- Loads artifacts - scaler, model, columns info
- Supports making predictions for a data instance 
- Contains helper functions for API response

### Key responsibilities
- Loading model and other artifacts needed for prediction
- Data transformation and preprocessing
- Running model prediction
- Exposing supporting functions to server.py

# Creating Web App using VS Code
## app.css

CSS styling for the web interface
- Defines styling for elements like radio buttons, submit button, result display etc
- Imports google font Roboto 
- Sets blur background image

## app.html
HTML template for the web interface

- Contains input fields for area, BHK, bathrooms
- Radio buttons implemented for options 
- Drop down for locations
- Results div to display predicted price 
- JavaScript file linked

## app.js
JavaScript handling backend API calls

- Gets input values selected  
- Makes POST AJAX request to Python backend for prediction
- Displays returned prediction
- Gets list of locations on page load

The key files implement the web interface for getting user inputs and displaying the predicted house price returned by the Python backend.

CSS handles styling to create the actual frontend template. JavaScript sends user data and handles API response. HTML provides the structure.
