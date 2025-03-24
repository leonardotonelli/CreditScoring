# Credit Scoring Model for Default Risk Prediction
Project for 30412 - Machine Learning course, at Bocconi University. Contributors: Leonardo Tonelli, Edoardo Putignano, Tommaso Ravasio e Vittoria Fiocchi. 


## Overview
This project focuses on developing a credit scoring model to predict the likelihood of loan default using machine learning techniques. The goal is to help banks assess the risk of issuing loans to new customers by predicting the binary variable `SeriousDlqin2yrs`, which indicates whether an individual has experienced a 90-day delinquency or worse.

## Key Features
- **Dataset**: Contains 11 variables related to customer financial behavior.
- **Target Variable**: `SeriousDlqin2yrs` (binary classification).
- **Class Imbalance**: The dataset is highly imbalanced, with the minority class (default) comprising only 6.7% of the observations.

## Methodology
1. **Data Preprocessing**:
   - Handling missing values (imputation of median values for "Monthly Income" and zeros for "Number of Dependents").
   - Outlier removal (eliminating extreme values above the 0.995 quantile).
   - Feature engineering: Created new features such as `CreditUtilizationRatio`, `Young`, and `LatePaymentsFrequency`.

2. **Exploratory Data Analysis (EDA)**:
   - Univariate and bivariate analysis to understand data distributions and correlations.
   - Correlation matrix to identify relationships between variables.

3. **Modeling**:
   - **Baseline Model**: Logistic Regression (AUC: 0.8077).
   - **Ensemble Methods**: Bagging Decision Tree, Boosted Decision Tree, and Random Forest.
   - **Resampling Techniques**: Random Undersampling (RUS), Random Oversampling (ROS), and SMOTE.
   - **Class Weighting**: Weighted Decision Tree and Weighted Random Forest.
   - **Algorithmic-Level Solutions**: Balanced Random Forest, Easy Ensemble, and Balanced Bagging.

4. **Evaluation Metrics**:
   - **Confusion Matrix**: Visualizes true positives, true negatives, false positives, and false negatives.
   - **Recall**: Measures the model's ability to identify all relevant instances.
   - **F1 Score**: Harmonic mean of precision and recall.
   - **AUC (Area Under the Curve)**: Evaluates the model's discriminative ability across different thresholds.

## Results
- **Best Performing Model**: RUS + Boosted Decision Tree (AUC: 0.8564).
- **Feature Importance**: `RevolvingUtilizationOfUnsecuredLines`, `DebtRatio`, and `NumberOfTimes90DaysLate` were the most significant predictors.
- **Engineered Feature Importance**: `LatePaymentsFrequency` showed high importance in predicting outcomes.

## ROC AUC Curve
![ROC AUC Curve](path_to_ROC_AUC_curve_image.png)  <!-- Replace with actual path to the ROC AUC curve image -->

## Conclusion
The project successfully developed several reliable credit scoring models, with the RUS + Boosted Decision Tree model achieving the highest AUC score. The study highlights the importance of addressing class imbalance and the effectiveness of ensemble methods in improving model performance.

## Limitations
- Limited computational resources restricted the exploration of more complex models like SVM and Neural Networks.
- Shallow hyperparameter tuning due to time constraints.
- Potential bias in the AUC metric due to class imbalance.
