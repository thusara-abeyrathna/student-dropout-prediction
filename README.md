# student-dropout-prediction
Complete machine learning pipeline to predict student dropout vs graduation using a Kaggle dataset.

In the landscape of higher education, student dropout rates present a significant challenge for academic institutions globally. This project addresses this challenge by developing a predictive model to distinguish between students who are likely to drop out and those who will successfully graduate.

The primary objective is to leverage machine learning techniques to build a robust binary classification model that enables educational institutions to provide timely interventions and allocate resources effectively.

Repository Structure
Report.pdf: The full project report detailing methodology, analysis, and conclusions.
Main.py: Python script(s) containing the data processing and modeling code.
images/: Visualizations generated during Exploratory Data Analysis (EDA) and model evaluation.
data/: kaggle dataset and preprocessed dataset.

Dataset
This project utilizes the "Predict students' dropout and academic success" dataset, publicly available from the UCI Machine Learning Repository.
Source: [Kaggle Dataset Link](https://www.kaggle.com/datasets/thedevastator/higher-education-predictors-of-student-retention) 
Attributes: 35 attributes spanning demographic data, socio-economic factors, and academic performance (both pre-higher education and current progress) .
Target Variable: A binary classification of "Dropout" vs. "Graduate" (records with "Enrolled" status were filtered out).

Methodology
The project follows a structured machine learning pipeline:

1. Data Preprocessing
Cleaning: Verified no null values or duplicates.
Filtering: Removed "Enrolled" instances to focus on the binary outcome.
Encoding: Mapped "Dropout" to 0 and "Graduate" to 1.
Balancing: Applied SMOTE (Synthetic Minority Oversampling Technique) to address class imbalance.
Outlier Removal: Used custom ranges for grades (0-20) and Interquartile Range (IQR) for other numeric features.
Scaling: Standardized numeric features using StandardScaler.

2. Model Implementation
Six machine learning algorithms were implemented and compared using scikit-learn:

Logistic Regression
Decision Tree
Random Forest
XGBoost
K-Nearest Neighbors (KNN)
Support Vector Machine (SVM)

Hyperparameter tuning was conducted using GridSearchCV with 5-Fold Cross-Validation.

Results
Best Performing Model: XGBoost.
Key Findings: Academic performance variables, such as second-semester curricular units approved, were found to be highly correlated with graduation success.

Evaluation Metrics: Models were assessed based on Accuracy, F1-Score, and AUC-ROC.

Ethical Considerations
This project emphasizes fairness and bias mitigation:
Potential Bias: Acknowledgement of historical data bias and socio-economic patterns that may disadvantage certain groups.

Mitigation Strategies:
Explainable AI (XAI): Using techniques like SHAP or LIME to make decisions transparent.
Fairness Audits: Evaluating error rates across different demographic subgroups.
Intervention Policy: The model is designed to trigger support mechanisms (counseling, financial aid), not to penalize students.
