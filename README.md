
# Loan Approval Prediction - Kaggle Competition(Oct 2024)






## Problem statement:

The goal is to build a classification model to predict loan_status (whether a loan will default or not) based on applicant demographic details, financial data, and loan-specific features. This model could help financial institutions identify high-risk loans and mitigate potential losses by making more informed lending decisions.


## Data Description

The dataset contains the following features:

- id (int64) – Unique identifier for each record.
- person_age (int64) – Age of the individual.
- person_income (int64) – Annual income of the individual.
- person_home_ownership (object) – Type of home ownership (e.g., "RENT", "OWN").
- person_emp_length (float64) – Length of employment (in years).
- loan_intent (object) – Purpose of the loan (e.g., "EDUCATION", "MEDICAL").
- loan_grade (object) – Grade assigned to the loan (e.g., "A", "B").
- loan_amnt (int64) – Amount of the loan.
- loan_int_rate (float64) – Interest rate of the loan.
- loan_percent_income (float64) – Proportion of income that the loan represents.
- cb_person_default_on_file (object) – Whether the individual has any defaults on file (e.g., "Y" for yes, "N" for no).
- cb_person_cred_hist_length (int64) – Length of the individual's credit history.
- loan_status (int64) – Status of the loan (likely binary: 0 for not defaulted, 1 for defaulted).


## Inference

**Analysis of the Dataset Using the XGBoost Classifier Model:**

* High Accuracy: The XGBoost Classifier model achieved a commendable accuracy of 95.05%, indicating that it correctly classifies approximately 95.05% of the instances in the dataset. This high level of accuracy demonstrates the model’s strong performance in predicting the target classes.

* Balanced F1 Score (Weighted): The weighted F1 score of 94.82% suggests that the model maintains a good balance between precision and recall. This score indicates that the model is effectively capturing both positive and negative instances. The slight difference between the accuracy and F1 score may imply potential class imbalance in the dataset, where one class may have a significantly higher representation than the other. This highlights the importance of investigating class distribution further and possibly applying techniques to handle any imbalances.

* Model Selection: While the XGBoost Classifier shows excellent results, it is essential to compare its performance with other models to ensure it is the best choice for this problem. For instance:

        Tuned XGBoost Classifier: Accuracy – 95.05%, Weighted F1 Score – 94.79%
        Random Forest Classifier: Accuracy – 94.86%, Weighted F1 Score – 94.57%
        K Neighbor Classifier: Accuracy – 92.63%, Weighted F1 Score – 92.05%

* The results indicate that XGBoost and its tuned version are strong candidates, but the Random Forest Classifier also performs competitively. A thorough comparison is essential to confirm the superiority of these models for this specific problem.

* Hyperparameter Tuning: The current results are promising, but the performance of the models could potentially be improved through more refined hyperparameter tuning. Revisiting the GridSearchCV process and exploring a broader range of hyperparameters might lead to enhancements in both accuracy and the weighted F1 score.

* Business Impact: The business implications of the model’s performance are significant for financial institutions seeking to predict loan default status. The relative importance of accuracy and the weighted F1 score hinges on the model's ability to minimize the risks associated with lending. Accurate predictions can help institutions identify high-risk loans, thereby reducing the cost of defaults and enhancing overall portfolio performance. Evaluating the trade-offs between false positives (incorrectly classifying a non-defaulting loan as a default) and false negatives (failing to identify a defaulting loan) is crucial. Understanding these costs will enable organizations to align the model’s predictions with their risk management strategies and business objectives, ultimately leading to more informed lending decisions.

**Conclusion:**
Achieving an accuracy of 95.05% and a weighted F1 score of 94.79% is an impressive outcome for predicting loan default status. These results indicate that the model is effective in distinguishing between high-risk and low-risk loans, which is critical for financial institutions. However, further analysis, including a thorough comparison with other models and a deep dive into the business implications, is essential to ensure that the model meets the specific needs of the lending process. Understanding how the model's predictions align with organizational objectives will provide insights into its practical applicability, enabling informed decision-making in mitigating potential losses and enhancing overall lending strategies.
