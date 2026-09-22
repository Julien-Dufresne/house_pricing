# Trying a new model: Catboost
CatBoost is a gradient boosting Machine Learning algorithm based on decision trees. It is especially useful for tabular data and performs particularly well when a dataset contains categorical features.

We will skip the Data Review section, as this was already covered in the initial prediction README document.

## Preprocessing and Categorical Features

One of the advantages of CatBoost is its ability to handle categorical features directly, without requiring OneHotEncoder.

The following preprocessing steps were performed:

- Identifying the categorical (object) columns.
- Adding MSSubClass to the list of categorical features.
- Filling missing (NaN) values in both the training and test datasets.
- No scaling or One-Hot Encoding was required for the categorical features, as CatBoost can process them directly.


## Creating the Catboost Regression model
- Creating a CatBoostRegressor model.

- Evaluating the model using Cross-Validation.

Cross-Validation Results

- Mean CatBoost CV log-RMSE: 0.1254

- Individual fold scores:
    - 0.1179
    - 0.1416
    - 0.1470
    - 0.1143
    - 0.1059

The Cross-Validation results showed an improvement compared with our previous Stacking model, which achieved a mean CV log-RMSE of 0.1311.

## Fitting the model and predicting prices of test data

After evaluating the model with Cross-Validation:

- The CatBoost model was fitted to the training data.
- The fitted model was used to predict SalePrice for the Kaggle test dataset.
- The log-transformed predictions were converted back to the original house-price scale.
- The predictions were formatted and submitted to Kaggle.

## Kaggle Results

The CatBoost submission achieved:

- Kaggle Score: 0.12259
- Leaderboard Position: 528

This was an improvement over our previous submission score of 0.12950, showing that CatBoost performed better on this dataset than our initial Stacking model.


<img width="1145" height="119" alt="Screenshot 2026-09-22 at 10 12 53" src="https://github.com/user-attachments/assets/d7a5fb6a-ce49-436a-888a-121b287e4948" />

  
