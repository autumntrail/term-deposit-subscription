# Model Card

## Model Description

This model is designed to predict whether a customer will subscribe to a term deposit following a direct marketing campaign. The dataset used is the Bank Marketing dataset from the UCI Machine Learning Repository.

### Input

The dataset consists of 20 attributes, capturing customer demographic information, economic factors, and details of the marketing campaign.

| Attribute | Description |
|-----------|-------------|
| age       | Age of the customer |
| job       | Type of job the customer holds (e.g., admin., blue-collar, technician) |
| marital   | Customer's marital status (single, married, divorced) |
| education | Level of education of the customer |
| default   | Indicates whether the customer has credit in default (yes or no) |
| balance   | The average yearly balance of the customer’s account (in euros) |
| housing   | Indicates whether the customer has a housing loan (yes or no) |
| loan      | Indicates whether the customer has a personal loan (yes or no) |
| contact   | Indicates whether the customer has a personal loan (yes or no) |
| day       | Last contact day of the month |
| month     | Last contact month of the year |
| duration  | Duration of the last call (in seconds) |
| campaign  | Number of contacts performed during this campaign for this client |
| pdays     | Number of days since the client was last contacted from a previous campaign |
| previous  | Number of contacts performed before this campaign |
| poutcome  | Outcome of the previous marketing campaign (e.g., success, failure) |

### Output

The target variable is binary and indicates whether the customer subscribed to a term deposit.

| Target Variable   | Description                                                 |
|-------------------|-------------------------------------------------------------|
| y (susbcription)	 | Whether the client subscribed to a term deposit (yes or no) |


### Model Architecture

We employed XGBoost, a high-performance implementation of gradient-boosted decision trees. This model is particularly suitable for handling tabular data and addressing classification tasks with imbalanced data distributions, such as the Bank Marketing dataset.

The best model parameters identified after hyperparameter tuning using Bayesian Optimisation are:

```
n_estimators=61
max_depth=9
min_child_weight=6
gamma=0.3689
subsample=0.6301
colsample_bytree=0.8449
learning_rate=0.0854
scale_pos_weight=6.856
```

The model was trained using the XGBoost classifier with the objective function set to `binary` for binary classification.

## Performance

We evaluate the performance of our XGBoost classifier using various metrics that offer insight into how well the model handles both majority and minority class predictions. Since the Bank Marketing dataset is imbalanced (with a higher proportion of customers not subscribing to a term deposit), using metrics beyond accuracy is essential to assess the model's true effectiveness. Specifically, the ROC-AUC score is a valuable metric for this kind of imbalanced dataset, as it captures the model's ability to distinguish between the positive and negative classes without being biased by class imbalances.

Below are the results of the XGBoost classifier on the test set, where we aim to predict whether a customer will subscribe to a term deposit:

| Algorithm | ROC-AUC | Accuracy | Precision | Recall | F1 Score
|-----------|-----------|-----------|-----------|-----------|-----------|
| XGBoost | 0.8553 | 0.8656 | 0.9156 | 0.8656 | 0.8813 

### ROC-AUC Score 

Measures the area under the Receiver Operating Characteristic (ROC) curve. It reflects the model's ability to distinguish between the positive (subscribed) and negative (not subscribed) classes across various threshold settings.

The score of 0.8553 indicates that the model has a good ability to distinguish between customers who will subscribe and those who will not, even though the data is imbalanced. This makes it a robust measure for evaluating the model's performance in scenarios where one class is underrepresented.

### Accuracy Score

Measures the ratio of correctly predicted instances (both positive and negative) to the total number of instances. While accuracy is easy to interpret, it can be misleading when the dataset is imbalanced, as it may overestimate performance by favoring the majority class.

The model achieves an accuracy of 86.56%, which is respectable but may not fully capture the performance on the minority class due to the imbalanced nature of the dataset.

### Precision Score

Measures the proportion of correctly predicted positive observations out of all observations predicted as positive. High precision means a low false-positive rate, ensuring that the model accurately identifies subscribers without including too many non-subscribers.

With a precision of 91.56%, the model correctly identifies most of the customers predicted to subscribe, which helps minimize the cost of false positives in marketing campaigns.

### Recall Score

Measures the proportion of actual positive observations (customers who subscribed) that were correctly identified by the model. High recall indicates that the model is sensitive to detecting true positives, though it may lead to more false positives.

A recall of 86.56% suggests that the model is effective at identifying true subscribers, although there is a small percentage that it may miss.

### F1 Score

The harmonic mean of precision and recall, providing a balanced evaluation. It is useful when seeking a trade-off between precision and recall, especially in imbalanced datasets where one metric alone may not fully capture performance.

The F1 score of 88.13% provides a balanced view between precision and recall, ensuring the model performs well on both metrics, particularly important for imbalanced datasets where optimizing one metric at the expense of the other can lead to suboptimal results.

## Limitations

### Class Imbalance

The dataset is imbalanced, with a larger proportion of customers who do not subscribe to a term deposit. This can lead to bias in the model toward predicting the majority class. To mitigate this, we applied the scale_pos_weight parameter in XGBoost, which assigns more weight to the minority class.

### Data Staleness

The dataset contains information from marketing campaigns conducted several years ago. Changes in economic conditions or customer behavior over time may limit the relevance of the model for current campaigns.

### Call Duration

One significant feature is the call duration, which has a strong influence on the prediction outcome. However, this variable is only known after the marketing call ends, reducing its usefulness in real-time prediction scenarios.

## Trade-offs

### Precision vs. Recall

In this model, optimising for one metric (e.g., precision) could lead to reduced performance in another metric (e.g., recall). For example, achieving higher precision means fewer false positives but may miss potential customers (lower recall). The F1 score provides a balanced metric, but adjustments can be made based on the business objective (e.g., maximising customer outreach vs. minimising wasted marketing resources).

### Interpretability vs. Complexity

XGBoost models are more complex and harder to interpret than simpler models like logistic regression, which can make it difficult for stakeholders to understand why certain customers are predicted to subscribe. This lack of transparency may be an issue when explaining the model's decisions. However, this can be addressed by using tools like feature importance to highlight key factors driving predictions. Additionally, techniques such as SHAP (SHapley Additive exPlanations) and LIME (Local Interpretable Model-Agnostic Explanations) can further enhance interpretability, making the model's decisions more transparent and easier to explain to non-technical stakeholders.

## Ethical Considerations

### Bias and Fairness

Ensure that the model is not unintentionally biased against certain demographic groups. Since the dataset includes sensitive attributes like age and education, careful handling is required to avoid discriminatory outcomes.

### Privacy

The model relies on personal data (e.g., age, job, marital status). Proper data governance and privacy measures should be in place to ensure the confidentiality of customer information and compliance with data protection regulations like GDPR.

