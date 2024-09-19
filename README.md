# Customer-Churn-Prediction-and-Analysis-Using-Interpretable-ML

### Project Overview

This project focuses on analyzing customer churn for a telecommunications company using data from [Kaggle's Telco Customer Churn dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/code). **Customer churn** refers to when customers leave the company for a competitor. The goal of this project is to **understand the factors** contributing to customer churn and to develop **interpretable models** that can predict which customers are most at risk of churning. The models used will vary in complexity and will include linear regression, logistic regression, and a generalized additive model (GAM).

#### Key Tasks

1. **Exploratory Data Analysis (EDA)**:
   - Perform EDA to explore relationships between customer features and churn. Assumptions for linear regression, logistic regression, and GAM will be checked using visualizations and statistical methods.
   - Understand the distribution of features like tenure, monthly charges, and contract types to determine their impact on churn.

2. **Modeling Approaches**:
   - **Linear Regression**: Treat the churn variable as continuous (0 = staying, 1 = churning) and build a linear regression model. While linear regression is interpretable, it may not fully capture the complexity of churn, as this model assumes a linear relationship.
   - **Logistic Regression**: Build a binary classification model (0 = staying, 1 = churning) using logistic regression to predict the probability of churn. This method models the log-odds of churn and offers a straightforward way to interpret feature contributions.
   - **Generalized Additive Model (GAM)**: Use GAM to account for non-linear relationships between customer features and churn. GAM provides more flexibility by modeling smooth, non-linear effects, offering deeper insights into how customer features interact to predict churn.

3. **Model Comparison and Evaluation**:
   - **Linear Regression**: Low MSE (0.17) indicates that the model makes relatively accurate predictions, but the low R² (0.15) suggests that it explains only 15% of the variance in churn, making it too simplistic.
   - **Logistic Regression (Threshold = 0.4)**: Strong accuracy (82.11%) and AUC-ROC (0.8659) show that the model performs well in discriminating between churners and non-churners. Precision (65.01%) and recall (70.24%) indicate a moderate balance between capturing churners and avoiding false positives.
   - **Generalized Additive Model (GAM, Threshold = 0.1)**: Slightly lower accuracy (80.84%) but captures complex, non-linear relationships between features and churn. AUC-ROC (0.8602) remains strong, and precision (64.11%) and recall (62.73%) demonstrate a balanced model, though it sacrifices some precision for improved recall.

#### Key Results and Recommendations

- **Linear Regression**: Although the model minimizes prediction error (low MSE), it fails to explain the variance in churn (low R²) and is not suitable for predicting binary outcomes like churn. **Not recommended** for the company’s churn prediction task.
  
- **Logistic Regression (Threshold = 0.4)**: The model strikes a good balance between interpretability and predictive performance. With strong accuracy (82.11%) and discriminatory ability (AUC-ROC = 0.8659), it is effective at predicting churn. The high recall (70.24%) ensures that most churners are captured, though the company should be prepared to handle false positives. **Recommended** for operational use when both interpretability and strong prediction are required.

- **Generalized Additive Model (GAM, Threshold = 0.1)**: GAM captures **non-linear relationships** between features and churn, providing valuable insights into customer behavior. With a high AUC-ROC (0.8602) and flexible modeling of features, GAM is a strong tool for **understanding churn drivers**. However, the slightly lower precision and recall make it less ideal for immediate operational use. **Recommended** for strategic insights and deeper analysis into the factors driving churn, complementing the logistic regression model.

#### Recommendations

- **Primary Model**: Use **logistic regression** for churn prediction due to its strong accuracy, interpretability, and balance between precision and recall.
- **Strategic Insights**: Leverage the **Generalized Additive Model (GAM)** to gain insights into non-linear feature effects and interactions that contribute to customer churn. GAM's ability to capture complex patterns makes it a valuable tool for understanding churn drivers, though it may require more computational effort and fine-tuning.

- Both models complement each other well. Logistic regression can serve as the primary operational model for predicting churn, while GAM can provide strategic insights into customer behavior for targeted retention efforts.
