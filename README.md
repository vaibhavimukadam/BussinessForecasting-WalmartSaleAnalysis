BussinessForecasting-WalmartSaleAnalysis
----

I am currently pursuing my masters in IT and Analytics at Rutgers. I am forecasting Walmart sales data for 45 retail stores on a weekly basis. 

We implemented time series on the date feature in format YYYY-MM-DD. The data set comes from Kaggle and is available at this [link](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data).
We are looking at the year forecast to consider the seasonality of the data. 
Team Members -
  - Aditya Pai: https://github.com/adityapai2 
  - Cameron Clark: https://github.com/codingcam91/codingcam91
 
Data Description 
---
Data has Weekly sales of 45 retail strores for 3 years (2010,2011,2012). Data is avaulable across different stores and its departments.  We have aggregated data of all stores to get consistently dated data for the timeseries. Data added cross Million.

Analyzing using following models -
---
  1. Naive
    Since the data is seasonal, naive does not do a fair job as we get a point forecast of 45.54412
  3. snaive
    A seasonal naive model predicts the last value of the same season (same week last year) when forecasting.(Point : 1st Forecast: 48.65554, 6th Forecast: 55.56115, 10th Forecast: 44.9554)
  5. rwf
    First point forecast 45.51449	 and MAPE of 6.356664
  6. meanf
    Here as well, we get the mean forecast of 47.11342.
  7. Holtwinters
    Point forecast for 1st Forecast: 48.32820, 6th Forecast: 56.65287, 10th Forecast: 45.10548 and MAPE of 1.932219
    Smoothing parameters --> alpha: 0.06058175, beta : 0.008479722, gamma: 0.557241
  9. Moving Averages
    Order 3
      MAPE : 0.775721 and ACF1: 0.008710816 
    Order 6
      MAPE : 0.3223557 and ACF1: 0.3467995
  
TimeSeries - 
----
We can see that the time series has seasonality. Seasonality refers to a periodic pattern, within years, that is related to the calendar day, month, quarter etc…
We can see that the time series does not appear to have a slight trend. A trend is a long run upward from the decomposed graph

Autocorrelation of the time series -
----
We can see there is a strong negative correlation from the 5th lag. We should expect this given the seasonality of the time series.
There is a strong correlation with the observation a year (52 weeks) prior, this is expected.

Acuuracy Measure - Mean absolute percentage error : 
----
Actual data is non zero, that is, the aggregated data which we are analysing does not have zero as a value in Weekly Sales.
MAPE puts a heavier penalty on negative errors than on positive errors.
We cannot use MAE and RMSE as it depends upon the scale and also it is difficult to make comparison for a different time interval.

ACF1: Autocorrelation of errors at lag 1. it is a measure of how much is the current value influenced by the previous values in a time series. It is expected that the autocorrelation function -- to fall towards 0 as points become more separated

Model - Moving Average order 3
-----
Gives the best MAPE with good ACF1 value.
Moving averages can be run at consistent interval to understand and be prepared for if there will be any influx for a particular time of the year.


---------------
[Presenatation for Insights and plots](https://github.com/vaibhavimukadam/BussinessForecasting-WalmartSaleAnalysis/blob/master/BusinessForecasting_group9.pdf)
