# Predicting Churn of Waze App Users  

## Overview
The goal of this project is to use the Waze app user data to build a binomial logistic regression, random forest model and extreme gradient boosting(XGBoost) model to predict whether the user will churn or not. For the purposes of this project, churn quantifies the number of users who have uninstalled or stopped using the app. This project focuses on monthly user churn. 

*Throughout this project, you'll see references to the problem-solving framework, PACE. The python notebook components are labeled with the respective PACE stages: Plan, Analyze, Construct, and Execute.*


## Business Understanding   
An effective churn prediction model will help improve app user retention and answer questions such as: 
  * Who are the users most likely to churn? 
  * Why do users churn? 
  * When do users churn?

If the model can identify a group of users who are at high risk of churning, Waze can proactively engage these users with specail offers to try and retain them. Otherwise, Waze may simply lose these users without knowing why.

## Data Understanding
The data came from a sample data collected from the users of the Waze app called [waze_dataset.csv](https://github.com/je-marco/Waze-App-User-Churn-Prediction/blob/aa80333332523b7df8b85122a48d70c7d8c6300e/waze_dataset.csv). The dataset contains **14,999 rows**—each representing one unique user and 13 columns. The features included user's driving information which includes number of sessions, distance driven, duration of drives and driving days during the last month. It also includes some information from when the user starts using the app such as total sessions, total navigations to the user's favorite places and the user's tenure. 

The pie chart below show the breakdown of how may users churned vs retained in the dataset.



## Modeling and Evaluation


## Conclusion
