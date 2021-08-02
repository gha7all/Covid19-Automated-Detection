# Covid19 Automated Detection
Here we're going to classify given CTR images and distinguish whether if there is any sign of covid-19 or not. In this documentation we name some methods to show how we got here and how could we reach the highest accuracy; **only the methods that gave us the best results are included in the code**

## Dataset
Click [here](https://github.com/muhammedtalo/COVID-19) to access the dataset.
## How it works?
There are some simple methods in Deep learning which can classify images into different classes, but for the matter of science world, it is vital that we implement this project with the highest level of accuracy; so we're not using those simple methods, we're going to extract features of each image and then use classification methods.

## Feature Extraction
The CNN network architectures that we used to extract the features:

* MobileNet
* DenseNet 169
Those we tried and they failed:
* VGG16
* Xception
* Inception_V3


Throughout implementing this project, we have found an idea that it's better to combine feautures of two networks, we combined features of DenseNet and MobileNet. So the model is trained with 2600 features per each image.

## Classification
### Classifiers:
* LightGBM classifier
>LightGBM extends the gradient boosting algorithm by adding a type of automatic feature selection as well as focusing on boosting examples with larger gradients. This can result in a dramatic speedup of training and improved predictive performance.

Those we tried and they didn't give us a convenient accuracy:
* CatBoost Classifier
* XGBoost Classifier
* CatBoost Classifier
* Random Forest

So far the best and fastest classifier is LightGBM classifier and it gave us the highest accuracy of all.

## Parameters Tuning
Since there are multiple parameters to play with, we decided to find the best parameters for the classifier, which is not an easy experiment to do. There was not an exact way to find the best parameters and based on LightGBM's [documentation](https://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html) we manually set the parameters and observed the model's behaviour to tune parameters.


## Accuracy
91.11 is the highest percentage of accuracy we have reached so far, we reached this accuracy by using LightGBM classifier.

## Performance Metrics
Because our class distribution is imbalanced, we determined metrics beside accuracy, such as precision, sensitivity, specificity and f1-score.

