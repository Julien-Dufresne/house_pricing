# Trying a new model: Catboost
CatBoost is a gradient boosting machine-learning algorithm based on decision trees. It is especially useful for tabular data and is particularly good when your dataset contains categorical features.
We will skip the Data Review part as it was already done in the Initial Prediction Readme Document. 

## Data Pre-processing
- Splitting the dataset into a data section and a target section
- Splitting the data into a train set (80%) and a test set (20%) so we could train the model on 80% of the dataset, and later on checking the accuracy of this model using the test set that the model would not have seen yet.
- As the houses price variation was very high, we had to scale the target data
- Review manually which categorical data was ordinal or not

## Pre processing, scaler and Pipelines
- Identifying text-category columns (no need to one-hot encode with CatBoost
- Adding MSSubClass to the categorical column list
- Filling NAs to train and test data

## Creating the Catboost Regression model
- Creating the model
- Running Cross_validation:
    > Mean CatBoost CV log-RMSE: 0.1254 (individual error scores:
         > 0.1179, 0.1416, 0.1470, 0.1143, 0.1059

## Fitting the model and predicting prices of test data

Ending up with place number 528 with a best score of 0.12259
<img width="1145" height="119" alt="Screenshot 2026-09-22 at 10 12 53" src="https://github.com/user-attachments/assets/d7a5fb6a-ce49-436a-888a-121b287e4948" />

  
