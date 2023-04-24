1: Predicting World Happiness

For this project, I created models to predict country happiness level (very low, low, average, high, very high) based on predictor variables GDP per capita, freedom to make life choices, social support, healthy life expectancy, generosity, perceptions of corruption, terrorist attacks, country region and subregion. Data comes from the United Nations' World Happiness Rankings.

The sample plots below show how a few of these variables relate to happiness level:

![download](https://user-images.githubusercontent.com/61389709/234114745-8b95cfe1-d1de-4f5c-bc2d-d8833c0816dc.png)

![download-2](https://user-images.githubusercontent.com/61389709/234114877-14e9ec76-65c7-4db9-ab0b-9551d14b93c2.png)

![download-1](https://user-images.githubusercontent.com/61389709/234114881-9005287d-fb62-4ed5-9b2b-1dcff9e33b4c.png)

I tried a support vector machine model (svm), a keras model with 4 dense layers trained over 300 epochs, and a random forest model. The svm was my most successful model, which makes sense given that the dataset was quite small.

The best models in the class were gradient boosted trees and random forest models, though my svm model was actually equal to many in terms of accuracy. Going by F1 score, my svm model came in 5th out of 951 total submissions, so not bad at all.
