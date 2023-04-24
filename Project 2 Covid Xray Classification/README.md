## Covid X-ray Classification

![download-3](https://user-images.githubusercontent.com/61389709/234124869-504782ac-8b91-4244-ac8e-308b3bc071c9.png)

Summary:

In this project, I used publicly available X-ray images of patients with covid-19, pneumonia, and healthy controls to develop a model to accurately predict disease status (covid vs. pneumonia vs. healthy). I tested various from-scratch models utilizing 2-dimensional convolutional layers as well as a transfer learning models borrowing architecture components from InceptionV3.

Models:

First I tried a basic sequential model with 10 Conv2D layers. I chose 32 filters for all Conv2D layers. I chose to train it over 14 epochs to begin with. This basic model performed actually relatively well with accuracy in the low 90s for the test data. I tried additional models that used this same sequential model as a template and changed the number of layers and filters slightly. Ultimately my best model at this stage had 15 layers total, 8 Conv2D layers all with 32 filters, and 4 max pooling layers.

Next I attempted a transfer learning model. I used the InceptionV3 model and changed the output shape to match the data. The initial model I used did not perform nearly as well as my much smaller sequential models, and I wanted to focus more on those, so I didn't try altering this model.

Next I tried adding batch normalization layers to my best sequential model. This worked very well and increased my test predicition accuracy by about 4%. My best performing model ended up with 24 layers total, 10 Conv2D layers, 6 with 32 filters and 4 with 16 filters, 4 max pooling layers, and 9 batch normalization layers. My best accuracy was about 94%.

In general, I found that models with relatively small numbers of filters and many batch normalization layers dispersed between Conv2D layers, trained over about 10-20 epochs worked best.

My best model ranked 12th on accuracy out of 451 total models submitted. Overall I came in 8th based on average F1 score accross all models submitted.

<img width="1034" alt="Screen Shot 2023-04-24 at 5 37 25 PM" src="https://user-images.githubusercontent.com/61389709/234124916-e729a5c2-c4cc-4a50-a26b-9fa7284ba55f.png">

I did however manage to achieve high F1 scores with very few parameters in my models compared to other competitors:

<img width="1021" alt="download-4" src="https://user-images.githubusercontent.com/61389709/234125135-87635f6a-7910-4b46-8166-d46fec16908c.png">

For this competition there seems to be an optimal depth for models of about 34 layers to get best F1 score:

<img width="1027" alt="Screen Shot 2023-04-24 at 5 41 05 PM" src="https://user-images.githubusercontent.com/61389709/234125178-20c0bed1-227e-4cd6-8c0f-fb14745e0b58.png">
