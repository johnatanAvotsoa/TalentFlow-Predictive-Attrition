# TalentFlow-Predictive-Attrition
Employee Turnover Prediction & HR Analytics

This project provides an end-to-end data science solution to identify at-risk employees. By analyzing historical HR data, we built a machine learning pipeline to predict the likelihood of an employee leaving the company, allowing for proactive retention strategies.
📂 Project Structure
Plaintext

project/
├── dataset/
│   ├── raw_hr_data.csv          # Original untouched data
│   └── cleaned_hr_data.csv      # Data after duplicate removal and processing
└── notebooks/
    ├── data_cleaning.ipynb      # Handling duplicates and data integrity
    ├── hr_data_analysis.ipynb   # EDA, turnover visualizations, and insights
    └── training.ipynb           # ML Pipeline, model training, and evaluation

🛠️ The Workflow
1. Data Cleaning (data_cleaning.ipynb)

The primary focus was ensuring data quality.

    Identified and removed approximately 3,800 duplicate records to prevent model bias.

    Verified data types and checked for missing values.

2. Exploratory Data Analysis (hr_data_analysis.ipynb)

Explored the drivers of turnover using visual analytics.

    Departmental Analysis: Visualized turnover volume vs. turnover rate per department.

    Satisfaction Drivers: Investigated the correlation between project workload, monthly hours, and employee attrition.

3. Machine Learning Pipeline (training.ipynb)

To ensure a robust and reproducible model, a Scikit-Learn Preprocessing Pipeline was used:

    Numerical Features: Scaled using StandardScaler to normalize features like average_monthly_hours.

    Categorical Features: Processed via OneHotEncoder(handle_unknown='ignore') for departments and salary levels.

    Class Imbalance: Handled the 5:1 imbalance (Stayed vs. Left) using class_weight='balanced' within the model.

📊 Model Performance

The current model (Logistic Regression) prioritizes Recall, ensuring we capture as many "Leavers" as possible.
Metric (Class: Left)	Score
Recall	84%
Precision	43%
F1-Score	57%

    Note: The high recall indicates the model is highly effective at identifying at-risk employees, though it produces some false positives (employees flagged as "leaving" who may actually stay).

🚀 How to Run

    Ensure you have the following libraries installed:
    Bash

pip install pandas matplotlib seaborn scikit-learn

Navigate to the notebooks/ folder.

Run the notebooks in the following order:

    data_cleaning.ipynb

    hr_data_analysis.ipynb

    training.ipynb
