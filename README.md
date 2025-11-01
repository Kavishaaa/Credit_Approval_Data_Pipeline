### Credit_Approval_Data_Pipeline

An end-to-end credit approval data analysis and machine learning pipeline built using Python, SQL, and Scikit-learn.  
This project identifies high-risk credit applicants based on payment history, income levels, and credit behavior.


### Overview
- Cleaned and merged Kaggle credit datasets (`application_record.csv`, `credit_record.csv`)
- Created an ETL pipeline using **Pandas** and stored results in an **SQLite** database
- Performed **SQL-based analytics** to identify trends in income, credit status, and risk
- Built a **Logistic Regression** model to classify high-risk applicants
- Added **5% label noise** to simulate real-world uncertainty
- Visualized **feature importance** to explain model predictions


### Tech Stack
**Python**, **Pandas**, **NumPy**, **SQLite**, **SQL**, **Scikit-learn**, **Matplotlib**, **Google Colab**


### Key Results

Accuracy : 0.950 (Model predicts correctly 95% of the time overall.)
Precision: 0.962 (When it predicts high-risk, it’s almost always correct.)
Recall   : 0.028 (But it’s missing many of the true high-risk customers (low sensitivity).)
F1 Score : 0.054 (Combined metric shows imbalance — model favors non-risky class.)

### Model’s Feature Importance
| Feature              | Coefficient   | Interpretation                                                                                                            |
| -------------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **amt_income_total** | 2.39e-08      | Negligible positive effect — income has almost no influence here (might need scaling or log transform for better impact). |
| **total_months**     | -1.15e-03     | Longer credit history slightly *reduces* risk.                                                                            |
| **avg_status**       | +9.50e-02     | Poor average credit status (higher numeric values) *increases* risk moderately.                                           |
| **late_payments**    | **+7.35e-01** | Strongest indicator — more late payments = significantly higher risk.                                                     |


### Dataset
[Kaggle - Credit Card Approval Prediction](https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction)


### Insights
- Late payments and poor credit history are the most influential risk indicators.  
- Higher income and longer credit history correlate with safer credit behavior.
