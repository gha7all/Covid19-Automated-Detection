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
XGBClassifier is the main idea, but we're gonna train the data with other models as well.

## Accuracy
78.66 is the highest level of accuracy we have reached so far, which, in any case, is not enough.
