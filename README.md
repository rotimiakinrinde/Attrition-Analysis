# Attrition-Analysis

### Business Overview

Global Talent Solutions (GTS) is a multinational company specialising in providing comprehensive HR solutions, including talent acquisition, employee training, and workforce analytics. With over 10,000 employees spread across 25 countries, GTS serves a diverse clientele ranging from Fortune 500 companies to small and medium enterprises. GTS prides itself on fostering workplace innovation and leveraging data-driven insights to support its clients' HR strategies.

### Problem Statement

GTS has noticed an alarming trend of employee attrition within its own workforce. Over the past year, the company recorded a 20% attrition rate, significantly higher than the industry average of 12%. High employee attrition disrupts operations, increases recruitment costs, and negatively impacts client satisfaction.
GTS wants to identify factors influencing employee attrition and predict which employees are most likely to leave. This will enable the HR team to implement targeted retention strategies.

### Project Rationale

**Reduce Costs:** Minimize the expenses related to hiring and onboarding replacements.

**Improve Workforce Stability:** Retain experienced employees who are critical to client success.

**Enhance Client Satisfaction:** Ensure continuity in service delivery.

**Support Data-Driven Decisions:** Empower the HR team with actionable insights to improve workplace policies.

### Data Preprocessing & Modeling Pipeline

The preprocessing techniques used in the employee attrition analysis were carefully selected to address data quality issues and enhance model performance. 

### Data Preparation

**Missing Values:**

The dataset had missing values in critical features: Age (9.98%), Monthly Income (10.04%), and Job Satisfaction (9.91%). Handled missing values using: Median Imputation: For numerical values like Age. Mode Imputation: For categorical values like Job Satisfaction.

**Removing Duplicates:**

The presence of 408 duplicate rows could distort insights and model learning. Duplicate rows were identified and dropped to ensure the dataset only contained unique records. this is to enhanced data quality and prevent redundancy, which could negatively affect the model’s generalisation.

**Outlier Treatment:**

Outliers were present in Age, Monthly Income, and Years at Company, potentially skewing the model. Interquartile Range (IQR) Method: Outliers were detected and adjusted to bring extreme values within a reasonable range. This is to improved the stability of machine learning algorithms, especially those sensitive to feature scaling.

**Model Performance Comparison**

**A. Logistic Regression Model**

Training Data Performance:
Accuracy: 56%
Precision: 0.56
Recall: 0.56
F1 Score: 0.56
|                   Metric            	|             Value             |
| ------------------------------------- | ----------------------------- |
|              **Precision**            |	            0.56              |
|              **Recall**               |             0.56              |
|              **F1 Score**             |             0.56              |

**Testing Data Performance:**

Accuracy: 56%, Confusion Matrix:, True Positives (1,1): 704, True Negatives (0,0): 620

False Positives/Negatives: Higher error rate in misclassifying attrition cases. The low accuracy, precision, recall, and F1 score indicate underfitting.

**B. Random Forest Classifier**

**Training Data Performance:**

Accuracy: 100%, Precision, Recall, F1 Score: All metrics showed perfect scores, indicating that the model predicted all training data points correctly.

**Testing Data Performance:**

Accuracy: 87%

|                   Metric            	|             Value             |
| ------------------------------------- | ----------------------------- |
|              **Precision**            |	            0.87              |
|              **Recall**               |             0.87              |
|              **F1 Score**             |             0.87              |


**Confusion Matrix:**
True Positives (1,1): 925
True Negatives (0,0): 1036
False Positives: 156
False Negatives: 266

|                 Model                	|         True Positives        |      True Negatives      |     False Positives    |    False Negatives    |
| ------------------------------------- | ----------------------------- | ------------------------ | ---------------------- | --------------------- |
|        **Logistic Regression**        |	             704              |           620            |          High          |         High          |
|            **Random Forest**          |              925              |           1036           |          156           |         266           |





