# Kaggle-Diabetes-Prediction
Link :: https://www.kaggle.com/competitions/playground-series-s5e12
rank :: 4032/4206

Logistic refgression model for Diabetes Prediction S5 Ep12 challenge on kaggle. This is my first challenge submission in which i just focused on learning instead of rank. 
Steps i followed ::
1. imported pandas numpy
2. loaded train, test and submission data
3. checked columns and found one which was of no use
4. removed the column 'id' which was of no use
5. checked of missing values using df.isna().sum() found sum=0 for each column
6. seperated features x and target y where x is dataframe and y is series
7. checked for imbalance data but found 1.0->436307 and 0.0->263693 which is nearly 60 40 and need not to balance.
   This can be managed using precision, recall, f1 score
8. identified categorical columns which are 'gender', 'ethenticity', 'education_level','income_level','smoking_status','employment_status'
9. used one hot encoding for transforming the categorical column into 0 1
   example in 'gender' we have 'female' 'male' and 'other' so we will get
   1 0 for male, 0 1 for other and if we will get 0 0 means it is female
   doing this will not mean that 1>0 means male greater than other but it assign 0 if not male 1 if male
10. performed train test split
11. imported pipeline and logistic regression
12. created the pipeline used solver='saga' which is used for large datasets and work well with L1 regularization
13. used model.fit()
    - This is step at which logistic regression model finds weights that maximize the likelihood of predicting the correct class.
    - It uses sigmoid function to convert linear combination to probability where p=1/(1+e^-z)
    - Threshold is 0.5
      if predicted probability is less than 0.5 class is 0
      else 1
14. model.predict(X_test) this is used for testing the model
15. evaluation matric accuracy, precision, recall, f1 score
16. model.predict(test) this is test.csv which is used for submission
17. submission file

# Other models to use are
- random forest
- decision tree
- knn
- svm
- naive bayes
will soon solve using these models.
