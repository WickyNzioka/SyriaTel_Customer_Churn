## Churn Prediction for SyriaTel

### Business Understanding

#### Problem Statement
The objective is to develop a classifier that predicts whether a customer is likely to terminate their services with SyriaTel, a telecommunications company. This binary classification task aims to identify patterns in customer behavior and demographic information indicative of potential churn. The ultimate goal is to help SyriaTel reduce the financial impact of customer churn by implementing proactive retention strategies. Additionally, the analysis aims to create a reliable churn rate prediction model by thoroughly examining essential features based on historical company data.

#### Key Questions:
1. What indicators suggest a customer is likely to churn?
2. Which state has the highest churn rate?
3. Does the type of customer service affect churn?
4. What is the correlation between minutes and churn?
5. Does the presence of international calls affect the churn rate?
6. Does the account length impact churn?
7. How does the charge affect churn?

#### Data Understanding
The dataset includes the following features:
- State, account length, area code, phone number
- Subscription plans: International plan, voice mail plan
- Call metrics: Number of voice mail messages, total minutes and charges for day, evening, night, and international calls, total number of calls
- Customer service calls
- Churn indicator

Exploratory Data Analysis (EDA) involved visualizing the distribution of numeric features, subscription plan distribution, minutes distribution, churn distribution, area code distribution, churn distribution by state, and correlation of features.

#### Data Preparation
Data preparation steps included converting column names to lowercase, replacing 'False'/'True' with 0/1 for the churn column, handling missing values and duplicates, and encoding categorical variables.

#### Data Modeling
Two models were employed: Logistic Regression, Random Forest, Decision Trees and XGBoost.

##### Logistic Regression:
- Achieved an accuracy of 85.3%, precision of 52.94%, recall of 17.82%, F1-score of 26.67%, and AUC of 0.575.
- The confusion matrix revealed 18 true positives, 551 true negatives, 15 false positives, and 83 false negatives.

##### Random Forest:
- Achieved an accuracy of 92.9%, F1-score of 77%, and AUC of 0.77.
- The confusion matrix revealed 55 true positives, 564 true negatives, 2 false positives, and 46 false negatives.

##### Decision Trees
- The model achieved aan accuracy of 92.2%, slightly lower that the random forest model.

##### XGBoost
- This model had an accuracy of 95%,but an AUC of 0.87generally performing better than all models except Random Forest that had an AUC of 0.93

Hyperparameter tuning was performed using GridSearchCV to optimize the Random Forest model.

      #### Model Evaluation
ROC curves were plotted to compare the performance of the Logistic Regression and Random Forest models. Random Forest outperformed Logistic Regression with a higher AUC.

#### Feature Importance
- From the graph, we can conclude the top features are:
    - Total day minutes
    - Customer service calls
    - Total eve minutes
    - Internal plan (Those that had subscribed)
    - Total minutes

##### Conclusion
The Random Forest model emerged as the superior model for predicting customer churn. Key features influencing churn were identified, providing valuable insights for retention strategies.

##### Recommendation
Recommendations based on the analysis include improving call quality, enhancing customer service, and offering better plans for customers with international subscriptions. These strategies aim to reduce churn and improve customer retention for SyriaTel.
