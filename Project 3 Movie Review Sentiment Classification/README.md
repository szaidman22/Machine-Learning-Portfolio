## Movie Review Sentiment Classification

<img width="382" alt="Screen Shot 2023-04-24 at 6 49 32 PM" src="https://user-images.githubusercontent.com/61389709/234133498-50d3640a-044c-4c40-836e-6b44bdf9f653.png">

Summary:

In this project, I used text embeddings combined with LSTM and Conv1d-based deep learning models to predict whether a movie review is positive or negative.

The dataset used contains about 9000 total movie reviews that are labeled as having either positive or negative sentiment.

Building a model to predict the sentiment of movie reviews would be practically useful for websites like Rotten Tomatoes or IMDB, which aggregate reviews from multiple sources and generate an overall rating for a film. It could also be useful as an input for a movie recommendation algorithm.

Models:

All of the models I tried performed very similarly, ranging from 78% accuracy to 81% accuracy. I tried a few LSTM-based models, some models with stacked conv1d layers, added batch normalization to one, played around with adam vs. rmsprop optimization. I tried training my own embeddings and used glove embeddings (via transfer learning). I also tried adding bidirectional LSTMs based on other top models I saw on the leaderboard. There was not a very clear jump in accuracy caused by tuning any of these hyperparameters. When I investigated the top performing models, I found that there was a good amount of variation in model architecture. Unfortunately, the highest performing model by 10% accuracy didn't have any model details submitted to the contest page. I wonder if it was based on transfer learning from a pre-trained sentiment classification model.

Ultimately, my best performing model had one LSTM layer with .4 dropout and used the pre-trained glove embedding layer. I found the dropout hyperparameter had the most noticeable effect in changing how fast the model was learning and dealing with overfitting. If I were to continue trying to refine my models, I would probably try gridsearch with different dropout ranges.

Overall I reigned supreme and came in first on average F1 score accross all models submitted.

<img width="894" alt="Screen Shot 2023-04-24 at 6 18 05 PM" src="https://user-images.githubusercontent.com/61389709/234129654-ef87aa43-c895-44ca-a9fc-fc16446842bf.png">

