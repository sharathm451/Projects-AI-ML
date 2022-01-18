
# Ensemble Techniques Optimization

Ensemble Techniques Optimization is used for to improve the machine learning results:

    it is exactly like fine tuning the results by figuring out the best model to it.
    so lets get into this small info:

    

# Optimizations

There are three types of Optimizations here:

They are: 
### 1) bagging:
Building  parallel multiple models (typically of the same type) from different subsamples of the training dataset.
Bagging stands for bootstrap aggregation. One way to reduce the variance of an estimate is to average together multiple estimates.

a) Bagging classifier/regressor

b) Random forest classifer/regressor

c) Extra Tree classifer/regressor

### 2) boosting:
Building multiple models (typically of the same type) each of which learns to fix the prediction errors of a prior model in the sequence of models.

a)AdaBoost classifer/regressor

b)GradientBoosting classifer/regressor

### 3) stacking:
Building multiple models (typically of differing types) and simple statistics (like calculating the mean) are used to combine predictions.

# project:
Given dataset is bank.csv containing info of previous campaigning results features like default credit values, house loan possessed, age, education, job, balance, pdays,poutcome, etc..

Aim is to predict the targeted customers subscribing to term deposit or not whether.

# performed operations on data:
## EDA:
   check the missing values¶

   Distribution of numerical columns(dist plots)¶

   Distributions of categorical cols¶

   Measure of skewness of numerical data¶

   check the outliers¶

   TARGET DISTRIBUTIONS¶

## Data preprocessing¶

   Label encoding¶

   Checking & modifying datatypes after Label Encoding¶

   Handling outliers with mean replacement¶

   corr and plot of all features¶

   Data visualization¶


# Building the models

  Train Test Split¶

  Scaling the X¶

  Models:
  
  logistic regression,Naive bayes,knn,svc,decision tree

  pruning of decision tree 

  Feature importance test of decision tree¶

# applying optimizations:
Bagging,
Boosting,
Voting classifier

models with accuracy scores.

# 5 points summary understanding from describe:
Outliers are present in 'age', 'balance', 'duration', 'campaign', 'pdays' and 'previous' columns.

    reason: mean and std(standard deviation) have high variance or difference

'balance', 'duration', 'campaign', 'pdays' and 'previous' are right skewed.

    Reason: if mean is less than std then it is right skewed or else left skewed

More than 75% people have been contacted in a day after previous campaign as pdays is -1 till 75th precentile

Minimum balance is -8019 and maximum balance is 102127

Minimum age is 18 years and maximum is 95 years

pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)



# Understanding from distributions
More than 90% customers have no default credit

Around 88% customers have not subscribed for term deposit

Most customers have been contacted in may

Most customers have been contacted by cellular network(mobile phone)

Number of customers who have housing loan is more than the number of customers who don't have housing loan

Around 6% customers have credit in default



# Conclusion
## Comments on dataset:
The models perform well in predicting the class 0 i.e. customer not subscribing to term deposit which can be seen in the confusion matrix of all models.

The models do not perform well in predicting the class 1 i.e. customer subscribing to term deposit which can be seen in the - - confusion matrix of all models.

Above situation occured because the Dataset is imbalanced. i.e. The ratio difference between class 0 and class 1 is huge. Which trained models to effectively identify class 0 but did not train suffuiciently to classify class 1.

This situation could have been avoided if the datset was balanced.

Along with imbalance, the dataset contained large number of unknown string values in 'job','education','contact' and 'poutcome' columns.








