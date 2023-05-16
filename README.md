## Overview of the Analysis

I aim to evaluate historical data of peer-to-peer lending services by building a machine learning model that can identify the crediworthiness
of borrows. I want to idenfify if a loan will be health or high-risk using a LogisticRegression. From the data I imported, we can see 75,036 
heathly loans and 2,500 high-risk loans. I display this using `y.value_counts`. 

I start by training training my model`log_model = LogsiticRegression(random_stage=1)`, fitting my model `log_model.fit(X_train, y_train)`,
and making my predictions `testing_prediction = log_model.predict(X_test)`.  After I review the results - I will discuss this later in my 
analysis - I decided try a resampling menthod `RandomOversampling`. With my new model `ros_model = RandomOverSampler(random_state = 1)` I 
peform the same process for analysis. 

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1: 
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  * `log_model = LogsiticRegression(random_stage=1)`
  * `accuracy = 0.944`
  * `precision = Healthy Loan: 1.00 --- High-Risk Loan: 0.87`
  * `recall = Healthy Loan: 1.00 --- High-Risk Loan: 0.89` 
  * `f1-score = Healthy Loan: 1.00 --- High-Risk Loan: 0.88 `



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  * `ros_model = RandomOverSampler(random_state = 1)`
  * `accuracy = 0.995`
  * `precision = Healthy Loan: 1.00 --- High-Risk Loan: 0.87`
  * `recall = Healthy Loan: 1.00 --- High-Risk Loan: 1.00` 
  * `f1-score = Healthy Loan: 1.00 --- High-Risk Loan: 0.93 `

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
