# Model Card

The model is a decision tree designed to identify fraudulent transactions. The model is designed, trained, and tested on credit card data which has undergone PCA transformation. Therefore, the data contains 28 variables labelled V1-V28, along with the time and monetary value. 

The model is built on credit card data, but due to the transformation and anonymisation, the principles could be applied to other fraud investigation or identification issues, such as forensic accounting or the audit of financial statements. This model is intended for use in credit card data in the same format, but the principles and approach could apply to a financial ledger in many other formats.

A decision tree model was selected primarily for the interpretability and explainability of the outcome, which would be important in many fraud detection situations where explaining the outcome or decision to stakeholders and being able to justify the choices made can be as important as getting the right answer.

## Model Description

**Input:** 
The inputs to the model are credit card transactions which have undergone PCA transformation. As a result, they include time (since first transaction in dataset), monetary amount, and 28 anonymised variables labelled V1-V28.

**Output:** 
The model classifies transactions as fraudulent (1) or not fraudulent (0)

**Model Architecture:** 
Two decision trees were constructed, one based tuned to have the best F1 score during 5-fold cross validation, and one tuned to have the best recall (with a minimum precision of 80%) during 5-fold cross validation.

Model 1 (best F1 score):
The model is a decision tree which was trained with a maximum of depth of 6 and class weights attributed as 0:0.3 and 1:0.7

Model 2 (best recall with a minimum precision of 80%):
The model is a decision tree which was trained with a maximum of depth of 4 and class weights attributed as 0:0.2 and 1:0.8


## Performance
Once tuned, the two models were tested on the final 25% of the dataset. This was the most recent transactions, as this best represents the real world problem of fraud detection, where models can be built on historic data but need to identify fraud as transactions occur in real time, or in the case of investigations or audits, models can be built on older data to identify transactions in the most recent ledgers.



## Limitations

The model can only classify transactions in the same format as the training data, and therefore would need to be retrained and tuned for other uses, as this is specific to a credit card transaction dataset which has already undergone PCA transformation.

The nature of fraud results in highly unbalanced datasets. For example, in this case there were 492 fraudulent transactions is a dataset of 284,807 transactions. As a result, the results of the model can be volatile, with a small change in weighting resulting in a significant increase in false positive classification, and an increase in the risk of overfitting already present in a decision tree model.

The model was designed as a proof in concept for building an explainable fraud detection model, however the method has only been applied to one credit card dataset which had previously undergone PCA transformation. It needs further investigation as to whether this model could be adapted to be run on other financial information such as company sales records.

It was noted that even though cross validation performance was very strong, there still remained a relatively high level of false negatives in the testing, with the best recall of 73.4%. However, this could be improved by reducing the precision threshold for selecting model 2, to reflect that the generalised recall on newer data may be reduced, and therefore a more risk averse strategy may be needed.

## Trade-offs

Due to the high level of imbalance in the dataset, measuring performance and selecting the performance metric to optimise in hyperparameter tuning were key trade-offs to be made. In general the cost of not identifying a fraud is considerably higher than the cost of investigating a non fraudulent transaction. However, this cost difference is not infinite and therefore there comes a tipping point where too many false positives outweighs the benefit of increasing true positives. When tuning the model, the user has to set a suitable metric based on their risk appetite.
