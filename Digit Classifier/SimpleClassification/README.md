# Simple Classification Techniques
MNIST data set of digit classifier solved using basic classification models



* Implemented basic classification techniques on data set available.
* Data acquired from the Kaggle Competitions website.
* KNN classifier, XGBoost Decision tree classifier and different version of Naive Bayes Model implemented. 

### Links 
Kaggle link of Competitions : https://www.kaggle.com/c/digit-recognizer/overview

## Preparing the Data

* We can see that unlike more complex computre vision tasks, we are given the pixel values in a table, and have no actual "images" to load in. 
* But the table of data is not enough as we have to split the label, or what we are predicting, from the training data, or the pixels.
* Some simple preprocessing to start out, to improve the model quality and speed up training. First I will normalize the data to the values of 0 and 1, to speed up training and help the model converge faster.

## Model Building 

### K Nearest Neighbours Classifier
* For this dataset, where each number is fairly distinct and different, KNN classifier should work well, as it can create clear distinctions between the different groups and points. There are still a couple parameters we have to specify, though.

* First, we have the n_neighbors parameter, which denotes how many neighbors we should compare each point with. Remember to keep in mind how large your training data is and how distinct your labels are, as too many neighbors many result in large influences from wrong labels and groups.

<img src="https://github.com/therrshan/Kaggle-Digit-Classifier/blob/master/images/KNN.png" alt="" width="600" height="400">

### Naive Bayes Classifier

#### Multinomial Naive Bayes
* The Multinomial classifier is a Naive Bayes model based off a Multinomial distribution. Here, the model is able to handle discrete values better and are used more when there are integer values rather than boolean.

#### Gaussian Naive Bayes
* Gaussian distribution is similar except it uses the Gaussian distrubtion to predict. Therefore, the distribution is preset, regardless of the data, and using the normal Gaussian distribution, the Naive Bayes model is able to make its predictions.

<img src="https://github.com/therrshan/Kaggle-Digit-Classifier/blob/master/images/normal.png" alt="" width="600" height="400">

#### Bernoulli Naive Bayes
* Bernoulli Naive Bayes Classifer. This basically implements a binomial distribution, which is similar to the multinomial distribution, except it uses 0 and 1s in a boolean fashion. Therefore, values are either present or not, whereas the count of the value is obsolete. This model should technically be the best one to use on our model. 

<img src="https://github.com/therrshan/Kaggle-Digit-Classifier/blob/master/images/binomial.png" alt="" width="600" height="400">


### XGBoost Classifier
* XGBoost is a great resource to train gradient boosted decision trees fast and accurately. It has an option to use either trees or linear models, and there are several other parameters for you to choose from. For this model, I will be using a decision tree because I am doing a classification task.

* For this data, the tree method should work out pretty well, especially because each number will cover different pixels, so different combinations of pixels should be a pretty strong way to differentiate between the labels.

<img src="https://github.com/therrshan/Kaggle-Digit-Classifier/blob/master/images/xgboost.png" alt="" width="600" height="400">


## Model performance

The XGBoost Classifier model was way too effective as compared to the other models
*	**XGBoost Classifier** - 97.29
*	**KNN Classifier** - 96.59
*	**Multinomial Naive Bayes** - 82.77
*	**Gaussian Naive Bayes** - 56.57
*	**Bernoulli Naive Bayes** -  83.40


