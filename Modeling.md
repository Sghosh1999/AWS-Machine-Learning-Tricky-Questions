**Question 1:**

After training a SageMaker XGBoost based model over a huge training dataset, the data science team observed that it has low accuracy on the training data as well as low accuracy on the test data.

As an AWS Certified ML Specialist, which of the following techniques would you recommend to help resolve this problem? (Select two):

- [x] Use more features in the model
- [x] Remove regularization from the model
- [ ] Use less features in the model
- [ ] Add regularization to the model
- [ ] Use less training data

For the given use case, as the model has low accuracy on the training data as well as low accuracy on the test data, it suggests that the model has a bias, or in other words, the model is underfitting. When a model is underfitting, then adding more features to the model or removing regularization can help in addressing the underlying problem. In case of an underfitting model, adding more training data may or may not help.

![Overfitting vs Underfitting](overfit.img)

**Question 2:**

A financial services company has the goal of reducing fraud transactions by 10% over the next financial year. In order to achieve this goal, which of the following is the most relevant model evaluation metric that the data scientists at the company need to focus on (the model’s predicted value of 1 implies that the transaction is predicted to be fraud)?

- [x] Precision-Recall Area-Under-Curve (PR AUC)


