# AWS-DataPipeline-CloudTech
💼 MSBA Financial Group: Bankruptcy Prediction on AWS Cloud
This project showcases an end-to-end cloud-based data analytics and machine learning pipeline built to predict bankruptcy risk for companies. The pipeline leverages Amazon Web Services (AWS) to collect, transform, store, and analyze financial data at scale, ultimately generating actionable insights on which companies to invest in or avoid.


---

## 🚀 Project Overview

The **MSBA Financial Group Cloud Environment** is designed to help analysts and decision-makers evaluate the financial health of various companies using historical and real-time data. Through a fully automated cloud pipeline, this project:

- Collects structured and unstructured company financial data
- Performs data cleaning, transformation, and feature engineering
- Trains a machine learning model to predict bankruptcy likelihood
- Outputs predictions on new, unlabeled company profiles

---

## 🔧 Architecture and Workflow

<img width="905" alt="Screenshot 2025-06-10 at 4 25 17 PM" src="https://github.com/user-attachments/assets/dd1882ce-27da-4c3c-8377-a5661f44094f" />


## AWS Glue Structure
ETL: Extract, Transform, Load
1. Extracting Data from source
2. Transforming Data with necessary changes like joining, change schema
3. Loading into Data Warehouses like Redshift
4. Connects Data source to Datawarehouse
<img width="284" alt="Screenshot 2025-06-10 at 4 28 51 PM" src="https://github.com/user-attachments/assets/af64fa67-63af-4024-878f-bc4992a78392" />

## AWS SageMaker
1. Data from S3 buckets is integrated and loaded into redshift warehouses
2. Has Query editor to transform and load data into tables
<img width="596" alt="image" src="https://github.com/user-attachments/assets/694831be-2798-44e5-a055-0b4da7589d9b" />

## Finding 1
Correlation Between Financial Ratios:
There is a strong correlation between the following two financial metrics:
1. Liability_to_Equity
2. Debt_ratio_percentage

### What This Means:
These two features are closely related in the dataset. A higher liability-to-equity ratio often leads to a higher debt ratio percentage.
This correlation is important because it may influence the behavior of the machine learning model. Highly correlated features can sometimes lead to redundancy, and in some cases, model overfitting.
### Actionable Insight:
During feature engineering, you might consider dimensionality reduction (like PCA) or removing one of the two features if they are too redundant — unless they both contribute unique information.

<img width="467" alt="image" src="https://github.com/user-attachments/assets/95bf7a83-92d1-408c-aec5-649fd013a4ce" />
<img width="440" alt="image" src="https://github.com/user-attachments/assets/4433063e-8ada-4819-afad-56585b156b8f" />

## Finding 2
The feature Persistant_eps (Persistent Earnings Per Share) had the highest impact on the machine learning model, contributing 20.89% to the training process.
### What This Means:
Persistant_eps is the most influential predictor in determining whether a company is likely to go bankrupt or not.
High impact indicates that the model relies heavily on this variable when making predictions, suggesting it’s a strong indicator of financial health.
### Actionable Insight:
This feature should be carefully monitored and validated during data preparation to ensure accuracy.
In a real-world deployment, fluctuations in Persistant_eps should trigger alerts for financial analysts reviewing company risk profiles.
<img width="596" alt="image" src="https://github.com/user-attachments/assets/0135bc66-b1b5-49b0-96a0-3d76082636b1" />

## 📈 Prediction Results
### ✅ Companies to Add to Portfolio:
Ninetech – 99.5% confidence

Rogers and Sons – 99.3%

Pharmasolve – 98.6%

Hallandall ag. – 98.6%

Songster INC. – 97.2%

### ❌ Companies to Avoid:
Western Corp. – 98.8% likely bankrupt

Design Solutions – 87%

Innocore – 74.9%

<img width="792" alt="image" src="https://github.com/user-attachments/assets/be894f4e-75b0-404d-8232-009369e1ab94" />











