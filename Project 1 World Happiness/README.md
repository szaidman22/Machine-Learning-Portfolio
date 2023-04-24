1: Predicting World Happiness

For this project, I created models to predict country happiness level (very low, low, average, high, very high) based on predictor variables GDP per capita, freedom to make life choices, social support, healthy life expectancy, generosity, perceptions of corruption, terrorist attacks, country region and subregion. Data comes from the United Nations' World Happiness Rankings.

The sample plots below show how a few of these variables relate to happiness level:

![download](https://user-images.githubusercontent.com/61389709/234114745-8b95cfe1-d1de-4f5c-bc2d-d8833c0816dc.png)

![download-2](https://user-images.githubusercontent.com/61389709/234114877-14e9ec76-65c7-4db9-ab0b-9551d14b93c2.png)

![download-1](https://user-images.githubusercontent.com/61389709/234114881-9005287d-fb62-4ed5-9b2b-1dcff9e33b4c.png)

I tried a support vector machine model (svm), a keras model with 4 dense layers trained over 300 epochs, and a random forest model. The svm was my most successful model, which makes sense given that the dataset was quite small.

Competition stats:

<img width="1006" alt="Screen Shot 2023-04-24 at 5 17 49 PM" src="https://user-images.githubusercontent.com/61389709/234125469-da36ad99-5689-4e9b-b45d-8e5737762010.png">

The best models on average out of 951 submissions based on F1 score were decision trees, closely followed by bagging classifiers.

Going by F1 score, my svm model came in 5th out of 951 total submissions, so not bad at all. I was second best in the competition based on average F1 score across all my submitted models.

<img width="1037" alt="Screen Shot 2023-04-24 at 5 33 07 PM" src="https://user-images.githubusercontent.com/61389709/234125519-2efbe004-7cd7-4854-91ee-4b1dc3cfa796.png">
