# Neural Networks and Deep Learning Models


Neural Networks and Deep Learning Models using Python, tensorflow, keras, pandas and scikit learn.


## Overview of Project

In this project we made a neural network to help Beks to predict which foundations would receive funding form Alphabet Soup Charity. 

As with Machine Learning techniques, the preprocessing of the data is very important. This includes taking out features that doesn’t help us predict the target variable, binning data, encoding categorical variables, split data for training and testing, scaling continuous features, compile, train and evaluate the model. To increase the accuracy of the model some optimizations were made.

### Resources used:
-	Data Sources: charity_data.csv
-	Software: Python, tensorflow, keras, pandas and scikit learn.


## Results:

Data Preprocessing

•	What variable(s) are considered the target(s) for your model?

The target variable was IS_SUCCESSFUL, because we are trying to predict if a foundation is going to receive funding based on the information that we have from it.

•	What variable(s) are considered to be the features for your model?
The variables we used as features for the model were: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT.

•	What variable(s) are neither targets nor features, and should be removed from the input data? 
The first two variables that were removed from the analysis were "EIN" and "NAME". These variables don’t help us for the analysis and will give too many extra columns when they go through the OneHotEncoder. They were removed at the beginning.

Compiling, Training, and Evaluating the Model

•	How many neurons, layers, and activation functions did you select for your neural network model, and why?

At first 80 in the first and 30 in the second hidden layer. The first one is about the double of the input dimensions to the Neural Network and is a rule of thumb. In the second a bit less than half.

For the optimizations the parameters used were:

Optimization 1

hidden_nodes_layer1 = 80
hidden_nodes_layer2 = 30
hidden_nodes_layer3 = 20
activation="relu"
epochs=100

Optimization 2

hidden_nodes_layer1 = 80
hidden_nodes_layer2 = 40
hidden_nodes_layer3 = 20
activation="relu"
epochs=51

Optimization 3

hidden_nodes_layer1 = 80
hidden_nodes_layer2 = 40
hidden_nodes_layer3 = 20
activation="relu"
activation="tanh" in layer 2

Optimization 4

hidden_nodes_layer1 = 40
hidden_nodes_layer2 = 20
hidden_nodes_layer3 = 10
activation="relu"
epochs=100

Optimization 5

hidden_nodes_layer1 = 90
hidden_nodes_layer2 = 30
hidden_nodes_layer3 = 10
activation="relu"
epochs=50

All of them use activation="sigmoid" in the output layer.

The best results were achieved by the optimization #2



![structure of the model Optimization 2](https://user-images.githubusercontent.com/96758511/169699079-1eb89df2-a6f4-4c98-8f22-828d9a949feb.png)


Structure of the model Optimization 2




![Evaluate the model using test data](https://user-images.githubusercontent.com/96758511/169699070-ee61ac28-82d3-4865-b70d-d8ff35607079.png)


Evaluation of the model Optimization 2 using test data




•	Were you able to achieve the target model performance?


There are some checkpoints that have over 75%, like the first optimization in epoch 51:

Epoch 51: 
 55/804 [=>............................] - ETA: 3s - loss: 0.5393 - accuracy: 0.7506

Or epoch 43 in the optimization #5:

Epoch 43: 
 57/804 [=>............................] - ETA: 5s - loss: 0.5308 - accuracy: 0.7527
	
Using the weights in that checkpoints would give a model with 75% accuracy.

•	What steps did you take to try and increase model performance?
 
•	We increase the number of hidden layers to 3.
•	In some experiments we used more neurons, in other We used less. 
•	We changed the activation function of the 2 hidden layers to tanh.
•	Changed the number of epochs.


## Summary:


The results from the different models were:

Normal model: 

Loss: 0.5582124590873718, Accuracy: 0.7292128205299377

Optimizations:
1)	Loss: 0.56023770570755, Accuracy: 0.7286297082901001
2)	Loss: 0.5560038089752197, Accuracy: 0.7309620976448059
3)	Loss: 0.5616557002067566, Accuracy: 0.728863000869751
4)	Loss: 0.5547448396682739, Accuracy: 0.7308454513549805
5)	Loss: 0.5557364225387573, Accuracy: 0.7292128205299377

Using the weight in epoch 43 of the fifth optimization you have an accuracy of 75.3%

Epoch 43: 
57/804 [=>............................] - ETA: 5s - loss: 0.5308 - accuracy: 0.7527


### Other recommendations

To solve this classification problem would be to use a Random Forest in Machine learning. These techniques are very similar and could give better results. Also, with this technique we are going to see how much every feature contributes to the target. With that information we can eliminate unnecessary features in the preprocess stage. 

With time and computational power there is the possibility to make a function that changes the different inputs, to find a robust zone were the accuracy is high for a variety of similar inputs. 




