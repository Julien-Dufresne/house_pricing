# house_pricing

## Objectives:
As part of my Data Science and Machine Learning studies, we were given the task of practicing our skills by participating in a Kaggle competition, where developers and data scientists from around the world can practice their skills by taking part in various competitions.

The goal of the competition we entered, House Prices - Advanced Regression Techniques, was to build a Machine Learning model that could learn from a dataset containing different information about houses that had been sold, including their sale prices.

The model would then use this information to predict the prices of other houses based on their characteristics.

## Data Review
After reviewing the dataset, we made the following observations:
- For each house, we had 80 different features, composed of both categorical (object) and numerical data (int and float).
- The target variable (SalePrice) was stored as an integer.
- Some values were missing (NaN).
- The dataset included 1,460 entries (houses).

## Data Preprocessing
- Splitting the dataset into:
    - Features (X)
    - Target (y)
- Splitting the data into:
- Training set: 80%
- Test set: 20%

This allowed us to train the model on 80% of the dataset and later evaluate its performance using the remaining 20%, which the model had not seen during training.

As house prices had a large variation and a skewed distribution, we applied a log transformation to the target (SalePrice).

Manually reviewing the categorical features to determine which ones were ordinal and which ones were nominal.

### Creation of the pipeline
The dataset was divided into three categories:

- Numerical Data
-  Categorical Data
- Nominal Categorical Data

A specific preprocessing approach was created for each category:

- Numerical Data
    - SimpleImputer to handle missing (NaN) values
    - Scaling of numerical features

- Ordinal Categorical Data
    - SimpleImputer to handle missing values
    - OrdinalEncoder using predefined ordinal category orders

- Nominal Categorical Data
    - SimpleImputer to handle missing values
    - OneHotEncoder for nominal categorical features

These preprocessing steps were combined into a single preprocessor.

## Baseline model and Pipeline building
A baseline model was first created and evaluated using Cross-Validation to estimate the model's ability to generalize to unseen data.

A Stacking Regressor was then created by combining several Machine Learning models:

- RandomForestRegressor
- GradientBoostingRegressor
- SVR (Support Vector Regression)

The preprocessing steps and the Stacking Regressor were then combined into a complete Machine Learning pipeline.

## Fitting and evaluating
The model was evaluated using cross_val_score.
Results:

    - Stacking CV log-RMSE: 0.1311
    - Standard deviation:   0.0208
  
The Root Mean Squared Error (RMSE) was used as the main evaluation metric.
A lower RMSE indicates better predictions.

## Creating Predictions using the pipeline and modifying those predictions to scale them
Creating Predictions

After training the pipeline, predictions were generated for the unseen data.

Since the target variable had been log-transformed before training, the predictions were transformed back to the original house-price scale before creating the final submission.

We also checked the contribution of each model to the final stacked prediction:
Model                                                Coefficient

Random Forest                                        0.125593

Gradient Boosting                                    0.705594

SVR                                                  0.18003

The Gradient Boosting model had the largest coefficient in the final estimator, indicating that it had the strongest influence on the final predictions.

## Sending those initial predictions through the Housing Competitions:
Kaggle Submission

Finally, the predictions were submitted to the House Prices - Advanced Regression Techniques Kaggle competition.

The initial submission achieved:

- Root Mean Squared Error: 0.12950

The Kaggle score was slightly better than our average Cross-Validation score of 0.1311, showing that the model performed similarly on completely unseen competition data.    - SimpleImputer to handle missing values
    - OneHotEncoder for nominal categorical features

These preprocessing steps were combined into a single preprocessor.
