
# Time Series Forecasting

Time is an amazing factor. A little baby can grow up over the time, Weather changes over the time, Stock prices changes over the time as well.

Time Series Data:  Data that change over the time is known as Time series data.
eg: stock prices, sales growth,etc...


### From a mathematical standpoints we can present time series data in three ways.
![arima1](https://user-images.githubusercontent.com/67855083/151524944-e23b5dc7-1ad1-40d6-b466-cdf66925b24a.png)


### 1)Auto Regressive(AR):
 Auto Regressive model which believed that Rome was not built on one day.The data values at the current spot is built on top of the data values at the previous time spots.
for eg: Todays stock price is built on the stock prices in previous days.

if we use the Auto Regressive model  to analyze a time series data. Our job is to identify the how many days we need to look back in order to forecast the current value.

what should be the value for the coefficients like beta 0,beta 1, beta 2 ...

### 2)Moving Average(MR):

Moving Average model believed that the current value is a result from previous unexpected events.
for eg: the current stock price is a result of unexpected events like US election results, covid-19 pandemic, a better sales revenue, the ceo change of the company and so on.

if we use the Moving Average model  to analyze a time series data. Our job is to identify the how many unexpected events we need to look back in order to forecast the current value.

what should be the value for the coefficients like theta 0,theta 1, theta 2 ...

### 3)Auto Regressive Moving Average(ARMA):

Both Above two models have valid points to forecast current value. so why don't we use both models together.

Then this model is the combination of Auto Regressive and Moving Average models.


# Stationary Data Assumption
No matter which model you use, the first step is to make sure the time series data follows the stationary data assumption.

This stationary data Assumption believed that time series data should have a constant mean and constant variance. The constant mean and constant variance should be the same through out the entire time series.

![Arima2](https://user-images.githubusercontent.com/67855083/151528984-5e66847e-0147-4832-ae8d-1aad16403dd4.png)

No matter where you choose the time period either future or present forecasting, the first step is draw the given time series data on plots to visualize whether time series data follows a stationary data assumption or not. 

The time series should be pretty flat or the data values should change around a central value as you can see in above picture.

if we see the Above chart in the picture, it is a non-stationary chart because it has a trends which follows decreasing or increasing in the plot chart.
The randomly choosen time period like P1 and P2 data mean values are not same if we compare,so it is a non-stationary.

# Differencing
So, when we face a non-stationary data, we have a technique to transform into stationary data. simply means subtracting previous values to current values.

![arima3](https://user-images.githubusercontent.com/67855083/151534055-c67cae29-23fa-4a7f-99ee-043948636c64.png)

### One lag Differencing: 
it is subtracting current values with a one step previous value like shown in the picture.

after performing one lag differencing, it is denoted as one star on X variabe like in the picture.
### One lag differencing twice:
it is performing one lag differencing twice times, which is like you are applying one lag differencing on X star values in the picture again to the x double star.

![arima4](https://user-images.githubusercontent.com/67855083/151534689-a27ce0a0-24fa-40b5-9d06-3e5b47c71c9d.png)

### Two lag differencing:
Two lag differencing means subtracting the current value with two steps back of previous values like in the given below picture.

![arima5](https://user-images.githubusercontent.com/67855083/151535578-b70f57b3-1428-43b0-a683-96c82d678aad.png)


Note:  Multi lag differencing is used mostly for the purpose of the Processing Seasonal Data's.

# ACF AND PACF
Acf and Pacf help us to decide which one to choose between AR and MA models that we should analyze time series data for how many days we need to look back in order to predict the current value.

![arima6](https://user-images.githubusercontent.com/67855083/151576370-d0762189-5765-4afb-bd2b-4632ed85dfbf.png)
  
  - Acf is a factor that  measures the correlation between the current value and the value at previous times like today and yesterday stock prices how strong those two days are correlated
  - pacf help us to measure the real correlation between the two time spots by taking out the influence of other time spots.

  - Pacf is a factor that measures the correlation between the two days but we also consider the influence of  other days  on this two days. Actually we can use ACF to calculate today's and yesterday's stock prices but don't forget that today's stock price is dependent on day before yesterday and yesterday stock price also dependent on day before yesterday, so there is a influence of day before yesterday on this ACF if we measures.

  - if we want to measure the  real correlation between today's and yesterday's we need to take out the influence of day before yesterday's 
  - pacf help us to measure the real correlation between the today and yesterday stock prices by taking out the influence of day before yesterday .
  - In practice, we use a PACF factor to evaluate the error model of Auto Regressive(AR) model which we need to find real correaltion between the two time spots.
  - We use Acf factor to evaluate the Moving Average(MR) model

![arima7](https://user-images.githubusercontent.com/67855083/151586401-5025a8e3-623c-4fc3-9e81-e08a50d873f8.png)
 
 - As we discussed we use Pacf factor to evaluate the AR model, the significant Pacf values are choosen to evaluate the AR model. 
 - Those significant Pacf values determine the order of the AR model. for example  to predict today stock price ,if the pacf values are significant on yesterday stock values then we use first order AR model. if pacf values significant on yesterday and day before yesterday then we use second order AR model to predict today's stock price using together of two previous days system prices.
 - The same rule to ACF if we find that yesterday price is significant then we should use yesterday error term to predict the current value then our model is called a first order Moving Average(MA) model.
 - since AR and MA models both can also use to predict time series analysis but when we determine the model we should look at ACF and PACF factors to decide.

![arima8](https://user-images.githubusercontent.com/67855083/151591313-88e3f7d5-5f46-4b95-9c03-e8cd92d4d9b9.png)

# Examples
 - now we get into the Acf and Pacf charts  then we decide the models between AR and MA models or ARMA combined model.
 ![arima9](https://user-images.githubusercontent.com/67855083/151591852-b8ab942a-984a-434b-a588-4cc51cda6202.png)

- The blue lines are the threshold lines of the charts to decide the significant values
- The vertical lines that exceeded the threshold lines are called significant lines in the charts.
- if you obeserve carefully picture,we can see the many significant lines in the ACF chart and two significant lines in the PACF chart.
- so we use choose the simpler factor that is pacf and decide as using the second order of AR model because we only need to use the  yesterday and day before yesterday values to predict the today values as we have only two significant values.
- if we insist to use MA model then there are many significant values in the ACF chart to consider and take as that many orders of MA model which is complicated process.
![arima10](https://user-images.githubusercontent.com/67855083/151594320-fa6b3f9e-1c94-4a0d-95e4-c5365d0ee227.png)
 
 - In the picture, ACF values have one significant value and PACf values have three significant values that are exceeded the blue line of threshold line.
 - if we use AR model from PACF significant values then we need to consider the yesterday, day before yesterday and three days back value as the order of AR model which is complicated and we know that we always need to switch to the simpler one.
 - Whereas if we use MA model then we take error term of only yesterday value to predict the today values so we use this MA model.

![arima11](https://user-images.githubusercontent.com/67855083/151596231-38e0e022-a0ff-4256-80ab-dbbbe1244505.png)

 - In this picture, there are three significant values on the pacf chart and many significant values on the acf chart.
 - so we can consider as the third order of AR model or (the first order of AR model and first order of MA model) because yesterday value and error term of yesterday are both important to predict today stock price.
 - we can choose either first method or second method, infact using second method is more prefarable as we can use two independent variables to predict the current value unlike the first method of three dependent significant values for third order of AR model.
 
# ARIMA(I for Integrated):
Integrated is a term represents the times you applied the differencing to detrend the non-stationary data and transform to stationary data to eligible for the stationary data assumption.
![arima12](https://user-images.githubusercontent.com/67855083/151598404-41f91969-1f60-4259-bba4-899e75f1b5df.png)

 - When you apply the differencing to the dataset and after that you find the ACF and PACF are non-significant values  then this dataset is called a random walk dataset and you cannot use arima model to this dataset. so you have to consider the another model technique for this type of datasets.



  Note: 

    from the time series data plot you get the stationary or non stationary data, the same way after applying statsmodel.acf/pacf within required 'n' lags we get the ACF and PACF charts to decide the AR and MA models.
     

    Also, the significant points or spikes exceeds the threshold at lag 0 should be ignored. we have to take count from lag 1.

# How to identify model from acf and pacf charts
### Rules:
 -CASE 1: If acf model spikes started in the beginning and suddenly started falling in the middle of the zero line,At the same time unlike acf there are only one or two spikes in the beginnig of pacf charts.
   Then you have to consider the AR1 or AR2 model as from the no. of significant lines in the pacf chart.

![arima](https://user-images.githubusercontent.com/67855083/151668416-722565c5-6462-418a-9290-9a2e87b2cf27.png)
 
 -CASE 2: If there are any wave like spikes or significant lines in the acf chart and at the same time having 1 or 2 significant lines in the beginning of pacf chart tells us to consider AR model only. 
 - The order of AR model depends on the no. of significant lines from lag 1 in the pacf chart either positively or negatively no matter what.

 ![arima1](https://user-images.githubusercontent.com/67855083/151668500-6bb404d5-f054-48cf-9389-32e7746b260b.png)

 -CASE 3: If the spikes in the pacf chart in the baginning either positively or negatively and decreasing suddenly to the zero of the middle line, at the same time having one or two spikes in the beginning of acf chart.
 - Then we need to use MA model and degree depends on the no. of spikes on acf chart
 ![arima2](https://user-images.githubusercontent.com/67855083/151668654-1bb28d2d-8562-4001-9f82-c4dfbf5d2c98.png)

-CASE 4: Sometime there are lots of spikes in both acf and pacf charts either suddenly decreasing to zero of the middle line or wave like formed spikes, so then we need to choose the ARMA 1 model.
- Because there might be lot of options but it makes model complication, so better to choose ARMA model with 1 degree.
![arima4](https://user-images.githubusercontent.com/67855083/151668823-060565be-5ee7-49e6-8ac9-708c81129f8d.png)


# Seasonal ACF and PACF (sarima)
 
 Seasonal data shows us in the plot chart of time series analysis like increasing and decreasing in Seasonal ways.
 for example sales of ceiling fans in the summer increases and decreases in winter.This might repeat several times and called as Seasonal chart.

 The signal data consists two types either non-Seasonal which increases or decreases the trend constantly and seasonality which changes in the trend with seasonal cycles like suddden increase and decrease of signal data.


 - In non-Seasonal we have parameters like p,d,q for AR,differencing,MA 
 - In Seasonal we having upper case parameters P,D,Q,S  for AR,differencing,MA and repeated months pattern for seasonality.

![arima5](https://user-images.githubusercontent.com/67855083/151669809-b0650762-7192-4948-9f9d-7637599a7a63.png)

# how to identify seasonal models from acf and pacf

Rule: Fewer repeated significant lines or spikes after the excluded beginning spike 

## Example 1:
- obeserve carefully that for non-seasonal we use MA1 model from case 3 statement.
- for seasonal determination, we need to check fewer no. of times repeated spikes excluding the beginning spike.
- so here, ACF has fewer no. of repeated spikes compared to the pacf chart so we go ahead with again MA 1 model only. why degree only 1 because there is a repeated spike at 11th and 12th lags together at one place, so considered as 1 degree only.
- the picture is given below
![arima6](https://user-images.githubusercontent.com/67855083/151670272-c03fb1a2-1837-47bd-b87b-8899760b235a.png)

## Example 2:

-  you can have the same exapmle picture but with one more repeated spike after the beginning spike in acf. 
- so totally two more repeated spikes at acf chart after the exceptional or excluded beginning spike in the chart.
- then we need to use MA 2 model with (P=0,D,Q=2),S=12. 
- the picture is given below
![arima7](https://user-images.githubusercontent.com/67855083/151670363-f7d95a45-1d94-41e2-9be3-c4bc5e71d29a.png)

- In the bottom picture given, we can obeserve the Case 1 observation for non-seasonal data so choose the pacf chart and go ahead with AR 1 model only
- But for non-seasonal data, we choose the acf chart becuase of fewer repeated spikes and decides to pick the MA 1 model.
- why MA 1 degree model when there are two repeated spikes in the acf chart after the beginning spike because the second spikes 25 th or 26 th are very marginally and negligible.
- so to reduce complication we can choose first order of the MA model in the seasonal data.
-  the picture is given below
![arima8](https://user-images.githubusercontent.com/67855083/151670523-6280c56a-7a1f-43b2-9c33-d91bdd6a4e6f.png)

### Note: Remember that in non-seasonal data, we consider the beginning spikes mostly, but in seasonal data we exclude the beginning spikes



# Project:

## 1)import packages and hanling data in pandas
 - Imported required packages and loaded the data with pandas
 - check the features datatypes and convert the timeframe column from object to datetime type as keeping it as index column

## 2) check for stationary
 - plot the timeseries data and check whether it's stationary or non-stationary
 - To check stationary write a function for test stationarity which containing of essential processes:
    
       --> To determine the rolling statistics
       --> Plotting the rolling statistics
       --> Use adfuller to get summary of statistics

## 3) Making Timeseries Stationary

 ### Estimating and Eliminating trends
  - Applying the np.log(Timeseries),for smoothing you can add rolling.mean which is  moving Average
  - Method1: Use differencing in order to make stationary( the ts.log and moving average(taken has rolling.window = 12))  
  - Method2: Alternate way instead of moving average, use exponentially weighted average(halflife=12).mean() and differencing from ts.log
  - Method3: For Eliminating trends and seasonality,  Use ts.log.shift(which shifts one value to next one) aand differencing from ts.log  
  - Method5: Decomposition Using Seasonal decompose packages, get the Plots of original data, trends, seasonal, residuals. The residuals are the required Decompositioned chart to make stationary
  - Note: All the above methods are verified for the best stationary assumption through Test stationarity function only.


## 4) Forecasting Timeseries 

### ACF and PACF
- plot the acf and pacf charts and decide the best model for the forecasting.
- I have checked generally with three models of AR,MA and ARIMA methods
- I have considered ARIMA model and forecasted with resuls_arima.plot_predict(1,'no. of months') with visualizations
- For numpy values , you can get by resuls_arima.forecast(step='no. of months')
- This is additional , To convert original scale 

    --> Take results of final model like results_arima and fit in to series with fittedvalues which is called as predictions_arima_diff

    --> a) Predictions_arima_diff_cumsum is created with cumsum function to the predictions_arima_diff

    --> b) define predictions_arima_log  with creating Series of ts_log.iloc[0] values by fittedvalues

    --> Again predictions_arima_log is assigned to fill the first month 'nan' value with adding a) predictions_arima_log and b)  Predictions_arima_diff_cumsum, This is done by fill_value =0 
    
    --> create plot of ts_log and predictions_arima_log

    --> scale down the predictions_arima_log to predictions_arima by np.exp function and plot the ts and pridictions_arima


# how to check or validate test stationarity values
 - Check P-value if it is lesser than 0.5 or Not. Because lesser than 0.5 value tells us it is stationary value data
 - Check Test statistics values whether they are equal or near to the any one of the critical values of 1,5,10 %
 
