# LoanDefault

# Project Overview

The Loan Default Prediction project addresses the critical business problem of loan defaults. By analyzing historical loan and customer data, we aim to predict which applicants are at risk of defaulting. This model helps financial institutions minimize non-performing loans (NPLs), optimize loan approvals, and increase profitability by making data-driven decisions.

# Objective

Business Problem: High default rates lead to significant financial losses. Predicting risky customers before issuing loans is vital for reducing bad debt.

Solution: A machine learning classification model that predicts whether an applicant will default on their loan.

Outcome: A deployable predictive system that helps lenders make informed decisions and minimize risk.

# Dataset

Source: CSV format.

Features:

Personal demographics (e.g., Age, Employment Type, Marital Status)

Financial indicators (e.g., Annual Income, Loan Amount, Credit Score)

Behavioral features (e.g., Number of Dependents, Education Level)

Target variable: Default (Binary: 1 = Default, 0 = No Default)

# Project Structure

# Methodology

1. Exploratory Data Analysis (EDA)

A comprehensive EDA was conducted to understand data distribution, detect missing values, and identify correlations. Key findings include:

Imbalanced target variable: Approximately 18% of applicants defaulted.

Strong predictors:

Lower Credit Score correlates with higher default probability.

Higher Loan Amount relative to income increases default risk.

Employment Type and Education Level show varying risk patterns.

EDA Plots:

Numeric Features Distribution:


Categorical Features Distribution:


Correlation Matrix:


2. Why Decision Tree Classifier?

Model Selection Rationale:

Interpretability: Decision Trees are easy to visualize and explain to non-technical stakeholders.

Speed: Fast to train and predict, making them ideal for initial models and quick deployment.

Non-linear relationships: Capable of capturing complex interactions without requiring feature scaling.

Feature Importance: Provides insight into which variables drive predictions.

3. Data Preprocessing

Dropped rows with missing values (approximately 2% of total records).

Removed duplicate records (about 1% of dataset).

Encoded categorical variables using LabelEncoder.

Train-test split: 80% training, 20% testing.

4. Model Building

Algorithm: DecisionTreeClassifier

Hyperparameter Tuning:

max_depth: Optimal at 5-10 to prevent overfitting.

min_samples_split: Balanced between 5 and 10.

criterion: Both gini and entropy tested.

Search Strategy: RandomizedSearchCV with 10 iterations and 3-fold cross-validation for efficiency.

5. Model Evaluation

Accuracy: ~87%

Precision (Defaulters): 0.76

Recall (Defaulters): 0.82

F1-Score (Defaulters): 0.79

Confusion Matrix:



True Positives (Correct Default Prediction): 164

False Positives (Incorrect Default Prediction): 34

True Negatives (Correct Non-Default Prediction): 580

False Negatives (Missed Default Prediction): 22

6. Model Saving

Saved the trained model as best_loan_default_model.pkl for later use.

Loading the model for inference can be done using joblib.load().

# How to Run

Clone the repository:

Install dependencies:

Execute the Python script:

Outputs:

Model evaluation printed in terminal

Plots saved in plots/ directory

Trained model saved as best_loan_default_model.pkl

# Business Insights & Recommendations

# Insights

Credit Score is the strongest predictor of loan default.

Applicants with unstable employment types (contract/temporary) have higher default rates.

Loan amounts exceeding 35% of applicant's annual income significantly increase risk.

# Recommendations

Risk-Based Loan Approval:

Prioritize applicants with higher credit scores and stable employment.

Apply stricter lending terms to high-risk profiles.

Tailored Loan Products:

Offer secured loans or require co-signers for applicants flagged as medium-risk.

Continuous Model Update:

Regularly retrain the model on new applicant data to maintain accuracy.

# Future Enhancements

Explore ensemble methods (Random Forest, XGBoost) for improved accuracy.

Integrate external credit bureau data for enriched feature sets.

Deploy as a REST API using Flask or FastAPI.

Develop a dashboard for real-time monitoring and decision support.

# Author

Chazin Brahma
