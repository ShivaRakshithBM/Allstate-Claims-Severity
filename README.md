Problem Statement:
Predict the amount of insurance claim for Allstate customers.

Questions:
1) What are the factors to include for determining the amount of insurance claim?
2) What are the techniques to be followed for predicting the insurance claim amount?

Approach:
Followed the 6 stage framework of CRISP Data Mining process
CRISP - Cross-Industry Standard Process

Business understanding:

1) Allstate is a multi billion dollar insurance company. Its goal is to reduce the time or mental energy spent for pusshing paper with the insurance agent
2) Allstate is creating automated methods of predctng incurance claim costs

Data understanding

1) The dataset consists of 188,319 instances, each corresponding to a claim from a customer
2) The data includes both categorical and numerical variables. It has 116 categorical variables and 14 continuous variables. The target variable is the claim amount

Data Preperation:

1) Normalization: I had to get all the variables into a standard range and give equal weightage to all of them in our predictions. I have implemented the min - max normalization

2) Log transformation
plotting the distribution of target variable -- number of shares, I noticed that it was right-skewed, so I did log transformation to reduce the skewnes

3) Principle Component Analysis
reduced the dimensions of the input dataset from 58 to 31, by  keeping 98% of the variance in the dataset

Modelling:
1) Have implemented SVM with non linear kernel, Decision trees, Random forests with Adaboost
2) The reason to select only non linear models is we hand pickex the imporatnt variables from the lot which might be affecting the target variable. Post which we checked the relationship between each of the hand picked variable and the target variable and found it was mostly non linear
3) Also, we saw that combination of variables together would afffect the target variable (interaction terms)

Evaluation:
1) I have used Cross validation of 10 folds. The model has been implemented to hold out data sets. 
2) Have used the metric Root Mean Square Error (RMSE) to evaluate the difference of Actual and predicted number of shares
3) Baseline - We took the mean number of shares for the articles at the categoruy of the article and then leveraged RMSE for comparison

Deployment:
1) The analysis ccan be used by deploying thhe same in Mashable. Multiple users can access if its on a cloud sharing platform like AWS or R server
2) It can also be automated so that on a daily basis when the data changes, the predictions can be produced and used. We can connect the model to the platform from where the data is stored
