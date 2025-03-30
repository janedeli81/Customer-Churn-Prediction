Predicting customer churn using Gradient Boosting and hyperparameter tuning with Optuna.
This project focuses on predicting customer churn – identifying which customers are likely to leave a service provider. Customer churn prediction is a critical task in various industries, including telecommunications, banking, and subscription-based services, helping businesses proactively retain high-risk customers.

Objective
The goal is to develop a highly efficient machine learning model that can process a large number of features (both numerical and categorical) while addressing class imbalance. The project demonstrates data preprocessing, feature engineering, model training, and hyperparameter optimization.
Dataset
Training Data: Contains customer features and a binary target variable (y), where:
y = 1 → Customer churned (left the service).
y = 0 → Customer remained.
Test Data: Contains customer features without target labels.
Dataset Challenges:
High dimensionality (many numerical & categorical features).
Imbalanced classes (fewer churned customers compared to retained ones).
Missing values in both numerical and categorical fields.

Methodology
Data Preprocessing:
Numerical Features: Missing values filled using the median, then standardized using StandardScaler.
Categorical Features: Missing values filled using the most frequent value, then encoded using OneHotEncoder.
ColumnTransformer was used to combine preprocessing steps.
Handling Class Imbalance:
SMOTE (Synthetic Minority Over-sampling Technique) was applied to generate synthetic samples for the minority class.

Model Training & Optimization:
Gradient Boosting Classifier was selected as the main model.

Hyperparameter tuning with Optuna was performed, optimizing:
Number of trees (n_estimators).
Learning rate (learning_rate).
Maximum depth (max_depth).
Minimum samples required to split (min_samples_split).
Minimum samples required in a leaf (min_samples_leaf).
Subsample fraction (subsample).
The best hyperparameters found during tuning:
{
    'n_estimators': 250,
    'learning_rate': 0.0435,
    'max_depth': 9,
    'min_samples_split': 9,
    'min_samples_leaf': 17,
    'subsample': 0.7348
}
Model Evaluation:
Balanced Accuracy Score to account for class imbalance.
F1 Score, Precision, and Recall to measure performance, especially focusing on correctly identifying churned customers.
Results
Before tuning:
F1 Score: 0.7206
Precision:0.7639
Recall: 0.6820
Balanced Accuracy: 0.8252
