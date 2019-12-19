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
Closing flag: if the store is closed, open or not yet listed on AIR system
Thanks to https://www.kaggle.com/huntermcgushion/rrv-weather-data , we can incorporate weather data
Also we did certain statistical features:
1. Average number of visitors by store 6, 7, 8, and 9 weeks ago
2. Average number of visitors by genre 6, 7, 8, and 9 weeks ago
3. Average number of visitors by area 6, 7, 8, and 9 weeks ago
4. Standard deviation of visitors by store 6, 7, 8, and 9 weeks ago
5. Standard deviation of visitors by genre 6, 7, 8, and 9 weeks ago
6. Standard deviation of visitors by area 6, 7, 8, and 9 weeks ago

## Model Detail
![Model Structure](https://github.com/Jiejanet/Seq2Seq-for-times-series-prediction/blob/master/Model%20Structure.png)
![Train and Validation Split](https://github.com/Jiejanet/Seq2Seq-for-times-series-prediction/blob/master/Train%20and%20validation%20split.png)

## File Description
DataCleaning_1120.ipynb:


