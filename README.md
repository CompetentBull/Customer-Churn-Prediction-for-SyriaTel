# Customer-Churn-Prediction-for-SyriaTel

## Overview

Customer churn is a major challenge within the telecommunications industry because losing customers directly affects company revenue and long-term profitability. Retaining existing customers is generally more cost-effective than acquiring new ones, making churn prediction an important business problem.

This project applies machine learning techniques to predict whether a customer is likely to churn (leave the company) based on their service usage patterns and account behavior. The project follows the CRISP-DM framework, including business understanding, data understanding, data preparation, modeling, evaluation, and deployment recommendations.

The primary objective of this project is to help SyriaTel identify high-risk customers early so that proactive retention strategies can be implemented.


# Business and Data Understanding

## Business Understanding

The main stakeholder for this project is SyriaTel’s customer retention and marketing teams. These departments can use predictive analytics to identify customers who are likely to leave the company and intervene before churn occurs.

By accurately predicting churn, SyriaTel can:
- Reduce customer loss
- Improve customer satisfaction
- Increase customer retention
- Protect company revenue
- Improve decision-making through data-driven strategies

The project specifically focuses on classification modeling because the business problem involves predicting two possible outcomes:
- Customer stays
- Customer churns


## Data Understanding

The dataset contains information for 3,333 telecommunications customers and includes variables related to:
- Account information
- Customer service interactions
- Call usage behavior
- International plans
- Voice mail plans
- Churn status


### Initial Data Inspection

During the data understanding phase:
- The dataset was inspected for missing values
- Duplicate records were checked
- Variable types and distributions were analyzed

Findings:
- No missing values were identified
- No duplicate records were found
- The dataset was relatively clean and suitable for analysis

### Key Observations

Exploratory Data Analysis revealed several important churn patterns:
- Customers with international plans were more likely to churn
- Customers making many customer service calls had higher churn rates
- Customers with voice mail plans were less likely to churn
- The dataset was imbalanced, with only approximately 14.5% churn customers

These insights helped guide the modeling and business recommendation phases.

# Data Preparation

Several preprocessing and cleaning steps were performed before modeling:

### Data Cleaning
- Removed irrelevant columns such as:
- -'state'
- 'area code'
- 'phone number'
 

### Feature Engineering and Transformation
- Encoded categorical variables into numerical format
- Removed highly correlated charge variables to reduce multicollinearity
- Scaled numerical features for Logistic Regression modeling

### Exploratory Data Analysis
EDA was conducted using:
- Count plots
- Box plots
- Correlation heatmaps

The analysis helped identify relationships between customer behavior and churn.


# Modeling

Multiple classification models were developed and compared.

## 1. Baseline Logistic Regression

A baseline Logistic Regression model was first developed to establish a simple benchmark model.

Results:
- Accuracy: 85%
- Poor recall for churn customers (17%)

The model performed well overall but failed to identify many actual churn customers.


## 2. Improved Logistic Regression

To address class imbalance, an improved Logistic Regression model using balanced class weights was implemented.

Results:
- Recall improved significantly to 77%
- Accuracy reduced slightly to 78%

This model became much better at detecting churn customers but produced more false positives.


## 3. Decision Tree Classifier

A Decision Tree model was developed to capture more complex relationships between customer behaviors and churn.

Results:
- Accuracy: 94%
- Precision: 88%
- Recall: 67%
- F1-score: 76%

The Decision Tree achieved the best overall balance between prediction accuracy and churn detection capability.


## 4. Tuned Decision Tree

Manual hyperparameter tuning was applied to improve the Decision Tree model.

Parameters adjusted included:
- Maximum tree depth
- Minimum samples split
- Minimum samples leaf

The tuned model produced results similar to the original Decision Tree model, indicating that the original model had already achieved near-optimal performance.


# Evaluation

The models were evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrices

Because customer churn prediction is a business-critical classification problem, recall was particularly important since failing to identify churn customers may result in revenue loss.


### Final Model Selection

The original Decision Tree Classifier was selected as the final model because it achieved:
- High overall accuracy
- Strong precision
- Good recall
- Balanced performance across evaluation metrics

The model demonstrated strong practical utility for customer churn prediction.


# Conclusion

This project successfully applied machine learning techniques to predict customer churn for SyriaTel.

The analysis identified important churn indicators such as:
- Customer service calls
- International plan subscriptions
- Customer usage behavior

Among the evaluated models, the Decision Tree Classifier achieved the strongest overall performance and was selected as the final predictive model.

The findings from this project demonstrate how predictive analytics can support customer retention strategies and improve business decision-making within the telecommunications industry.


# Recommendations

Based on the analysis and modeling results, the following recommendations are proposed:

1. Improve customer service quality to reduce dissatisfaction and churn risk.

2. Monitor customers subscribed to international plans more closely.

3. Implement targeted retention campaigns for high-risk customers.

4. Integrate predictive analytics into customer relationship management systems.

5. Continuously retrain the model using updated customer data.
