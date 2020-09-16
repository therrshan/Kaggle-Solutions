# Kaggle-Advanced-Regression

* Implemented advanced regression techniques on data set available.
* Data acquired from the Kaggle Competitions website.
* Optimized Linear, Lasso, Min Max, ridge and Random Forest Regressors to reach the best model. 

### Links 
Kaggle link of Competitions : https://www.kaggle.com/c/house-prices-advanced-regression-techniques


## Data Cleaning
### The obtained data had too many missing values. Those were filled using the following methods:

*	Replaced with 'None' for features where missing value meant the feature was not available
*	Replaced with the mode for most of the values
*	Mode was chosen because the average of the columns was not required.
*   Columns with numeric dta was transformned into strings for the label encoder
*   All the missing values were ultimately filled to get uniform data

### Label encoding
*	all the data columns were encoded using the label encoder

## EDA
The plots for various columns were observed for relations between them. Below are a few of the important revelations.
Also the sales and the probability were highly morphed. They were normalized by fitting to the norm method,  

![alt text](https://github.com/therrshan/Kaggle-Solutions/blob/master/Housing%20Price%20Prediction/Images/correlation.png "Relations between some of the values")
![alt text](https://github.com/therrshan/Kaggle-Solutions/blob/master/Housing%20Price%20Prediction/Images/normalized.png "Normalized curve of sales")
![alt text](https://github.com/therrshan/Kaggle-Solutions/blob/master/Housing%20Price%20Prediction/Images/normP.png "Normalized curve of probability")

## Model Building 

The  data set was split into Test data and train data.   

These are some of the most commonly used advanced regression techniques that are implemented. 

Used models:
*	**Linear Regression**
*	**Lasso Regression**
*	**Random Forest** 
*	**Min Max Scaler**
*	**Ridge Regression**  

## Model performance

The Random Forest model was way too effective as compared to the other regression models
*	**Linear Regression** - 0.899
*	**Lasso Regression** - 0.846
*	**Random Forest** - 0.971
*	**Min Max Scaler** - 0.884
*	**Ridge Regression** -  0.902

# Note:
 * The XGBoost algorithm used is way too accurate as compared to other regression models.
 * But in the case of this data the difference was just 0.2 percent as Random Forest was already way too high.
 * I have provided the python script for xgboost algorithm on the same data set as a python file.

