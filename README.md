# zillow_logistic_regression
Using a dataset built from Zillow home listings, this project predicts home price based on various features from 600 homes listed on Zillow in Northwest Arkansas. The dataset consists of 300 sold homes and 300 homes still on market.

# Quick Conclusion
Here's a consolidated overview of the key insights from the classification reports for each scaler:
# Unscaled Data:
Moderate overall accuracy (56%).
Imbalance towards Class 1: Higher recall but lower precision, leading to more false positives.
Consider metrics like precision, recall, F1-score for each class for a more balanced view.

# Standard Scaler:
Moderate overall accuracy (65%).
Class 1 has higher recall but lower precision, still indicating false positives.
Class 0 has lower recall but higher precision, suggesting missed true positives.
Analyze data distribution and explore hyperparameter tuning or alternative models.
# MinMaxScaler:
High overall accuracy (96.2%) but potential class imbalance.
Perfect recall for Class 1 suggests overprediction at the cost of Class 0 recall.
Investigate data imbalance, evaluate for specific application context, and consider alternative metrics.
# General Recommendations:
Investigate potential class imbalances and their impact on model performance.
Analyze the trade-off between precision and recall based on your specific application's needs.
Explore data exploration, hyperparameter tuning, alternative models, and additional metrics for improvement.
Remember to interpret results in the context of your problem and the consequences of misclassifications.

# Unscaled Data
Class-Specific Performance:<br>
Class 0:<br>
Precision: 0.65 (65% of predicted class 0 instances were correct.)<br>
Recall: 0.40 (It correctly identified only 40% of actual class 0 instances.)<br>
F1-score: 0.50 (Balanced measure of precision and recall for class 0, indicating moderate performance.)<br>
Support: 107 (There were 107 instances in class 0.)<br>
Class 1:<br>
Precision: 0.52 (52% of predicted class 1 instances were correct.)<br>
Recall: 0.75 (It correctly identified 75% of actual class 1 instances.)<br>
F1-score: 0.61 (Balanced measure of precision and recall for class 1, also indicating moderate performance.)<br>
Support: 91 (There were 91 instances in class 1.)<br>
Overall Performance:<br>
Accuracy: 0.56 (56% of instances were correctly classified overall.)<br>
Macro Average: Averages the metrics across classes, treating them equally.<br>
Weighted Average: Averages the metrics across classes, weighted by their support (number of instances in each class).<br>
Key Insights:<br>
The model's overall performance is moderate, with an accuracy of 56%.<br>
It has a higher recall for class 1 (75%) but lower precision (52%), indicating a tendency to overpredict class 1, leading to false positives.<br>
Class 0 has higher precision (65%) but lower recall (40%), meaning it misses many actual class 0 instances.<br>
The F1-scores (0.50 and 0.61) reflect this imbalance between precision and recall for both classes.<br>
Considerations:<br>
Class Imbalance: Check for significant differences in the number of instances in each class, as it can affect performance.<br>
Specific Needs: Evaluate whether false positives or false negatives are more critical for your application and prioritize metrics accordingly.<br>
Next Steps:<br>
Data Exploration: Analyze the data to understand class imbalances or feature issues.<br>
Model Tuning: Experiment with hyperparameter tuning or feature engineering to improve performance.<br>
Alternative Models: If the current model doesn't meet your needs, consider other classification algorithms.<br>
Additional Recommendations:<br>
Visualize the Data: Plot predictions against actual values to identify patterns or outliers.<br>
Analyze Residuals: Examine the distribution of errors to diagnose potential model issues.<br>
Consider Context: Evaluate the model's performance in light of the specific problem and potential consequences of misclassifications.<br>

# Confusion Matrix
Interpretation:<br>
Overall Accuracy: [(TP + TN) / Total] = [(43 + 68) / 138] = 111 / 138 ≈ 80.4%<br>
True Positives (TP): 43 instances were correctly classified as belonging to Class 0.<br>
False Positives (FP): 64 instances were incorrectly predicted as belonging to Class 0 (while actually Class 1).<br>
True Negatives (TN): 68 instances were correctly classified as belonging to Class 1.<br>
False Negatives (FN): 23 instances were incorrectly predicted as belonging to Class 1 (while actually Class 0).<br>
# Key Insights:
The model achieves a respectable overall accuracy of 80.4%.<br>
However, there are a significant number of false positives (64), meaning the model tends to misclassify Class 1 instances as Class 0.<br>
This may be a concern if false positives are costly or undesirable in your specific application.<br>
# Further Analysis:<br>
Class Imbalance: Check if the data has significantly more instances in one class than the other. This can impact the model's performance and skew the interpretation of certain metrics.<br>
Precision and Recall: Consider calculating these metrics to understand the trade-off between correctly identifying true positives and avoiding false positives.<br>
F1-Score: This balanced measure of precision and recall can also provide a holistic view of the model's performance for both classes.<br>
Data Exploration: Analyze the features and distribution of data points to identify potential patterns or biases that might contribute to the high False Positive rate.<br>
# Recommendations:<br>
Experiment with hyperparameter tuning to adjust the model's sensitivity towards specific classes.<br>
Explore data balancing techniques if class imbalance is present.<br>
Consider alternative classification algorithms that might be better suited for your specific problem and cost function.<br>
Remember, a good model interpretation goes beyond just accuracy. Analyze the context, explore the metrics beyond a single number, and use the insights to improve your model or mitigate potential risks associated with misclassifications.<br>

