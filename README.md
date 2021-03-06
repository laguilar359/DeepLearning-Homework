# LSTM_Stock_Predictor

![deep-learning.jpg](Resources/DeepLearning.jpeg)

In this project, we will use deep learning recurrent neural networks to model bitcoin closing prices. One model will use the FNG indicators to predict the closing price while the second model will use a window of closing prices to predict the nth closing price.

Project Approach:
1. [Prepare the data for training and testing](#prepare-the-data-for-training-and-testing)
2. [Build and train custom LSTM RNNs](#build-and-train-custom-lstm-rnns)
3. [Evaluate the performance of each model](#evaluate-the-performance-of-each-model)

- - -
### Prepare the data for training and testing

1. We will slice the data using the window of time function for the n day window.
2. For the Fear and Greed model, We will use the FNG values to try and predict the closing price. 
3. For the closing price model, We will use previous closing prices to try and predict the next closing price.
4. We will use  70% of the data for training and 30% of the data for testing in each model
5. using MinMaxScaler we will scale X and y values for the model.
6. Finally, reshape the X_train and X_test values to fit the model's requirement of samples, time steps, and features. 
(*example:* `X_train = X_train.reshape((X_train.shape[0], X_train.shape[1], 1))`)

### Build and train custom LSTM RNNs

In the Jupyter Notebooks, we created the same custom LSTM RNN architecture. 

* In one notebook, we fit the data using the FNG values. In the second notebook, only closing prices are used.
* In order to compare the models, we will use the same parameters and training steps for each model. 

### Evaluate the performance of each model

Finally, using the testing data to evaluate each model and compare the performance, we will answer the following:

- Which model has a lower loss?

* The model based on past closing prices has a lower loss compared to the model which predicted using FNG

- Which model tracks the actual values better over time?

* The model based on past close prices bettter tracks the actual values than predicting using FNG.

<table> <tr><td>

![Prediction using 2day window close prices](Resources/close_2day.png) 

</td><td>


![Prediction using 2day FNG window](Resources/FNG_2.png) 

</td></tr> </table>


- Which window size works best for the model?
* The 2-day window size gave a better closing price prediction. <br>

Price Predictions using closing prices across different time windows


![Prediction using 2day window close prices](Resources/close_2day.png) 


![Prediction using 5day window close prices](Resources/close_5day.png) 


![Prediction using 10day window close prices](Resources/close_10day.png)


![Prediction using 20day window close prices](Resources/close_20day.png)



* Price Prediction using FNG index over different time windows 

![Prediction using 10day FNG window](Resources/FNG_20.png) 


![Prediction using 20day FNG window](Resources/FNG_10day.png) 


![Prediction using 5day FNG window](Resources/FNG_5.png)


![Prediction using 2day FNG window](Resources/FNG_2.png) 

- - -

