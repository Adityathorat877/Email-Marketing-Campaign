# 📬 Email Marketing Campaign Optimization (ML Case Study)

This Jupyter Notebook provides an end-to-end machine learning pipeline for analyzing and predicting click-through rates (CTR) in email campaigns. The main steps include data preprocessing, model building, evaluation, and segmentation analysis. Additionally, it estimates the improvement in CTR by targeting high-probability users, and performs a feature importance analysis.

Table of Contents
Introduction

1. Data Preprocessing

2. Model Building and Evaluation

3. CTR Improvement Estimation

4. Segmentation Analysis

5. Conclusion

## 1. Introduction
This notebook aims to predict the likelihood of a user clicking on an email based on historical email data, such as email text, version, and user information. The following datasets are used:

email_table.csv: Contains information about the emails (e.g., email ID, text, version, weekday, user country).

email_opened_table.csv: Contains email IDs of the emails opened by users.

link_clicked_table.csv: Contains email IDs of the emails that users clicked on links.

The final goal is to build a predictive model that estimates the click-through rate (CTR) for each email and helps optimize email targeting strategies.

## 2. Data Preprocessing
Key steps:
Labeling: Two new columns (opened, clicked) are added to the email_df to indicate whether the email was opened or clicked by the user.

Categorical Encoding: The categorical features (email_text, email_version, weekday, user_country) are converted to dummy variables using one-hot encoding.

Feature and Label Selection: The features used for the model include the encoded categorical columns and other relevant features, while the label is whether or not the user clicked on the email.

3. Model Building and Evaluation
Steps:
Train-Test Split: The data is split into training and testing sets (80-20 split).

Modeling: An XGBClassifier is used to train a classification model for predicting whether a user will click on an email.

Evaluation: The model is evaluated using classification metrics such as precision, recall, F1-score, and the ROC AUC score.

Output:

A classification report is printed, showing the performance of the model.

The ROC AUC score provides a measure of the model's ability to distinguish between clicked and non-clicked emails.

## 4. CTR Improvement Estimation
The notebook estimates how much the CTR can be improved by only targeting the top 30% of users with the highest predicted click probabilities. The following steps are performed:

Probability Thresholding: The 30% of users with the highest predicted probabilities are selected.

Improved CTR Calculation: The actual click rate for the top 30% is calculated and compared to the original CTR.

Output:

The estimated CTR improvement is printed, showing the potential uplift from targeted sending.

## 5. Segmentation Analysis
The notebook performs an analysis of CTR across different email segments based on email_text, email_version, and weekday. The following steps are performed:

Grouping: The dataset is grouped by email_text, email_version, and weekday, and the average click-through rate is calculated for each segment.

Output:

A summary table with segment-wise CTR values is printed, which can help identify which segments perform the best.


## 6. Conclusion
The notebook demonstrates how to predict email click-through rates (CTR) using machine learning, and how to improve email targeting by focusing on users with high click probability. By analyzing email segments and the importance of features, businesses can gain valuable insights into optimizing their email campaigns for better engagement and performance.

Requirements
Ensure the following libraries are installed:

pandas

numpy

scikit-learn

xgboost

matplotlib

seaborn





