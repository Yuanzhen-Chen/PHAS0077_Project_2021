# Using Machine Learning Algorithms to Identify Physician-Hospital
# Integration Based on Physician Characteristics Data


## Description
This repository contains the project report ("PHAS0077_Project_YuanzhenChen.pdf"), the project 
code ("PHAS0077_Codes.ipynb"), and the datasets including NPPES provider data ("npidata_20050523-20100208.csv"),
physician characteristics data ("physician_integration_gi_2005_2015.csv") and RUCC code convertion 
files ("ruralurbancodes2013.xls" and "zipfips.csv"). After running the code, a file named "zipfips_new.csv"
will be created, which is tranposed dataset of "zipfips.csv".

CMS Medicare datasets ("Medicare_Provider_Util_Payment_PUF_*.csv") are not in the repository because
their sizes are too large to be accepted by Github.


### Project code
The project code has three modules: Data processing, Machine Learning Models and Prediction. 
Before these is the advance preparation, including defining functions and data pre-loading.

#### Data Processing
This module will load, clean and merge three of the datasets including CMS Medicare data, 
physician characteristics data and NPPES provider data. For initialization, select the year of data 
(from 2012 to 2015) and the model type (claim-based model or claim-free model) so that the 
code will load the data of the year and use the required variables. Finally, create the objects X 
and y as independent variables and predictor variable respectively and split them into 75% 
training set and 25% testing set.

#### Machine Learning Models
This module is the implementation of Machine Learning Algorithms using scikit-learn library 
mainly. The applied algorithms are Linear Regression, Logistic Regression, Support Vector 
Machine, Decision Tree, K-Nearest Neighbour, Naive Bayes and Random Forest. For each 
algorithm, train the model using training set data and use grid search to find the optimal values 
of the parameters. Lastly, compute accuracy, precision, recall and f1 score for the classification
on both of training set and testing set data.

#### Prediction
This module applies SVM, Decision Tree, KNN and Random Forest models to predict physicians’ 
integration status, computes the percentages of physicians that are predicted to be integrated 
with hospitals and creates a line chart that shows the integration trend from 2015 to 2018.
