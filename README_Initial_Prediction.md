# house_pricing

## Objectives:
As part of my Data Science and ML studies, we had as a task to practice our skills by participating to a Kaggle competition, where developers and data scientists from all the words can practice by participating to several competitions. 

The goal of the competition we entered, (House Prices - Advanced Regression Techniques) was to build a Machine Learning model that would learn from a data set containing different informations about houses that have been sold and the price they have been sold, and use this model to predict prices of other houses when given just their related information. 

## Data Review
After reviewing the data, we could observe about the database: 
- For each house, we had 80 different parameters, composed of both categories (object) and numerical data (integer and floats).
- The target (SalePrice) was in an integer format
- Some values were null
- The dataset included 1460 entries (houses)

## Data Preprocessing
- Splitting the dataset into a data section and a target section
- Splitting the data into a train set (80%) and a test set (20%) so we could train the model on 80% of the dataset, and later on checking the accuracy of this model using the test set that the model would not have seen yet.
- As the houses price variation was very high, we had to scale the target data
- Review manually which categorical data was ordinal or not

### Creation of the pipeline
- Splitting the data set into three categories:
    > Numerical Data
    > Categorical Ordinal Data
    > Categorical Nominal Data
- Creating a preprocessor for each categories:
    > Using SimpleImputer to compute data where NA was present
    > Scaling numerical Data
    > Using Ordinal Encoder using preselected ordinal categories' names
    > Using OneHotEncoder for the rest of the nominal categorical data

## Baseline model and Pipeline building

- Creating of a baseline model and evaluating it with Cross Validation to see the ability of this model to generalize

- Building the Pipeline that would stack several ML models:
      > RandomForestRegressor
      > GradientBoostingRegressor
      > Support Vector Regression

## Fitting and evaluating
- Fitting the model and evaluating using cross_val_score:
  > Stacking CV log-RMSE: 0.1311
  > Standard deviation: 0.0208
  

## Creating Predictions using the pipeline and modifying those predictions to scale them
- Checking which model contributed the most to the prediction:
    > Random Forest        0.125593
    > Gradient Boosting    0.705594
    > SVR                  0.180033

## Sending those initial predictions through the Housing Competitions:
Root-Mean-Squared-Error: 0.12950
