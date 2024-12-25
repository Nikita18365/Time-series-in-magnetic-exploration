# Time-series-in-magnetic-exploration
Forecasting the time series of measurements of the magnetovariation station at the Alexander Practice base

In order to perform the task of predicting the time series of magnetometric measurements from a variation station (MVS), it is necessary to analyze the available data. 

Qualitative behavior of the magnetic field in the work area: in the morning and evening, geomagnetic activity is minimal and corresponds to the level of the normal magnetic field, the peak of activity is reached at lunchtime (at 13:00-16:00). The amplitudes of anomalies can reach up to 30 NT, and in magnetic storms up to 100 NT.

Among the available data, there are recordings from the MVS for 2 days and the qualitative behavior of the magnetovariance field. We will use the ExponentialSmoothing model as a forecasting model.

Model options:

**ARIMA** (Autoregressive Integrated Moving Average):

Advantages: ARIMA is a powerful and flexible model that can capture both autoregressive (AR) and moving average (MA) components. Suitable for stationary time series.

Disadvantages: ARIMA requires a sufficient amount of data for a good estimate of the parameters. 2 days may not be enough for an accurate assessment. ARIMA also assumes stationarity.

Application: You can try, but it may not be the optimal choice due to the short data period. 

**SARIMAN** (Seasonal ARIMA):

Advantages: SARIMA extends ARIMA to account for seasonal patterns.

Disadvantages: SARIMA requires even more data than ARIMA to evaluate seasonal components, which is not suitable for 2 days of data.

Application: Not suitable for a short period of time.

**Exponential Smoothing (ES)**:

Advantages: ES is a simple and effective model for short-term forecasts, especially for trend or seasonal data.

Disadvantages: ES may not be very good at handling data where there are drastic changes.

Application: A good candidate for our case. Models like Holt-Winters are suitable if there are trends or seasonality.

**Simple neural networks** (MLP, RNN, LSTM):

Advantages: Neural networks can capture complex nonlinear patterns.

Disadvantages: Neural networks require a lot of data for training. In our case, 2 days is not enough.

Application: Not recommended for small amounts of data.

**Machine learning models with features (Feature-Based Machine Learning)**:

Advantages: You can create time-based features (hour, day of the week, etc.) and use them to train models (for example, Random Forest, Gradient Boosting).

Disadvantages: More work is needed to create the features.

Application: It is possible, but the creation of features takes a very long time.

**The Prophet Model (from Facebook)**:
Advantages: Prophet is designed to predict time series with trends and seasonality and is resilient to missing data and outliers.
Disadvantages: It may be less effective for very short time series.
Application: It can be considered if the data is seasonal.

The magnetometer recorded data on magnetic field variations for three days, including the following attributes: date, time, and magnetic field value in nanotesles (nTl). 

It is necessary to build a model that would predict the behavior of the magnetic field on the fourth day, based on the observed patterns and trends over the previous three days. To do this, first of all, preliminary data processing should be carried out, which includes checking for omissions, anomalies and outliers. After that, the data should be prepared for time series analysis, namely grouped
