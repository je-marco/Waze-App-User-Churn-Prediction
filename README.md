# Predicting Churn of Waze App Users  

## Overview
The goal of this project is to use the Waze app user data to build a binomial logistic regression model, random forest model and extreme gradient boosting (XGBoost) model to predict monthly user churn. For the purposes of this project, churn quantifies the number of users who have uninstalled or stopped using the app.

The XGBoost model fits the data better than the random forest and binomial regression models. However, the modeling effort reveals that the current data is inadequate to predict user churn consistently and that there is a great need for additional data or features that strongly correlate with user churn. 

## Business Understanding   
An effective churn prediction model will help improve app user retention and answer questions such as: 
  * Who are the users most likely to churn? 
  * Why do users churn? 
  * When do users churn?

If the model can identify a subset of users who are at high risk of churning, Waze can proactively engage these users with special offers to try and retain them. Otherwise, Waze may simply lose these users without knowing why.

## Data Understanding
The data came from a sample data collected from the users of the Waze app called [waze_dataset.csv](https://github.com/je-marco/Waze-App-User-Churn-Prediction/blob/aa80333332523b7df8b85122a48d70c7d8c6300e/waze_dataset.csv). The dataset contains **14,999 rows**—each representing one unique user and **13 columns**. The features include the user's monthly driving information such as number of sessions, distance driven, duration of drives and driving days. It also includes some information from when the user starts using the app such as total sessions, total number of navigations to the user's favorite places and the user's tenure. 

The pie chart below shows the breakdown of how may users churned vs retained in the dataset.

![pie_chart](https://github.com/je-marco/Waze-App-User-Churn-Prediction/blob/b1b737b465b5d1f30b96f721d0bf488ce6ed0122/pie_retainedvschurned.png)

New features were engineered to help improve the performance of the models such as distance driven per hour, total sessions per day, distance driven per driving day, etc.

## Modeling and Evaluation
Extreme gradient boosting is the champion model and was used to determine which features are the strong predictors of user churn. The plot below shows that user's tenure (*n_days_after_onboarding*), distance driven per hour (*km_per_hour*) and total sessions per day were the Top 3 predictors. 

![feature_importance](https://github.com/je-marco/Waze-App-User-Churn-Prediction/blob/08842efa522d966d6c24927fbc95dcd75090e20c/feature_importance.png)

The model has a moderate precision score (42% of its positive predictions are correct) but with poor recall, with only 19% churned users identified during testing. This means that the model makes a lot of false negative predictions and fails to capture users who will churn.

## Conclusion and recommendation
Because of the model's poor performance, this model should not be used to make important business decisions. It is recommended only to use the key insights from this project to guide further exploration such as collecting data/features that would accurately predict user churn such as:
 *  Drive-level information for each user: drive times, geographic locations
 *  More granular data to know how users interact with the app: How often users report or confirm road hazard alerts?
 * Monthly count of unique starting and ending locations each driver inputs

## Note
*Throughout this project, you'll see references to the problem-solving framework, PACE. The python notebook components are labeled with the respective PACE stages: Plan, Analyze, Construct, and Execute.*

## Link to data dictionary, project proposal, and executive summaries
* [Data Dictionary](https://docs.google.com/document/d/1C0CUArMaY5is3cvUfBC9WVou2BPSOze-xY1zwzP0tG0/edit?usp=sharing)
* [Project Proposal](https://docs.google.com/document/d/1M8E2HE4Cc0hYvtsiZMtJ_ICMAlQyyw6Nvt1jSjIEENo/edit?usp=sharing)

Executive summaries:
* [Preliminary Data Summary](https://docs.google.com/presentation/d/1109xtLRtJyVJ358GXKAXt9SHt9MB5N-pm4IR2zx68LU/edit?usp=sharing)
* [Exploratory Data Analysis](https://docs.google.com/presentation/d/1noWXBPMM9l84pXsyfJjuDne_d7jFc4Fe7YbBS3Ixymc/edit?usp=sharing)
* [Hypothesis Testing](https://docs.google.com/presentation/d/1hs6YRyOOht6XBvi8IGzxcaKh8cBVWGkM6GjI7w0vDIk/edit?usp=sharing)
* [Regression Modeling](https://docs.google.com/presentation/d/1Otnj9wWdlDhhTORXde5G6fujx_pdnttr7QL2RwX0c-8/edit?usp=sharing)
* [Machine Learning Model](https://docs.google.com/presentation/d/10wSPMdx_Tev-j-A5k_wkXXpAbUS_eFZXua8Gy4oek7M/edit?usp=sharing)

