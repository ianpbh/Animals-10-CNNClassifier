# Animals Classification CNN

## Introduction
This project was created to fit a Convolutional Neural Network to make predictions of animals species. The model is fitted using the (Animals-10)[https://www.kaggle.com/datasets/alessiocorrado99/animals10], which consists of 10 classes, about 28K images.

## How to run the project:
1. Create the "checkpoints" and "dataset" folders inside the project's root directory. 
2. Download the (dataset)[https://www.kaggle.com/datasets/alessiocorrado99/animals10] and extract into the just created "dataset" folder.
3. Run "AnimalsSpecies_CNN_classifier" notebook to preprocess the data and fit the model (more info about architecture below).
4. To make single predictions, place your image under the project's root folder, open "AnimalsCNNClassifier_singlePredict", change the image file name in code and run.

## OBS.:
Under trained_model folder there's a model created using the code within this project, it had 0.89 accuracy on the validation data.
This model is already being loaded in the "AnimalsCNNClassifier_singlePredict" notebook.

## About the model
The model is a CNN with 5 convolutional layers followed by one MaxPooling layer each, a Flatten layer and then a Dense layer of 512 neurons, before the output.

It also relies on Data Augmentation to improve it's accuracy, since there's not enough samples on each class.

The model has callbacks to save checkpoints (which also is needed if you want to make single predictions), and early stopping to stop training when a monitored metric has stopped improving. It also relies on a dropout layer to reduce overfitting.