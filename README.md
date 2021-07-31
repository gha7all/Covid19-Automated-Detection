# Covid19 Automated Detection
Here we're going to classify given CTR images and distinguish whether if there is any sign of covid-19 or not.

## Dataset
Click [here](https://github.com/muhammedtalo/COVID-19) to access the dataset.
## How it works?
There are some simple methods in Deep learning which can classify images into different classes, but for the matter of science world, it is vital that we implement this project with the highest level of accuracy; so we're not using those simple methods, we're going to extract features of each image and then use classification methods.

## Feature Extraction
The CNN network architectures that we've been using:
* VGG16
* Xception
* DenseNet 169
* Inception_V3
* MobileNet

Throughout implementing this project, we have found an idea that it's better to combine feautures of two networks, we combined features of DenseNet and MobileNet.

## Classification
### Classifiers:
* XGBoost Classifier
* CatBoost Classifier
* LightGBM classifier
* Random Forest

So far the best and fastest classifier is LightGBM classifier and it gave us the highest accuracy of all.

## Parameters optimization
Since there are multiple parameters to play with, we decided to find the best parameters for the classifier, which is not an easy experiment to do; so we used Bayesian optimization, as wikipedia mentioned:
> Bayesian optimization is a sequential design strategy for global optimization of black-box functions that does not assume any functional forms. It is usually employed to optimize expensive-to-evaluate functions.

### Pip installation
```
pip install bayesian-optimization
```
We used this method to optimize xgboost classifier's parameters and used grid search to reach optimized parameters of catboost classifier.


## Accuracy
91.11 is the highest percentage of accuracy we have reached so far, we reached this accuracy by using LightGBM classifier.
