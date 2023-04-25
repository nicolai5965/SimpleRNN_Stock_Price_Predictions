# Project Title: Stock Price Prediction with Custom RNN
# Overview
This project demonstrates the implementation of a custom RNN (Recurrent Neural Network) for predicting stock prices using historical stock data. The model is built using TensorFlow and Keras, with custom RNN cells and layers. The performance of the model is evaluated using various metrics such as MAE, RMSE, MAPE, and Directional Accuracy.

# Data Preparation
* Historical hourly stock data for NVIDIA (NVDA) is fetched using the yfinance library.
* Data is fetched hourly for each 7-day interval, resulting in a finer granularity of stock price movements.
* The dataset is cleaned to remove any duplicate entries.
* The 'Adj Close' column is dropped as it represents future information.
* Relevant features are selected: 'Open', 'High', 'Low', 'Close', and 'Volume'.
* The 'Close' column is used as the target, and it is removed from the input features when creating sequences.
* The remaining data is normalized using MinMaxScaler from the sklearn library.

# Feature Engineering
* Input sequences with multiple features are created for feeding the RNN model. Each sequence has a length of 60 timesteps.
* The dataset is split into training (80%) and test (20%) sets.
# Custom RNN Implementation
* A custom RNN cell, SimpleRNNCell, is created by subclassing the Layer class from TensorFlow. The cell contains the necessary weight matrices, bias terms, and the     call() method for the RNN computation.
* A custom RNN layer, SimpleRNN, is created by subclassing the Layer class from TensorFlow. The layer takes the custom RNN cell as input and processes the input      sequence.

# Model Building
* A simple RNN model is built using the custom RNN cell and layer. The model consists of a single RNN layer followed by a Dense output layer.
* The model is compiled with the 'adam' optimizer and 'mean_squared_error' loss function.

# Training and Evaluation
* The model is trained for 100 epochs with a batch size of 32 and a validation split of 20%.
* The training and validation loss curves are plotted.
* The model is evaluated on the test set using metrics such as MAE, RMSE, MAPE, and Directional Accuracy.

# Results Visualization
* The actual and predicted stock prices (normalized and unnormalized) are plotted to visually assess the model's performance.

# Conclusion
The custom RNN model serves as a proof of concept for predicting stock prices using historical data. The model's performance can be further improved by tuning the hyperparameters, using more advanced RNN architectures like LSTM or GRU, or incorporating additional features and external data sources. 
