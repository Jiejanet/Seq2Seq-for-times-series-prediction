# Seq2Seq-for-times-series-prediction
Implementation of Seq2Seq model on time series prediction of restaurant visitor traffic
## Data Source
The data comes from a past Kaggle competition for predicting 39 days of restaurant traffic in 39 days.
https://www.kaggle.com/c/recruit-restaurant-visitor-forecasting/overview

## Approach Brief
Several algorithm is implemented: logistic regression,  KNN, gradient boosting, Seq2Seq. Gradient Boosting top crowns the performance, Seq2Seq ranks the last.
![Model Performance Comparison](https://github.com/Jiejanet/Seq2Seq-for-times-series-prediction/blob/master/Model%20Performance.png)
The gradient boosting method has already been elaborated by many Kaggle Notebooks, so this repository only dedicated to showcase how to do Seq2Seq modeling, especially a multi-timesteps, multi-dimensional feature

Seq2Seq refers to the sequence-to-sequence architecture of the neural network fit. This architecture enables mapping arbitrary length sequences to other arbitrary length sequences. This ability helps Seq2Seq shine in performing many tasks including language translation, image captioning, and time series prediction. RNN’s ability to successfully learn from data with long range temporal dependencies makes it a natural choice for time series prediction. 

## Feture Engineering
Weather data was added in, thanks to https://www.kaggle.com/huntermcgushion/rrv-weather-data 

## Model Performance



## File Description