<img width="500" alt="image" src="https://github.com/Tannerbrodess/zillow_logistic_regression/assets/159087577/6ba35faa-60aa-4b73-9c2a-0aeacbe74828">


# Standard Scaler 

Here's an interpretation of the classification report:<br>
Class-Specific Performance:<br>
Class 0:<br>
Precision: 0.78 (78% of predicted class 0 instances were correct.)<br>
Recall: 0.49 (It correctly identified 49% of actual class 0 instances.)<br>
F1-score: 0.60 (Balanced measure of precision and recall for class 0.)<br>
Support: 107 (There were 107 instances in class 0.)<br>
Class 1:<br>
Precision: 0.58 (58% of predicted class 1 instances were correct.)<br>
Recall: 0.84 (It correctly identified 84% of actual class 1 instances.)<br>
F1-score: 0.68 (Balanced measure of precision and recall for class 1.)<br>
Support: 91 (There were 91 instances in class 1.)<br>
Overall Performance:<br>
Accuracy: 0.65 (65% of instances were correctly classified overall.)<br>
Macro Average: Averages the metrics across classes, treating them equally (0.68 for precision, 0.66 for recall, 0.64 for F1-score).<br>
Weighted Average: Averages the metrics across classes, weighted by their support (0.69 for precision, 0.65 for recall, 0.64 for F1-score).<br>
Key Insights:<br>
The model performs moderately well, with an overall accuracy of 65%.<br>
It has higher recall for class 1 (meaning it identifies most actual class 1 instances) but lower precision (more false positives for class 1).<br>
It has higher precision for class 0 (fewer false positives for class 0) but lower recall (misses some actual class 0 instances).<br>
The F1-scores balance precision and recall, indicating moderate performance for both classes.<br>
# Considerations:<br>
Class Imbalance: Analyze the data distribution to see if one class is significantly larger than the other, as it can impact model performance.<br>
Specific Needs: Consider the relative importance of precision and recall for your application. If false positives are more costly, focus on improving precision. If false negatives are more costly, focus on improving recall.<br>
# Next Steps:<br>
Data Exploration: Explore the data to understand potential class imbalances or issues with features.<br>
Model Tuning: Experiment with hyperparameter tuning or feature engineering to improve performance.<br>
Alternative Models: If the current model doesn't meet your needs, explore other classification algorithms like decision trees, random forests, or support vector machines.<br>

# Confusion Matrix:<br>

This confusion matrix represents the results of a binary classification model based on the following format:<br>
Predicted True         False
Actual        Positive  Negative
Positive     | TP (52)  | FN (15)
Negative     | FP (55)  | TN (76)

# Interpretation:<br>
Overall Accuracy: [(TP + TN) / Total] = [(52 + 76) / 143] = 59.4%<br>
True Positives (TP): 52 instances were correctly predicted as belonging to the positive class.<br>
False Positives (FP): 55 instances were incorrectly predicted as belonging to the positive class, while they actually belonged to the negative class.<br>
True Negatives (TN): 76 instances were correctly predicted as belonging to the negative class.<br>
False Negatives (FN): 15 instances were incorrectly predicted as belonging to the negative class, while they actually belonged to the positive class.<br>
# Additional Insights:<br>
The model seems biased towards predicting positive cases, resulting in more false positives than false negatives.<br>
Consider the impact of false positives and false negatives in your specific context. Are false positives more acceptable than false negatives, or vice versa?<br>
Explore other metrics like precision, recall, F1-score, and ROC curve to get a more comprehensive understanding of your model's performance.<br>
# Further Analysis:<br>
Analyze the data distribution for both classes. Is there an imbalance or overlap in features that could explain the higher False Positive rate?<br>
Consider overfitting or class imbalance, which can lead to biased predictions.<br>
Try tuning the model hyperparameters or employing appropriate data balancing techniques to improve performance.<br>
Remember, interpreting a confusion matrix depends on your specific problem and the consequences of misclassifications. Use this information to evaluate your model's strengths and weaknesses and explore ways to improve its performance.<br>
Feel free to ask further questions or provide more context about your problem for a more detailed analysis.<br>

