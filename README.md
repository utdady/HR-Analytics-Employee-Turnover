# HR Analytics — Employee Turnover Prediction (Salifort Motors)
## Overview

This project analyzes HR data from Salifort Motors to understand the key drivers of employee turnover and build predictive models that estimate the likelihood an employee will leave.

Employee turnover is expensive — recruiting, onboarding, and lost productivity significantly impact organizational performance. By identifying at-risk employees early, HR can proactively intervene to improve retention and job satisfaction.

This notebook includes:

- Exploratory Data Analysis (EDA)
- Logistic Regression, Decision Tree, Random Forest, and XGBoost models
- Feature importance analysis
- Model comparison & ROC curves
- Actionable business insights for HR stakeholders

## Dataset Summary

The dataset contains 14,999 rows and 10 features, including:

- Satisfaction level
- Performance evaluation
- Number of projects
- Average monthly hours
- Tenure
- Work accident
- Promotion history
- Department
- Salary tier
- Target variable: left (1 = employee left, 0 = stayed)

## Exploratory Data Analysis (Key Insights)
### Satisfaction Level Distribution

Employees who leave have significantly lower satisfaction, clustering between 0.1–0.4, while retained employees are typically above 0.6.

![Satisfaction Distribution](images/satisfaction_level_distribution.png)

### Tenure vs Employee Departure

Turnover peaks at 2–4 years, indicating a critical window where intervention may prevent churn.

### Department vs Employee Departure

Sales, Technical, and Support show the highest total turnover. Management employees have the lowest turnover rate.

### Workload Effects — Average Monthly Hours

Employees who leave fall into two risk groups:

- Underworked (low monthly hours → disengaged)
- Overworked (240+ hours → burnout)

### Number of Projects vs Employee Departure

Extremes contribute to risk:

- Too few projects → boredom
- Too many projects → overload

### Modeling & Performance Evaluation

We trained four models:

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.83 | 0.45 | 0.21 | 0.29 | 0.82 |
| Decision Tree | 0.98 | 0.96 | 0.91 | 0.94 | 0.98 |
| Random Forest | 0.98 | 0.99 | 0.91 | 0.95 | 0.98 |
| XGBoost | 0.98 | 0.97 | 0.91 | 0.94 | 0.99 |

📈 ROC Curve Comparison

Random Forest and XGBoost deliver the strongest predictive power.

## Key Predictors (Feature Importance)

Across tree-based models, the most influential features were:

- Satisfaction Level — strongest predictor
- Number of Projects
- Average Monthly Hours
- Tenure
- Last Evaluation Score
Salary, promotions, and department have weaker predictive power but still contribute.

## Actionable Recommendations for HR
### Improve employee satisfaction

- Conduct anonymous pulse surveys
- Implement regular check-ins
- Provide recognition programs

### Address workload imbalance

- Detect employees with extreme hours or project counts
- Redistribute workload to avoid burnout

### Target interventions at 2–4 year mark

- Provide growth pathways
- Offer mentorship or rotational programs

### Increase promotion opportunities

- Promotions are rare but strongly associated with lower turnover
- Establish clear and fair advancement criteria

### Focus on high-risk departments (Sales, Technical, Support)

- Perform root-cause analysis for department-specific turnover patterns

## Ethical Considerations

- Predictive models must not be used to penalize employees.
- Ensure transparency — predictions should support employees, not punish them.
- Avoid reinforcing biases tied to salary or department.
- Protect employee privacy when storing or sharing model outputs.

## How to Run This Project

Clone the repository:
```bash
git clone https://github.com/utdady/HR-Analytics-Employee-Turnover
cd HR-Analytics-Employee-Turnover
```

Install dependencies:
```bash
pip install -r requirements.txt
```

Open the Jupyter notebook:
```bash
jupyter notebook "Salifort Motors project.ipynb"
```

## Project Structure
```vbnet
HR-Analytics-Employee-Turnover/
│
├── images/                     <- Key EDA and model visualizations
│   ├── satisfaction_level_distribution.png
│   ├── tenure_vs_departure.png
│   ├── department_vs_departure.png
│   ├── avg_monthly_hours_distribution.png
│   ├── projects_vs_departure.png
│   └── roc_comparison.png
│
├── HR_capstone_dataset.csv
├── Salifort Motors project.ipynb
├── best_model.pkl
├── requirements.txt
└── README.md
```
