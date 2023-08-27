# Time-Series-India-GDP

## Use case of project:
The project's use case was to forecast India's GDP at a certain year, on the basis of previous year's data which was gathered from [data.gov.in](https://data.gov.in/resource/gdp-india-and-major-sectors-economy-share-each-sector-gdp-and-growth-rate-gdp-and-other).

**NOTE:** This model does not take in consideration, the sudden big spikes which are naturally caused and affects the country's economic structure in a positive or negative way. For eg: COVID-19 outbreak did pretty much damage and caused GDP to dip a certain amount irrelevant of forecasted amount

# Basics of Time-Series Analysis and working of our model:
Time Series analysis is used when we have to predict or forecast our target values in future with respect to date with the help of previous data. There are basically 4 types of patterns:

**Trend**

A trend exists when there is a long-term increase or decrease in the data. It does not have to be linear. Sometimes we will refer to a trend as “changing direction”, when it might go from an increasing trend to a decreasing trend.

## Workflow:

1) First we downloaded the data provided from government site and import all the data into dataframe. 
2) Then did pre-processing over our dataframe till we get our target feature which is ``gdp_in_cr_04``` and index as ```Financial_year``` as needed. 
3) Using Augmented-Dickey Fuller test checked if our data is stationary or not. 
4) If its not-stationary then we make it stationary by differencing it.
5) Compute AR and MA values using acf, pacf plots.
6) After that we test our model and get RMSE score, if gap between target feature's mean and RMSE is huge then model is good enough.
7) Now we fit ARIMA on whole dataset and start forecasting for future predictions. 
