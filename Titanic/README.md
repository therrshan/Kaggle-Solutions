# Kaggle-Titanic

* Implemented basic machine learning algorithm techniques on data set available.
* Data acquired from the Kaggle Competitions website.
* Logistic Regression, k-Nearest Neighbours, Decision Tree Classifier, Gradient Boosting Trees and CatBoost algorithm and cross validation method.

### Links 
Kaggle link of Competitions : https://www.kaggle.com/c/titanic

## Preparing the Data

* We can see that there a lot of missing values in two of the columns. 
* Go through each feature / coloumn and based on the number of missing values or in general the relation with survived members, decide wether or not to add in the training data frame.
* Also convert non integer feilds into integer to store in df_train_int

<img src="https://github.com/therrshan/Kaggle-Solutions/tree/master/Titanic/Images1.png" alt="">

<img src="https://github.com/therrshan/Kaggle-Solutions/tree/master/Titanic/Imagesimp.png" alt="">

## Model Building 

#### Logistic Regression
#### K Nearest Neighbours Classifier
#### Decision Tree Classifier
#### Gradient Boosting Tree

* These models are similar to fit and have the same steps through out.
* Thus a common function was written to use to fit the dataset on the different models.

#### CatBoost Algorithm

* Use the CatBoost Pool() function to pool together the training data and categorical feature labels


## Model performance

The results below are of the cross validation method for 10 folds as the regression models on one direction give high accuracy on training data which is irrelevant to the testing data.

*	**Logistic Regression** - 79.46
*	**KNN Classifier** - 76.88
*	**Decision Tree Classifier** - 80.36
*	**Gradient Boosting tree** - 81.14
*	**Catboost Algorithm** -  84.51

# Scope for future improvement

1. Compute a way to involve Age, Ticket and Cabin into the training data set for increasing the accuracy
2. If possible use the prefix from the name such as Mr. Mrs. Ms. Master. Dr. and give them labels and nvolve it in the training data set.
3. Scope out the errors in the plots that are occuring in two of the above plots without there being an error in the data frame.


