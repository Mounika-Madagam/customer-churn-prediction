\# Customer Churn Prediction (Telecom)



End-to-end machine learning project that predicts subscriber churn for a telecom customer base, identifies key churn drivers, and translates findings into actionable retention strategies.



\## Business Context



Customer churn is a critical metric for subscription businesses. Acquiring a new customer typically costs 5-7x more than retaining one. This project builds a predictive model to identify at-risk customers before they cancel, enabling proactive retention campaigns and targeted winback offers.



\## Dataset



\- \*\*Source:\*\* IBM Telco Customer Churn (via Kaggle)

\- \*\*Records:\*\* 7,043 customers

\- \*\*Features:\*\* 20 (demographics, services, contract info, charges)

\- \*\*Target:\*\* Churn (Yes/No)

\- \*\*Class Distribution:\*\* 26.5% churn rate (imbalanced)



\## Approach



1\. \*\*Data Cleaning\*\* — Converted TotalCharges from string to numeric, handled 11 missing values with median imputation, dropped customerID

2\. \*\*Exploratory Data Analysis (EDA)\*\* — Visualized churn patterns by contract type, tenure, and monthly charges

3\. \*\*Feature Engineering\*\* — Created tenure buckets (New / Early / Established / Loyal), one-hot encoded all categorical variables

4\. \*\*Model Training \& Comparison\*\* — Trained Logistic Regression, Random Forest, and XGBoost models

5\. \*\*Hyperparameter Tuning\*\* — Used GridSearchCV with 5-fold cross-validation on XGBoost across 12 parameter combinations

6\. \*\*Evaluation\*\* — ROC-AUC, accuracy, precision, recall, confusion matrix

7\. \*\*Feature Importance Analysis\*\* — Identified top churn drivers for business interpretation



\## Results



| Model | Accuracy | ROC-AUC |

|-------|----------|---------|

| Logistic Regression | 0.798 | 0.842 |

| Random Forest | TBD | TBD |

| \*\*XGBoost (tuned)\*\* | \*\*0.803\*\* | \*\*0.846\*\* |



\*\*Best XGBoost Parameters:\*\*

\- learning\_rate: 0.1

\- max\_depth: 3

\- n\_estimators: 100



\## Visualizations



\### Top 10 Features Driving Churn

!\[Feature Importance](images/feature\_importance.png)



\### Confusion Matrix (XGBoost)

!\[Confusion Matrix](images/confusion\_matrix.png)



\### Churn by Contract Type

!\[Churn by Contract](images/churn\_by\_contract.png)



\## Key Insights



\- \*\*Month-to-month contracts\*\* drive the highest churn — customers on these plans cancel significantly more often than those on 1-year or 2-year contracts

\- \*\*Tenure\*\* is a strong predictor — new customers in their first 12 months are at highest risk

\- \*\*Higher monthly charges\*\* correlate with higher churn rates

\- \*\*Fiber optic\*\* customers churn at a higher rate than DSL — suggests potential service quality or pricing issues

\- \*\*Customers without add-on services\*\* (online security, tech support) churn more frequently



\## Business Recommendations



1\. \*\*Incentivize annual contracts\*\* — Offer discounts to convert month-to-month customers to 1-year or 2-year plans

2\. \*\*Strengthen new customer onboarding\*\* — Build a structured 12-month onboarding journey to reduce early churn

3\. \*\*Audit fiber optic service\*\* — Investigate service quality and pricing competitiveness

4\. \*\*Promote add-on services\*\* — Bundle online security and tech support to increase retention and value perception



\## Tech Stack



\- \*\*Python 3.11\*\*

\- \*\*pandas, NumPy\*\* — Data manipulation

\- \*\*scikit-learn\*\* — ML pipeline, model training, evaluation, GridSearchCV

\- \*\*XGBoost\*\* — Gradient boosting classifier

\- \*\*matplotlib, seaborn\*\* — Visualization



\## How to Run



