# Seq2Seq-for-times-series-prediction
Implementation of Seq2Seq model on time series prediction of restaurant visitor traffic
## Data Source
The data comes from a past Kaggle competition for predicting 39 days of restaurant traffic in 39 days.
https://www.kaggle.com/c/recruit-restaurant-visitor-forecasting/overview

## Approach Brief
Several algorithms are implemented: logistic regression,  KNN, gradient boosting, Seq2Seq. Gradient Boosting top crowns the performance, Seq2Seq ranks the last.
![Model Performance Comparison](https://github.com/Jiejanet/Seq2Seq-for-times-series-prediction/blob/master/Model%20Performance.png)
The gradient boosting method has already been elaborated by many Kaggle Notebooks, so this repository only dedicated to showcase how to do Seq2Seq with multi-timesteps, multi-dimensional features 

Seq2Seq refers to the sequence-to-sequence architecture of the neural network fit. This architecture enables mapping arbitrary length sequences to other arbitrary length sequences. This ability helps Seq2Seq shine in performing many tasks including language translation, image captioning, and time series prediction. RNN’s ability to successfully learn from data with long range temporal dependencies makes it a natural choice for time series prediction. 

## Feture Engineering
Closing flag: if the store is closed, open or not yet listed on AIR system
Thanks to https://www.kaggle.com/huntermcgushion/rrv-weather-data , we can incorporate weather data
Also we did certain statistical features:
1. Average number of visitors by store 6, 7, 8, and 9 weeks ago
2. Average number of visitors by genre 6, 7, 8, and 9 weeks ago
3. Average number of visitors by area 6, 7, 8, and 9 weeks ago
4. Standard deviation of visitors by store 6, 7, 8, and 9 weeks ago
5. Standard deviation of visitors by genre 6, 7, 8, and 9 weeks ago
6. Standard deviation of visitors by area 6, 7, 8, and 9 weeks ago

date and time features:
1. day of week
2. holiday flag
3. month/year/day
etc...

Geo location:
1. longitude and latitude
2. area name

Restaurant features:
1. genre name
2. reservation numbers
3. visitors number

## Model Detail
![Model Structure](https://github.com/Jiejanet/Seq2Seq-for-times-series-prediction/blob/master/Model%20Structure.png)
The Seq2Seq architecture is comprised of two parts, an encoder and a decoder. I designed an encoder which looks into 400 days of historical data and a decoder to predict 39 days of future visitor traffic. I throw in restaurant features, geo location, weather feature, statistical features, date and time features to the encoder, with the intention that it would pick up patterns embedded within the sequential 400 days’ worth of data. The decoder was fed stationary information(features that can be known ahead of prediction period) about the 39 upcoming days, such as flags for holidays, area, and genre.

Categorical data was one-hot encoded (area name, genre name, except for restaurant id) and all numeric data were scaled down to [-1, 1] 

![Train and Validation Split](https://github.com/Jiejanet/Seq2Seq-for-times-series-prediction/blob/master/Train%20and%20validation%20split.png)
Data from January 1st, 2016 to March 14th, 2017 was used for training and data from February 9th, 2016 to April 22nd, 2017 was used as a validation set.

## File Description
DataCleaning_1120.ipynb: Merge separate files together and created a closing flag feature. (Does not include weather and statistical features)
Seq2Seq_master.ipynb: Implementation of Seq2Seq model


## Possible Improvement for Seq2Seq
1. Bring in inferential model during prediction period.
During training the Seq2Seq model, I tried different hyperparameters(learning rate, drop out rate etc) and model architecture(number of neurons, number of LSTM layers), but the validation loss stagnated after certain epochs. This looks to me indicate a obvious flaw in the model I found most of the prediction that Seq2Seq made range around 7-20 visitors per day. This is such a bad generalization 

2. 

