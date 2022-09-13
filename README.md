# Learnings 
Super Market Sales Analysis

•	Objective
Overview

Creating a classification machine learning model to predict Customer_Type, Which will be resulting in better targeting of products and services of Super Market, So We can achieve high sales #from each customers and retention of customer base as per their purchases pattern via campaigns/offers.

•	Methodology

Univariate, Bi-variate, and Multivariate analysis on the EDA of Supermarket sales data. Create a model to analyse the relationship between different variables of the supermarket.
Create a classification model to identify how the other features are related to the target feature. Create a prediction model to predict the day of future purchase.
Classification of goods: Based on the analysis of the historical consumption data of the supermarket.

This dataset is one of the historical sales of supermarket company which has ... Predictive data analytics methods are easy to apply with this datasets.

We have implemented Random forest and logical regression model to build the target model.


•	The 3 classifiers used
Model 1: Baseline RandomForest Algorithm gives 47% accuracy
Model 2: GridSearch Tunned RandomForest Algorithm gives 49% accuracy Model 3: Baseline LogisticRegression Algorithm gives 53% accuracy
Model 4: GridSearch Tunned LogisticRegression Algorithm gives 50% accuracy


•	Ensemble pipeline
1.	Ensemble methods are commonly used to boost predictive accuracy by combining the predictions of multiple machine learning models.
2.	We have fine-tuned the Random search and Logistic regression model using GridSearch Tunned Algorithm.
3.	Build a data pipeline that works with ... making it useful for polyglot projects typical of modern data science.
4.	Ensemble modelling is a process where multiple diverse models are created to predict an outcome, either by using many different Modelling algorithms.
•	Other models considered
We can use multiple models apart from Random search and Logistic regression, however we have used these two models in achieving the target system.


•	Hyper-parameter tuning
1.	Since we have used GridSearch Model 2 and 4, we can optimize with hypermarket tuning.
2.	Hyper-parameter optimization or fine tuning is the problem of choosing a set of optimal hyper-parameters for a machine learning algorithm.



1.	Classification Report is: (Random Forest) precision recall f1-score support

member	0.47	0.47	0.47	150
normal	0.47	0.47	0.47	150

accuracy		
0.47	
300
macro avg	0.47	0.47	0.47	300
weighted avg	0.47	0.47	0.47	300

Confusion Matrix: [[70 80]
[80 70]]


2.	#Selecting Model :random forest- Hyper parameter tunning Classification Report is:
precision   recall f1-score support

member	0.49	0.49	0.49	150
normal	0.49	0.49	0.49	150

accuracy		
0.49	
300
macro avg	0.49	0.49	0.49	300
weighted avg	0.49	0.49	0.49	300

Confusion Matrix: [[74 76]
[76 74]]


3.	#Logistic Regression using sklearn Classification Report is:
precision recall f1-score support

member	0.52	0.63	0.57	150
normal	0.54	0.43	0.48	150

accuracy		
0.53	
300
macro avg	0.53	0.53	0.52	300
weighted avg	0.53	0.53	0.52	300

Confusion Matrix: [[95 55]
[86 64]]


4.	#Selecting Model :Logistic Regression- Hyper parameter tunning Classification Report is:
precision recall f1-score support

member	0.50	1.00	0.67	150
normal	0.00	0.00	0.00	150

accuracy		
0.50	
300
macro avg	0.25	0.50	0.33	300
weighted avg	0.25	0.50	0.33	300

Confusion Matrix:
[[150 0]
[150 0]]



1.	Model 1: Baseline RandomForest Algorithm gives 47% accuracy
2.	Model 2: GridSearch Tunned RandomForest Algorithm gives 49% accuracy
3.	Model 3: Baseline LogisticRegression Algorithm gives 53% accuracy
4.	Model 4: GridSearch Tunned LogisticRegression Algorithm gives 50% accuracy


