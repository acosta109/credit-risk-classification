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
  * `log_model = LogsiticRegression(random_stage=1)`
  * `accuracy = 0.944`
  * `precision = Healthy Loan: 1.00 --- High-Risk Loan: 0.87`
  * `recall = Healthy Loan: 1.00 --- High-Risk Loan: 0.89` 
  * `f1-score = Healthy Loan: 1.00 --- High-Risk Loan: 0.88 `



* Machine Learning Model 2:
  * `ros_model = RandomOverSampler(random_state = 1)`
  * `accuracy = 0.995`
  * `precision = Healthy Loan: 1.00 --- High-Risk Loan: 0.87`
  * `recall = Healthy Loan: 1.00 --- High-Risk Loan: 1.00` 
  * `f1-score = Healthy Loan: 1.00 --- High-Risk Loan: 0.93 `

## Summary

From the results above, we can observe both models can predict the outcome of a loan well. Our resample method, using `RandomOverSample` is
more accurate and better predicts if a loan will be a high-risk loan `0.995 > 0.944`. Moreover, We can observe the recall of for high-risk loans increase when implementing the `RandomOverSample` `0.89 -> 1.00`.  This means, in our original mode, 89% of high-risk loans were identified in model 1, while 100% of high-risk loans were identified in model 2. Overall, I recommend this model. 