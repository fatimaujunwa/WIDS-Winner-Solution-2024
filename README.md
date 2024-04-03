# WIDS CHALLENGE 2024- 1ST PLACE SOLUTION
We are thrilled to announce that our team secured first place in this challenge, and so we're excited to share the strategies that propelled us to this success.

Our approach was centered on data preprocessing, feature engineering, and model ensemble techniques. Here's an overview of how we tackled the challenge:
## Challenge Task
Challenge task:
You will be asked to predict if the patients received metastatic cancer diagnosis within 90 days of screening.

## Data Preprocessing
We recognized the potential of the location features to introduce noise rather than valuable predictive power, so we made the decision to drop most of these features. However, we retained pollutant features (NO2, ozone, and PM25).

## Feature Engineering
We then combined various pollutants into a single feature. Our goal was to capture the overall environmental impact in a more digestible form for our models. Additionally, we introduced flags for critical variables:

A flag for metastatic_cancer_diagnosis_code with a length of 4 to identify specific diagnosis codes of interest.
A flag for breast_cancer_diagnosis_desc containing the term "female". This was inspired by some of the discussions in the discussion forum.
We applied one-hot encoding to a carefully selected set of features, including payer_type, patient_race, and breast_cancer_diagnosis_desc, among others.

## Model Selection and Ensemble Strategy
Our model architecture consisted of base models and a meta-model:

Base Models: We utilized two CatBoost models and one XGBoost model. These models were chosen for their robust handling of categorical features and their ability to handle the missing data in our dataset.
Meta-Model: A Logistic Regression model served as our meta-model.
Validation Technique
We employed a Stratified K-Fold cross-validation approach with 10 folds.

## Performance
Our strategy resulted in a best local cross-validation (CV) score of 0.8025, with a private leaderboard score of 0.801 (±0.001) and a public leaderboard score of 0.807 (±0.001). Additionally, our best single ensemble on the public leaderboard achieved a local CV of 0.799, with scores of 0.81 on the public leaderboard and 0.801 on the private leaderboard.

We're grateful for the opportunity to participate in this competition and look forward to applying the insights gained to future challenges. You can find the code at https://www.kaggle.com/code/ujunwafatima/wids-2024-2nd-place
