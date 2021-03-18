# TimeSeries Analysis
---
In the wolrd of finance, some international companies transact in different currencies to support their business. It is in the company's best interest to make the most out of these transactions by understanding the future direction of the currency's value so later they can use that money to sustain their business.


In this analysis, we test the many time-series tools that we can use to predict future movements in the value of the Japanese yen versus the U.S. dollar.

The following are the main tasks that we go through:

Time Series Forecasting

Linear Regression Modeling


## Time-Series Forecasting
In this time_series_analysis.ipynb, we first load historical Dollar-Yen exchange rate futures data and apply time series analysis and modeling to determine whether there is any predictable behavior.


1. Decomposition- using a Hodrick-Prescott Filter (Decompose the Settle price into trend and noise).

2. Forecasting Returns using an ARMA Model- ARMA: Create an ARMA model and fit it to the returns data. Note: Set the AR and MA ("p" and "q") parameters to p=2 and q=1: order=(2, 1).
Output the ARMA summary table and take note of the p-values of the lags.
Then, we plot the 5-day forecast of the forecasted returns (the results forecast from ARMA model)

3. Forecasting the Settle Price using an ARIMA Model- Output the ARIMA summary table and take note of the p-values of the lags.
Construct a 5 day forecast for the Settle Price. 

4. Forecasting Volatility with GARCH- Rather than predicting returns, we forecast near-term volatility of Japanese Yen futures returns. Being able to accurately predict volatility is extremely useful if we want to trade in derivatives or quantify our maximum loss.

Then, we use the results of the time series analysis and modeling to answer the following questions:

Q. Based on the time series analysis, would you buy the yen now? 
A. Yes, because based on the forecast the final plot clearly shows us that the yen is in an upward trajectory.

Q. Is the risk of the yen expected to increase or decrease? 
A. Yes it is expected to increase as the trend goes up because in the initial price plot the yen was already slightly increasing.

Q. Based on the model evaluation, would you feel confident in using these models for trading? 
A. Yes, because this upward trend forecast is short term and there is higher chance it'll be accurate considering the historical data. 


## Linear Regression Forecasting
In this analysis, we build a Scikit-Learn linear regression model to predict Yen futures ("settle") returns with lagged Yen futures returns and categorical calendar seasonal effects (e.g., day-of-week or week-of-year seasonal effects).

Data Preparation (Creating Returns and Lagged Returns and splitting the data into training and testing data)
Fitting a Linear Regression Model.
Making predictions using the testing data.
Out-of-sample performance.
In-sample performance.

Use the results of the linear regression analysis and modeling to answer the following question:

Q. Does this model perform better or worse on out-of-sample data compared to in-sample data?
A. Comparatively, if we look at the Root Mean Squared Error (RMSE) then the out-of-sample data is performs better as it has a lower score of .42 vs .57. As the lower the RMSE, the better fit the model is. 
