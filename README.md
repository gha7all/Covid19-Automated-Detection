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
* Inception_V3
* MobileNet

Throughout implementing this project, we have been changing some parameters for a better result.

## Classification
### Classifiers:
* XGBoost Classifier
* CatBoost Classifier
* Random Forest

## XGBClassifier parameters optimization
Since there are multiple parameters to play with, we decided to find the best parameters for the classifier, which is not an easy experiment to do; so we used Bayesian optimization, as wikipedia mentioned:
> Bayesian optimization is a sequential design strategy for global optimization of black-box functions that does not assume any functional forms. It is usually employed to optimize expensive-to-evaluate functions.

### Pip installation
```
pip install bayesian-optimization
```


## Accuracy
89 is the highest percentage of accuracy we have reached so far, we reached this accuracy by using catboost classifier.
