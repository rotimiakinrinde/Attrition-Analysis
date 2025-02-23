# Attrition-Analysis

### Business Overview

Global Talent Solutions (GTS) is a multinational company specialising in providing comprehensive HR solutions, including talent acquisition, employee training, and workforce analytics. With over 10,000 employees spread across 25 countries, GTS serves a diverse clientele ranging from Fortune 500 companies to small and medium enterprises. GTS prides itself on fostering workplace innovation and leveraging data-driven insights to support its clients' HR strategies.

### Problem Statement

Employee attrition can significantly impact organizational performance, leading to increased hiring and training costs, reduced productivity, and potential disruptions to business operations. By understanding the patterns and predictors of attrition, GTS can implement targeted strategies to retain top talent and enhance workplace satisfaction.

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
![Missing Values bar](https://github.com/user-attachments/assets/a1acf096-19a4-4cd5-af72-d27b073f9cc3)
![Fillin in missing values](https://github.com/user-attachments/assets/76e9953b-c710-487f-b5d0-564f3b57d983)

**Removing Duplicates:**

The presence of 408 duplicate rows could distort insights and model learning. Duplicate rows were identified and dropped to ensure the dataset only contained unique records. this is to enhanced data quality and prevent redundancy, which could negatively affect the model’s generalisation.
![Remove duplicates](https://github.com/user-attachments/assets/e6c84b18-4eb2-4e5a-bc83-0954db05439f)

**Outlier Treatment:**

Outliers were present in Age, Monthly Income, and Years at Company, potentially skewing the model. Interquartile Range (IQR) Method: Outliers were detected and adjusted to bring extreme values within a reasonable range. This is to improved the stability of machine learning algorithms, especially those sensitive to feature scaling.
![Outliers Boxplot](https://github.com/user-attachments/assets/c87f58a3-f6d0-4776-957a-ea7cd6629d82)
![IQR use](https://github.com/user-attachments/assets/8f8a73f3-1a3a-4e45-9686-e8e77b643656)


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

False Positives/Negatives reflects a higher error rate in misclassifying attrition cases. The low accuracy, precision, recall, and F1 score indicate underfitting.

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

![Model evaluation](https://github.com/user-attachments/assets/37164979-45e7-45af-aeaa-99318cf34193)

**Confusion Matrix:**

|                 Model                	|         True Positives        |      True Negatives      |     False Positives    |    False Negatives    |
| ------------------------------------- | ----------------------------- | ------------------------ | ---------------------- | --------------------- |
|        **Logistic Regression**        |	             704              |           620            |          High          |         High          |
|            **Random Forest**          |              925              |           1036           |          156           |         266           |





