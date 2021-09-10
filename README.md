# Covid19 Automated Detection
Here we're going to classify given CTR images and distinguish whether if there is any sign of covid-19 or not. In this documentation we name some methods to show how we got here and how could we reach the highest accuracy; **only the methods that gave us the best results are included in the code.**

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
* ResNet


Throughout implementing this project, we have found an idea that it's better to combine feautures of two networks, we combined features of DenseNet and MobileNet.

## Feature Selection
Training the model by using all the extracted features probably isn't the best idea, so that the best features which have the most effect on producing output are selected by SelectKBest algorithm; it'll boost the speed of training. 2000 features per image are ready to be trained by a classifier.

## Classification
### Classifiers:
* LightGBM classifier
>LightGBM extends the gradient boosting algorithm by adding a type of automatic feature selection as well as focusing on boosting examples with larger gradients. This can result in a dramatic speedup of training and improved predictive performance.

Those we tried and they didn't give us a convenient accuracy:
* LightGBM Classifier
* XGBoost Classifier
* CatBoost Classifier
* Random Forest

So far the best and fastest classifier is LightGBM classifier and it gave us the highest accuracy of all.

## Parameters Tuning
Since there are multiple parameters to play with, we decided to find the best parameters for the classifier, which is not an easy experiment to do. There was not an exact way to find the best parameters and based on LightGBM's [documentation](https://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html) we manually set the parameters and observed the model's behaviour to tune parameters.


## Accuracy
* Binary class classification(Covid-19, No-finding): 98.54
* Multi class classification(Covid-19, Pneumonia, No-findings): 91.11
<br> In order to classify both types of classifications, the LightGBM classifier is used. The hyper-parameters are tuned.
## Performance Metrics
Because our class distribution is imbalanced, we determined metrics beside accuracy, such as precision, sensitivity, specificity and f1-score.

