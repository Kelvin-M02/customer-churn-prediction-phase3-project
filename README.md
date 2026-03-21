# Customer Churn Prediction Project

## Overview
Customer churn is a major challenge in the telecommunications industry, as losing customers directly impacts revenue and growth. This project aims to predict whether a customer is likely to churn using machine learning techniques, enabling proactive retention strategies.

---

## Business and Data Understanding

### Stakeholder
Telecommunications company management, particularly customer retention and marketing teams.

### Business Problem
The company seeks to identify customers at risk of churning in order to take preventive action and reduce revenue loss.

### Dataset
The dataset contains 3,333 customer records with features including usage patterns, service plans, and customer service interactions. 

The target variable is **churn (binary classification)**.

---

## Data Preparation

- Dropped irrelevant columns such as `phone number`
- Encoded categorical variables into numeric format
- Performed train-test split to evaluate generalization
- Scaled features for logistic regression
- Prevented data leakage by fitting transformations only on training data

---

## Exploratory Data Analysis (EDA)

### 1. Target Variable Distribution - Churn

<img src="images\Target_Variable_Distribution.png" width="600">

![Churn Distribution](images\Target_Variable_Distribution.png)

The dataset shows a class imbalance, with most customers not churning.

### 2. Churn Rate by State
![Churn Rate](images\Churn_Rate_by_State.png)

States in the top such as **NJ, CA, TX, MD, SC, MI, MS, NV, WA, and ME** have the highest proportion of churned customers and are priority for retention action.

### 3. International Plan VS Churn
![International Plan](images\International_Plan_vs_Churn.png)

Customers with an international plan are more likely to churn maybe due to higher costs, dissatisfaction or unmet usage needs.

**Key findings:**

- Customers with **4+ customer service calls** are significantly more likely to churn  
- Customers with an **international plan** show higher churn rates  
- **Higher usage (day minutes/charges)** is associated with increased churn  
- Churn varies across states, suggesting geographic influences  
- Strong correlations exist between minutes and charges  

---

## Modeling

### Baseline Model: Logistic Regression
Below is the evaluation of the baseline logistic model. Our main focus metric will be **recall**, this is in mind with the variable we are trying to predict **'Churn'**.

![Model Evaluation](images\Evaluation_of_Baseline_Logistic_Model.png)

#### Focus on Class 1
- Accuracy: **[0.87]**
- Recall: **[0.23]**
- Precision: **[0.66]**

### Tuned Model: [Tuned Logistic Regression Model] - Focus on Class 1
Below is the evaluation of the Tuned logistic model after **handling class imbalance using SMOTE**.

![Tuned Model Evaluation](images\Evaluation_of_Tuned_Logistic_Model.png)
 
- Accuracy: **[0.75]**
- Recall: **[0.70]**
- Precision: **[0.33]**

The tuned model was selected based on improved recall, ensuring better identification of customers likely to churn.

---

## Evaluation

### Metric Selection: Recall

Recall was prioritized because:

> Failing to identify a customer who will churn results in lost revenue. It is more important to capture as many churners as possible, even if it leads to some false positives.

### Model Performance

- The final model improved recall from **[0.23]** to **[0.70]**
- This indicates a stronger ability to detect churners
- Model performance on test data confirms good generalization

---

## Conclusion and Recommendations

### 1. Improve Customer Service Experience
Customers with frequent service calls are at high risk of churn. Prioritize faster resolution and proactive engagement.

### 2. Re-evaluate International Plans
Higher churn among international plan users suggests pricing or service dissatisfaction. Offer better packages or incentives.

### 3. Retain High-Value Customers
High-usage customers generate more revenue but are at greater risk. Introduce loyalty programs and targeted offers.

### 4. Regional Retention Strategies
States with higher churn rates should be prioritized for investigation and localized interventions.

### 5. Proactive Retention System
Deploy the model to flag high-risk customers and intervene early with personalized strategies.

---

## Next Steps

- Experiment with ensemble models (Random Forest, Gradient Boosting)
- Address class imbalance using resampling techniques (e.g., SMOTE)
- Incorporate more customer behavioral data
- Deploy model for real-time predictions

---

## Author
**[Kelvin Mburu Kamau]**

---

## Acknowledgements
This project was completed as part of a data science learning program focusing on machine learning and predictive analytics.
