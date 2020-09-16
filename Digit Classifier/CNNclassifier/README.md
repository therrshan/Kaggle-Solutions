# CNN Keras Model
MNIST data set of digit classifier solved by a Convulational Neural Network using Keras



* Built a Sequential Keras Model using TensorFlow.
* Data acquired from the Kaggle Competitions website.
* Methods such as Convulationa2D, MaxPooling and Callbacks were used.

### Links 
Kaggle link of Competitions : https://www.kaggle.com/c/digit-recognizer/overview

## Preparing the Data

* We can see that unlike more complex computre vision tasks, we are given the pixel values in a table, and have no actual "images" to load in. 
* Train and test images (28px x 28px) has been stock into pandas.Dataframe as 1D vectors of 784 values. We reshape all data to 28x28x1 3D matrices where 1 is the dimesnion of bytes representing colour.
* We perform a grayscale normalization to reduce the effect of illumination's differences. Moreover the CNN converge faster on [0..1] data than on [0..255].
* There are no missing values in the train and test dataset. So we can safely go ahead.
* But the table of data is not enough as we have to split the label, or what we are predicting, from the training data, or the pixels.

<img src="https://github.com/therrshan/Kaggle-Solutions/blob/master/Digit%20Classifier/images/3.png" alt="" width="400" height="300" align="centre">

## Model Building 

### Model Definition:

* The model is built using the Keras Sequential API, where you have just to add one layer at a time, starting from the input.

* The first is the convolutional (Conv2D) layer. We set 32 filters for the two firsts conv2D layers and 64 filters for the two last ones. Each filter transforms a part of the image (defined by the kernel size) using the kernel filter. The kernel filter matrix is applied on the whole image. Filters can be seen as a transformation of the image.

* The CNN can isolate features that are useful everywhere from these transformed images (feature maps).

* The second important layer in CNN is the pooling (MaxPool2D) layer. It looks at the 2 neighboring pixels and picks the maximal value. These are used to reduce computational cost, and to some extent also reduce overfitting. 

* Combining convolutional and pooling layers, CNN are able to combine local features and learn more global features of the image.

* Dropout is a regularization method. This drops randomly a propotion of the network and forces the network to learn features in a distributed way. This technique also improves generalization and reduces the overfitting.

### Model Fitting Functions:

1. Optimizer: The RMSProp update adjusts the Adagrad method in a very simple way in an attempt to reduce its aggressive, monotonically decreasing learning rate.
2. Metric Function: The metric function "accuracy" is used is to evaluate the performance our model. This metric function is similar to the loss function, except that the results from the metric evaluation are not used when training the model.
3. Callbacks: With the ReduceLROnPlateau function from Keras.callbacks, i choose to reduce the LR by half if the accuracy is not improved after 3 epochs.

### Data Augmentation: 

* Approaches that alter the training data in ways that change the array representation while keeping the label the same are known as data augmentation techniques. Some popular augmentations people use are grayscales, horizontal flips, vertical flips, random crops, color jitters, translations, rotations, and much more. 

* By applying just a couple of these transformations to our training data, we can easily double or triple the number of training examples and create a very robust model.

Data Augmentation Techniques choosed:
   - Randomly rotate some training images by 10 degrees
   - Randomly  Zoom by 10% some training images
   - Randomly shift images horizontally by 10% of the width
   - Randomly shift images vertically by 10% of the height
   
I did not apply a vertical_flip nor horizontal_flip since it could have lead to misclassify symetrical numbers such as 6 and 9.

### Model error plots for further analysis:

<img src="https://github.com/therrshan/Kaggle-Solutions/blob/master/Digit%20Classifier/images/2.png" alt="" width="400" height="300"> <img src="https://github.com/therrshan/Kaggle-Solutions/blob/master/Digit%20Classifier/images/1.png" alt="" width="400" height="300" >

 
## Model performance

The model, on the validation data set after just using the base data augmentation gave the final result of 98.25% accuracy.

