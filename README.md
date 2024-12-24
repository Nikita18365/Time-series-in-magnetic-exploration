# Time-series-in-magnetic-exploration
Forecasting the time series of measurements of the magnetovariation station at the Alexander Practice base

In order to perform the task of predicting the time series of magnetometric measurements from a variation station (MVS), it is necessary to analyze the available data. 

Qualitative behavior of the magnetic field in the work area: in the morning and evening, geomagnetic activity is minimal and corresponds to the level of the normal magnetic field, the peak of activity is reached at lunchtime (at 13:00-16:00). The amplitudes of anomalies can reach up to 30 NT, and in magnetic storms up to 100 NT.

Among the available data, there are recordings from the MVS for 3 days and the qualitative behavior of the magnetovariance field. We will use the ARIMA model as a forecasting model. 

The magnetometer recorded data on magnetic field variations for three days, including the following attributes: date, time, and magnetic field value in nanotesles (nTl). 

It is necessary to build a model that would predict the behavior of the magnetic field on the fourth day, based on the observed patterns and trends over the previous three days. To do this, first of all, preliminary data processing should be carried out, which includes checking for omissions, anomalies and outliers. After that, the data should be prepared for time series analysis, namely grouped