We can conclude Baseline RandomForest Algorithm can be used for deployment. From above models accuracy then can see that even with model hyper parameter tunning no good increase in accuracy has happened. We need to try other feature engineering techniques for model building.
LogisticRegression baseline model is giving us best accuracy


•	How many features

16 features are there in the dataset, we have dropped Invoice and time as it is significant.

•	Size of the dataset
1000 rows are there in the dataset.

•	Multiple files
Single Supermarket sales dataset file. Dataset contains various attributes of supermarket like Invoice Id, Branch, City, Customer Type, Gender, Product Type, Unit Price, Quantity, Tax, Selling Price, Date, Time, Payment Type, Cost Price, Gross Income, and Rating.

•	What kind of data – numerical or character
Both Numerical data and Character data are present on the Input dataset.
It is evident that Invoice ID is detected as “typeless” since it has hyphens in between which could not be detected as a valid measurement type. Whereas, fields like branch, city, product line and payment are “nominal” that have multiple values. The customer type and gender are a binary field, and thus has “flag” measurement. And the rest of the variables are “continuous” since they have a range of numeric values.

•	Balanced or imbalanced – what is the distribution
Target Future is the Customer Type and it is Balanced.

•	Distribution of Training set, validation set, testing set
      •	Total number of feature dataset: 1000
      •	Total number of training data: 700
      •	Shape of train data: (700, 31)
      •	Shape of test data: (300, 31)

•	Missing data and Preprocessing challenges
No Missing Value, #No NA, so no need of NA imputation. Tax, Selling and Cost Price has upper tail outliers.
Replacing outliers values with 90% quantile values for upper tail and 10% quantile values for lower tail outliers

Feature Engineering Techniques
•	Features removed
a.	We have dropped Invoice and time as it is evident that Invoice ID is detected as “typeless” since it has hyphens in between which could not be detected as a valid measurement type. Time doesn’t make any significance in achieving the target feature and model.
b.	Tax, Selling_Price, Cost_Price are highly Postive correlated to Target feature (Gross_Income). Therefore we have dropped Tax, Selling_Price,Cost_Price features.
Feature creation
We extracted the day, moth and year from the date feature and used in our model building.
Feature ranking
Rating, Unit Price, Quantity are the top 3 features

The Diagram

Class imbalance treatment
No Missing Value , #No NA, so no need of NA imputation. The target feature class type is balanced.
Any other
Tax, Selling and Cost Price has upper tail outliers. Replacing outliers’ values with 90% quantile values for upper tail and 10% quantile values for lower tail outliers for tax selling price and cost price.

Table for the evaluation metric for each ML technique used
 
Results
 
Model Name	Accurracy	Recall	F1
score	Support
Baseline RandomForest Algorithm gives 47% accuracy	0.47	0.47	0.47	300
GridSearch Tunned RandomForest Algorithm gives 49% accuracy	0.49	0.49	0.49	300
Baseline LogisticRegression Algorithm gives 53% accuracy	0.53	0.53	0.53	300
GridSearch Tunned LogisticRegression Algorithm gives 50%
accuracy	0.50	0.50	0.50	300

Conclusion
1.	We used Uni-variate, bi-variate and correlation analysis to perform basic EDA on the supermarket sales data.
2.	To summarize below are some of the findings/observations from the data:
3.	The customer rating is more or less uniform with the mean rating being around 7 and there is no relationship between gross income and customer ratings.
4.	The data consists of 3 cities/branches. Though branch C has slightly higher sales than the rest, A and B.
5.	There is no particular time trend that can be observed in gross income.
6.	At an overall level, ‘Sports and Travel’, home and life style generates highest gross income.
7.	Using the correlation analysis, one interesting observation has emerged that customer ratings is not related to any variable.
8.	Though the rating for ‘fashion accessories’ and ‘food and beverages’ is high but the quantity purchased is low. Hence, supply for these products need to be increased.
9.	We can offer Loyalty Programs so that we can attract more customers and so that they can get enrolled in the membership,



