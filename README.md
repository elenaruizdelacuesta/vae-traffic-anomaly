Link for the traffic accidents by date in LA:
https://data.lacity.org/Public-Safety/Traffic-Accidents-by-date/2mzm-av8t


NOTES: 
DATA VISUALIZATION
we can consider drawing 10 sensors with the highest number of anomalies and plot the time series per each and try to identify if in each time series occured an accident
+
we plot a map with the same sensors with the highest number of anomalies OVER A TIME WINDOW(day, hour, month...) + incidents in this area within this time window 
+
we plot the days when more anomalies occured , again to see if our model is able to spot anomalies happenign big events too. (+ table with special and normal days, to discriminate between anomalies: anomalies that are not incidents, trying to give sense) 

ELENA: 
/traffic dataset: instead of feeding shuffled inputs to the model, try to use sliding windows. 

MARTA:
LSTM over CVAE 
