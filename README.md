# Machine-Learning-Portfolio
Portfolio with projects from advanced machine learning class taken in Spring 2023.
For more details please refer to this Jupyter notebook: https://github.com/szaidman22/Machine-Learning-Portfolio/blob/main/AdvancedMLProjectPortfolio.ipynb

## 1. Predicting World Happiness
https://github.com/szaidman22/Machine-Learning-Portfolio/tree/main/Project%201%20World%20Happiness

<img width="409" alt="Screen Shot 2023-04-24 at 6 43 03 PM" src="https://user-images.githubusercontent.com/61389709/234132003-959c6b80-f891-4f8d-83e3-f62d71f2f127.png">

For this project, I created models to predict country happiness level (very low, low, average, high, very high) based on predictor variables GDP per capita, freedom to make life choices, social support, healthy life expectancy, generosity, perceptions of corruption, terrorist attacks, country region and subregion. Data comes from the United Nations' World Happiness Rankings.

Models:
I tried a support vector machine model (svm), a keras model with 4 dense layers trained over 300 epochs, and a random forest model. The svm was my most successful model, which makes sense given that the dataset was quite small.

The best models on average out of 951 submissions based on F1 score were decision trees, closely followed by bagging classifiers.

Going by F1 score, my svm model came in 5th out of 951 total submissions, so not bad at all. I was second best in the competition based on average F1 score across all my submitted models.

## 2. Covid X-ray Classification
https://github.com/szaidman22/Machine-Learning-Portfolio/tree/main/Project%202%20Covid%20Xray%20Classification

![download-3](https://user-images.githubusercontent.com/61389709/234132133-eeef0c59-9df9-47e3-ac60-a00eb1e37f7a.png)

Summary:

In this project, I used publicly available X-ray images of patients with covid-19, pneumonia, and healthy controls to develop a model to accurately predict disease status (covid vs. pneumonia vs. healthy). I tested various from-scratch models utilizing 2-dimensional convolutional layers as well as a transfer learning models borrowing architecture components from InceptionV3.

Doctors, patients, hospitals and epidemiologists/other scientists and researchers could all benefit from models to assist in the diagnosis of COVID-related lung disease.

There is a clear use for this technology in assisting radiologists and physicians in diagnosing COVID-related lung disease vs. pneumonia, especially if, for instance, there is no detectable COVID virus in the patient (perhaps in the case of long-covid). Knowing the cause of specific lung problems could impact the way physicians treat the illness and could make a difference in a patient's recovery and outcome.

This technology could also impact hospital operations and insurance claims. If a patient is diagnosed with having COVID-related lung issues as opposed to pneumonia, this could result in changes to billing procedures.

Epidemiologists could use diagnostic models to improve data quality for analyses of COVID transmission and incidence of acute COVID illness.

Models:

First I tried a basic sequential model with 10 Conv2D layers. I chose 32 filters for all Conv2D layers. I chose to train it over 14 epochs to begin with. This basic model performed actually relatively well with accuracy in the low 90s for the test data. I tried additional models that used this same sequential model as a template and changed the number of layers and filters slightly. Ultimately my best model at this stage had 15 layers total, 8 Conv2D layers all with 32 filters, and 4 max pooling layers.

Next I attempted a transfer learning model. I used the InceptionV3 model and changed the output shape to match the data. The initial model I used did not perform nearly as well as my much smaller sequential models, and I wanted to focus more on those, so I didn't try altering this model.

Next I tried adding batch normalization layers to my best sequential model. This worked very well and increased my test predicition accuracy by about 4%. My best performing model ended up with 24 layers total, 10 Conv2D layers, 6 with 32 filters and 4 with 16 filters, 4 max pooling layers, and 9 batch normalization layers. My best accuracy was about 94%.

In general, I found that models with relatively small numbers of filters and many batch normalization layers dispersed between Conv2D layers, trained over about 10-20 epochs worked best.

My best model ranked 12th on accuracy out of 451 total models submitted. Overall I came in 8th based on average F1 score accross all models submitted.

I did however manage to achieve high F1 scores with very few parameters in my models compared to other competitors.

For this competition there seems to be an optimal depth for models of about 34 layers to get best F1 score.

## 3. Movie Review Sentiment Classification
https://github.com/szaidman22/Machine-Learning-Portfolio/tree/main/Project%203%20Movie%20Review%20Sentiment%20Classification

<img width="382" alt="Screen Shot 2023-04-24 at 6 49 32 PM" src="https://user-images.githubusercontent.com/61389709/234132810-ee08a03c-12a9-4403-9266-14145243a075.png">

Summary:

In this project, I used text embeddings combined with LSTM and Conv1d-based deep learning models to predict whether a movie review is positive or negative.

The dataset used contains about 9000 total movie reviews that are labeled as having either positive or negative sentiment.

Building a model to predict the sentiment of movie reviews would be practically useful for websites like Rotten Tomatoes or IMDB, which aggregate reviews from multiple sources and generate an overall rating for a film. It could also be useful as an input for a movie recommendation algorithm.

Models:

All of the models I tried performed very similarly, ranging from 78% accuracy to 81% accuracy. I tried a few LSTM-based models, some models with stacked conv1d layers, added batch normalization to one, played around with adam vs. rmsprop optimization. I tried training my own embeddings and used glove embeddings (via transfer learning). I also tried adding bidirectional LSTMs based on other top models I saw on the leaderboard. There was not a very clear jump in accuracy caused by tuning any of these hyperparameters. When I investigated the top performing models, I found that there was a good amount of variation in model architecture. Unfortunately, the highest performing model by 10% accuracy didn't have any model details submitted to the contest page. I wonder if it was based on transfer learning from a pre-trained sentiment classification model.

Ultimately, my best performing model had one LSTM layer with .4 dropout and used the pre-trained glove embedding layer. I found the dropout hyperparameter had the most noticeable effect in changing how fast the model was learning and dealing with overfitting. If I were to continue trying to refine my models, I would probably try gridsearch with different dropout ranges.

Overall I reigned supreme and came in first on average F1 score accross all models submitted.
