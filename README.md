# CNN-LSTM-Image-Capture-Generator
Project: Image Caption Generator with CNN &amp; LTSM

This is a final project in one of my course: Machine Learning - CSBU014.M11.KHBC (06/09/2021 - 13/11/2021)

## Overview
The goal of our project is to capture the meanings of images and express them in the form of natural languages that the user desires. 

We built an image caption generator model by merging deep learning methods of CNN (Convolutional Neural Networks) and RNN (Recurrent Neural Network). 
Xception, a CNN model trained on the imagenet dataset, is used to extract features from images. The information obtained from CNN is then used by LSTM to generate an image description. 
For training the model, we used the Flickr8K dataset. It is composed of 8000 different images, each of which will be mapped to five different sentences that describe the image.

## Dataset
Each image in the Flickr8k dataset is associated with five different descriptions that describe the entities and events shown in the image. The dataset captures some of the linguistic variability that can be used to describe the same image by connecting each image with different, independently produced words. 

![image](https://user-images.githubusercontent.com/81853079/147538890-07307d24-e00f-4921-9757-6b68f874d74b.png)

## Problem Approach
In this project, we used an encoder-decoder model to solve the problem. Here, the encoder model will give the decoder both the encoded form of the image and the encoded form of the text caption. CNN is used as the 'image model' and RNN/LSTM as the 'language model' to encode text sequences of variable lengths. This helped us to train the part of the neural network that handles images and the part that handles language separately, using images and sentences from different training sets. To make a final prediction, the vectors generated from both encodings are merged and processed by a dense layer. 

![image](https://user-images.githubusercontent.com/81853079/147538237-4e7f5102-dc2d-4cb5-87f3-155ec75350e9.png)

To extract features from images, we made use of transfer learning. There are a lot of models that we can use like VGG-16, InceptionV3, ResNet, etc. Here, we used the Xception model which has been trained on the ImageNet dataset that had 1000 different classes to classify.
To encode our text sequence, we mapped every word of the vocabulary with a unique index value. This mapping will be done in a separate layer after the input layer called the embedding layer.

## Results
After training the model for 20 epochs, we had a training loss of 2.38, as shown in Fig. 6. For testing the model, we used some images from both the training set and testing set.

![image](https://user-images.githubusercontent.com/81853079/147538465-25a8a07e-b782-4c3c-9577-8104d8eab639.png)

![image](https://user-images.githubusercontent.com/81853079/147538473-590d4d30-9c53-4a94-9449-4b59c77410a3.png)

![image](https://user-images.githubusercontent.com/81853079/147538477-8ed350f3-42f3-4ffa-9498-8c161fab2d30.png)

## More Information
We used Jupyter Notebook & Google Colab to implement this project. If you want to know more about our project, you can see our source code and report here:
https://drive.google.com/drive/folders/1LqRFo_B7OftkX5awgvpVuwLrVpzlt77W?usp=sharing