<img width="500" alt="image" src="https://github.com/Tannerbrodess/zillow_logistic_regression/assets/159087577/786dfa6e-29d6-49fe-9b09-f351a2e614af">


# MinMaxScaler<br>

Here's a breakdown of the logistic regression results you provided:<br>
Class-Specific Performance:<br>
Class 0:<br>
Precision: 1.00 (All predicted class 0 instances were correct, but it only predicted 13% of actual class 0 instances as such.)<br>
Recall: 0.13 (It correctly identified only 13% of actual class 0 instances.)<br>
F1-score: 0.23 (Balanced measure of precision and recall for class 0, indicating poor performance.)<br>
Support: 107 (There were 107 instances in class 0.)<br>
Class 1:<br>
Precision: 0.49 (51% of predicted class 1 instances were wrong.)<br>
Recall: 1.00 (It correctly identified all actual class 1 instances.)<br><br>
F1-score: 0.66 (Balanced measure of precision and recall for class 1, indicating moderate performance.)<br>
Support: 91 (There were 91 instances in class 1.)<br>
Overall Performance:<br>
Accuracy: 0.53 (53% of instances were correctly classified overall, indicating room for improvement.)<br>
Macro Average: Averages the metrics across classes, treating them equally.<br>
Weighted Average: Averages the metrics across classes, weighted by their support (number of instances in each class).<br>
# Key Insights:<br>
The model has perfect precision for class 0 but very low recall, meaning it identifies very few actual class 0 instances correctly.<br>
It has perfect recall for class 1 but lower precision, indicating it tends to overpredict class 1, leading to false positives.<br>
The overall accuracy of 53% suggests the model's performance is not ideal.<br>
The relatively low F1-scores (0.23 and 0.66) further highlight the imbalance between precision and recall for both classes.<br>
# Considerations:<br>
Class Imbalance: If the dataset has significantly more instances in one class than the other, it can affect these metrics.<br>
Specific Needs: The relative importance of precision and recall depends on your application. If false positives are more costly, focus on improving precision. If false negatives are more costly, focus on improving recall.<br>
# Next Steps:<br>
Explore Data: Analyze the data distribution to understand class imbalances or potential issues with features.<br>
Model Tuning: Experiment with hyperparameter tuning or feature engineering to improve performance.<br>
Consider Alternatives: If logistic regression doesn't meet your needs, explore other classification algorithms like decision trees, random forests, or support vector machines.<br>

# Confusion Matrix<br>

# Interpretation:<br>
Overall Accuracy: (TP + TN) / Total = (14 + 91) / 105 = 101 / 105 ≈ 96.2%<br>
True Positives (TP): 14 instances were correctly classified as belonging to Class 0.<br>
False Positives (FP): 0 instances were incorrectly predicted as belonging to Class 0 (while actually Class 1).<br>
True Negatives (TN): 91 instances were correctly classified as belonging to Class 1.<br>
False Negatives (FN): 0 instances were incorrectly predicted as belonging to Class 1 (while actually Class 0).<br>
# Key Insights:<br>
This model achieves a very high accuracy of 96.2%, suggesting excellent performance overall.<br>
There are no false positives or false negatives, meaning the model perfectly distinguishes between the two classes.<br>
This is an ideal scenario for many classification tasks, especially when misclassifications could have severe consequences.<br>
However, consider these additional points:<br>
Data Imbalance: Since all positive instances are correctly classified, there might be significantly more instances in Class 1 than in Class 0. This could artificially inflate the overall accuracy and mask potential challenges with identifying Class 0 instances.<br>
Domain knowledge: Analyze the context of the problem and the consequences of misclassifications. Even with perfect accuracy, are there potential biases or limitations in the model's performance that need further evaluation?<br>
# Recommendations:<br>
Investigate the data distribution to confirm or reject the possibility of class imbalance.<br>
If class imbalance exists, explore techniques like oversampling the minority class or using class-balanced metrics like F1-score or Matthews correlation coefficient for a more comprehensive evaluation.<br>
Analyze the false negative rate for Class 0 in greater detail, even if it's currently zero, to understand the model's sensitivity in identifying rare or challenging examples.<br>
Remember, even with impressive results, interpreting the context and limitations of the model is crucial to ensure its effectiveness in your specific application.

<img width="500" alt="image" src="https://github.com/Tannerbrodess/zillow_logistic_regression/assets/159087577/2847f2a5-95e6-4443-89e2-bbf1810ece3a">

