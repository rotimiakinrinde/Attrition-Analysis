# Attrition-Analysis

### Business Overview

Global Talent Solutions (GTS) is a multinational company specialising in providing comprehensive HR solutions, including talent acquisition, employee training, and workforce analytics. With over 10,000 employees spread across 25 countries, GTS serves a diverse clientele ranging from Fortune 500 companies to small and medium enterprises. GTS prides itself on fostering workplace innovation and leveraging data-driven insights to support its clients' HR strategies.

### Problem Statement

Employee attrition can significantly impact organisational performance, leading to increased hiring and training costs, reduced productivity, and potential disruptions to business operations. By understanding the patterns and predictors of attrition, GTS can implement targeted strategies to retain top talent and enhance workplace satisfaction.

### Project Rationale

**Reduce Costs:** Minimise the expenses related to hiring and onboarding replacements.

**Improve Workforce Stability:** Retain experienced employees who are critical to client success.

**Enhance Client Satisfaction:** Ensure continuity in service delivery.

**Support Data-Driven Decisions:** Empower the HR team with actionable insights to improve workplace policies.

## Data Preprocessing & Modeling Pipeline

The preprocessing techniques used in the employee attrition analysis were carefully selected to address data quality issues and enhance model performance. 

### Data Preparation

**Missing Values:**

The dataset had missing values in critical features: Age (9.98%), Monthly Income (10.04%), and Job Satisfaction (9.91%). Handled missing values using: Median Imputation: For numerical values like Age. Mode Imputation: For categorical values like Job Satisfaction.
![Missing Values bar](https://github.com/user-attachments/assets/a1acf096-19a4-4cd5-af72-d27b073f9cc3)
![Fillin in missing values](https://github.com/user-attachments/assets/76e9953b-c710-487f-b5d0-564f3b57d983)

**Removing Duplicates:**

The presence of 408 duplicate rows could distort insights and model learning. Duplicate rows were identified and dropped to ensure the dataset only contained unique records. This is to enhance data quality and prevent redundancy, which could negatively affect the model’s generalisation.
![Remove duplicates](https://github.com/user-attachments/assets/e6c84b18-4eb2-4e5a-bc83-0954db05439f)

**Outlier Treatment:**

Outliers were present in Age, Monthly Income, and Years at Company, potentially skewing the model. The Interquartile Range (IQR) Method was used and outliers were detected and adjusted to bring extreme values within a reasonable range. This is to improved the stability of machine learning algorithms, especially those sensitive to feature scaling.
![Outliers Boxplot](https://github.com/user-attachments/assets/c87f58a3-f6d0-4776-957a-ea7cd6629d82)
![IQR use](https://github.com/user-attachments/assets/8f8a73f3-1a3a-4e45-9686-e8e77b643656)

## Modelling

**1.  Logistic Regression Model**

Logistic Regression was selected as a baseline model due to its simplicity and interpretability in binary classification problems. It is particularly useful for estimating the probability of attrition (binary outcome: Yes/No).
The optimal hyperparameters improved the model’s precision and recall, but the accuracy remained at 56%, indicating potential underfitting.

**2.  Random Forest Classifier**

Random Forest was chosen for its ability to handle complex datasets and provide key insights. 

![Model](https://github.com/user-attachments/assets/f4eba769-d9f3-4970-825f-ee8340e47b73)


### Model Performance Comparison

**A. Logistic Regression Model**

**Training Data Performance:**
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

The 87% accuracy on the test data, demonstrats improved generalisation but also highlighting the need for further regularisation or pruning to avoid overfitting.

![Model evaluation](https://github.com/user-attachments/assets/37164979-45e7-45af-aeaa-99318cf34193)

**Confusion Matrix:**

|                 Model                	|         True Positives        |      True Negatives      |     False Positives    |    False Negatives    |
| ------------------------------------- | ----------------------------- | ------------------------ | ---------------------- | --------------------- |
|        **Logistic Regression**        |	             704              |           620            |          High          |         High          |
|            **Random Forest**          |              925              |           1036           |          156           |         266           |

## Key Insights

### A.  Employee Attrition Patterns:

**High Attrition Groups:**

-  Employees with low job satisfaction and poor work-life balance are at a significantly higher risk of attrition.
-  Individuals with lower monthly incomes are more likely to leave the company.

**Demographic Insights:**

-  Younger employees and those with shorter tenures at the company show a higher likelihood of attrition, indicating potential issues with onboarding and integration processes.

**Organizational Factors:**

-  Departments with limited growth opportunities and roles with high workloads contribute to attrition.
-  Overtime workers show higher attrition, suggesting burnout as a critical factor.

###  B.  Model-Driven Insights:

-  Random Forest Classifier outperformed Logistic Regression with an accuracy of 87% on test data, highlighting its strength in identifying complex relationships within the data.
-  The Confusion Matrix of Random Forest demonstrated fewer false positives and negatives, indicating reliable classification of attrition cases.
-  The Feature Importance Analysis (from Random Forest) revealed that Job Satisfaction, Monthly Income, Work-Life Balance, and Age are among the top predictors of attrition.


## Recommendations

-  **Improve Job Satisfaction:** Launch regular surveys and feedback loops to identify pain points.

-  **Enhance Work-Life Balance:** Introduce flexible work policies and monitor overtime practices.

-  **Invest in Training:** Provide development opportunities, mentorship programs, and clear career paths.

-  **Optimise Compensation:** Benchmark against industry standards and adjust salaries accordingly.

-  **Targeted Retention Initiatives:** Develop tailored strategies for high-risk demographics and departments.

-  **Evaluate Impact:** Regularly track attrition rates, employee satisfaction scores, and productivity metrics.

## Conclusion

The employee attrition analysis for GTS reveals critical insights into the drivers of turnover and offers a data-driven roadmap to enhance retention strategies. By prioritising job satisfaction, work-life balance, and targeted development programs, GTS can create a positive work environment, reduce attrition, and achieve long-term organisational success.


