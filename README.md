# Customer-Churn-Prediction-for-SyriaTel
## Overview
This project focuses on predicting customer churn for SyriaTel, a telecommunications company. Churn happens when customers stop using the service, leading to significant revenue loss. The main objective was to develop a classification model that identifies customers likely to churn so the company can take proactive retention actions.

## Business and Data Understanding
The primary stakeholders are SyriaTel’s Marketing and Customer Retention teams. These teams need reliable insights to target high-risk customers with interventions such as special offers, improved support, or service adjustments.
The dataset used contains records of 3,333 customers. It includes features such as account length, total day/evening/night/international minutes and charges, international plan status, voice mail plan status, number of customer service calls, and the target variable (churn).
Exploratory analysis revealed a class imbalance issue: only 14.5% of customers (483 out of 3,333) churned, while 85.5% stayed. Because failing to identify churners has direct business costs, recall was chosen as the main evaluation metric.

## Modeling
A classification approach was used to predict whether a customer will churn or not. This allows the business to move from reactive to proactive customer management.
Three models were developed and compared:
1. Logistic Regression (baseline)
2. Logistic Regression with class weighting (balanced)
3. Decision Tree
The process started with a standard Logistic Regression model. After observing low recall on the churn class, a balanced version was tested to better handle the imbalance. Finally, a Decision Tree model was implemented and tuned for improved performance.

## Evaluation
Model performance was assessed using accuracy, precision, recall, and confusion matrices.
The baseline Logistic Regression achieved 86% accuracy but only 25% recall on churners. The balanced Logistic Regression improved recall to 74% but suffered from low precision.
After testing, the tuned Decision Tree was selected as the final model. It delivered:
1. Overall accuracy of 92%
2. Churn recall of 65%
3. Precision of 76% for the churn class
This model provided the best balance between identifying actual churners and minimizing false positives. Key patterns identified include high number of customer service calls, presence of international plan, and absence of voice mail plan as strong indicators of churn risk.

##Conclusion
The tuned Decision Tree model successfully predicts customer churn and offers actionable insights for SyriaTel. By implementing this tool, the company can identify at-risk customers early, reduce churn rates, and improve customer retention efforts in a cost-effective way.
Future work includes deploying the model for regular monthly use and integrating predictions with targeted retention strategies.
