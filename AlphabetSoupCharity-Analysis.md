# Analysis Alphabet Soup Charity - Neural Network

## Overview
Tasked to design and build a binary classification model to use as a tool to analyze funding applications for Alphabet Soup Charity.  Utilizing metadata provided in a dataset containing over 34,000 organizations that have received funding from Alphabet Soup a deep learning model was created and multiple optimization attempts made to analyze and predict the success of future applicants based on the provided dataset. 


## **Model Setup and Outcomes**

## Initial Model
Consisted of two layers:

**First layer:**  Neurons = 80
Activation Function: ReLu

**Second layer:**  Neurons = 30

**Activation Function:** ReLu

**Output layer:** Sigmoid

**Epochs:** 100

**Performance Accuracy Results: 72.92%**

## **Optimization Attempt - 1**

1. Model Architecture Changes:
- Increased the first hidden layer from 80 to 120 neurons
- Increased the second hidden layer from 30 to 60 neurons
- Added a third hidden layer with 30 neurons
- Added dropout layers (0.2) after the first and second hidden layers to prevent overfitting
- Added validation_split=0.2 to monitor model performance during training
- Set batch_size=32 for more stable training

2. Training Improvements:
- Added validation split to monitor model performance
- Kept the same number of epochs (100) but with better monitoring
- Maintained the same optimizer (adam) and loss function (binary_crossentropy)

**Performance Accuracy Results: 72.90%**

## **Optimization Attempt - 2**

1. Model Architecture Changes:
- Increased first hidden layer to 160 neurons
- Added a fourth hidden layer
- Used a pyramid structure (160→80→40→20→1)
- Increased dropout rates to 0.3 for first two layers

2. Training Improvements:
- Added Early Stopping to prevent overfitting
- Added Learning Rate Reduction when model plateaus
- Increased maximum epochs to 200
- Added validation split for monitoring
- Adjusted batch size to 32

3. Optimizer Settings:
- Explicitly set learning rate to 0.001
- Added learning rate reduction when model stops improving

**Performance Accuracy Results: 72.96%**

## **Optimization Attempt - 3**

1. Model Architecture:
- Added BatchNormalization layers after each Dense layer
- Increased first layer to 200 neurons
- Simplified to three hidden layers (200→100→50→1)
- Increased dropout rates to 0.4 for first two layers
- Removed the fourth hidden layer to reduce complexity

2. Training Improvements:
- Reduced initial learning rate to 0.0005
- Increased batch size to 64 for more stable training
- Increased maximum epochs to 300
- Increased early stopping patience to 15
- More aggressive learning rate reduction (factor=0.1)

3. Batch Normalization:
- Added after each dense layer
- Helps with internal covariate shift
- Can improve training stability and speed
- May help with the vanishing gradient problem


**Performance Accuracy Results: 73.03%**

# **Summary**

I was unable to reach the required target model performance with four attempts (Initial model and three optimization runs). 

In future attempts I would design and building a new feature to look at ratio between requested amount an the requester's income. I feel like this feature and ratio may provide a predictor and opportunity for the model to learn.