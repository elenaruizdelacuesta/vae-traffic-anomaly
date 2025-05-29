Link for the traffic incidents by date in LA: 
https://data.lacity.org/Public-Safety/Traffic-Accidents-by-date/2mzm-av8t


NOTES: 

DATA VISUALIZATION 

We can plot THE TIME SERIES FOR EACH among e.g. 10 sensors with the highest number of anomalies, to try identifying if detected anomalies correspond to incidents actually occurred (real incidents dataset available in this repo on master node) 

We can plot A MAP with 
  * e.g the 10 sensors with the highest number of anomalies (a sum of spotted anomalies, MSE over the threshold) over a CERTAIN TIME WINDOW(hour, day, month...) 
  * AND the localization of incidents occured within the same area in the same time window, again to evaluate the capacity of the model to spot traffic anomalies caused by incidents

We can try to discriminate among anomalies, taking into account special festivities/events (falgging days as special or normal), again to try giving a sense, ok the model is spotting anomalies, but understendably not all are related to incidents. We can justify by saying that would be good to collect more variables beyond speed data only.

ELENA: 

/traffic dataset: instead of feeding shuffled inputs to the model, try to use sliding windows. 

MARTA:

implement LSTM over CVAE 
