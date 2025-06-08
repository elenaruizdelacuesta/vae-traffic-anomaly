Link for the traffic incidents by date in LA: 
https://data.lacity.org/Public-Safety/Traffic-Accidents-by-date/2mzm-av8t


08/06/2025
we have zero values in train and test data --> we cleaned both using the cvae model trained on raw data 
we fill with the generated samples the zero values
we use the cleaned train data to train again the cvae and obtain the predictions
we use the cleaned test set to evaluate the performance of the model in the prediction of traffic velocity
we use the raw test to calculate the anomalies 

thing to do: fix names, clean the code, check the markdown, visualization and analysis of the results
lstm+cvale...

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

---


ABOUT A POSSIBLE CLASSIFICATION OF FALSE AND TRUE POSITIVE: 

Labeling Traffic Speed Time Series for ROC-Based Anomaly Evaluation

We would like to draw a Receiver Operating Characteristic (ROC) curve to evaluate how effectively our model identifies anomalies in the traffic speed dataset. To compute true positive and false positive rates across different detection thresholds, we need ground-truth labels indicating when traffic incidents actually occurred.

**Action Required:**

1. **Incident Labeling**

   * Annotate the traffic speed time series with binary labels (anomaly vs. normal) based on the timestamps of recorded traffic incidents.

2. **Data Validation**

   * Ensure labels accurately reflect incident start and end times to minimize misclassification.
   * Rather than flagging a single timestamp, label a small window around each incident (for example, ±3 observations). This approach:

     * Accounts for pre-incident slowdowns and post-incident recoveries.
     * Reduces sensitivity to logging noise or GPS jitter.
   * **Recommendation:**

     1. Begin with a ±3-sample window.
     2. Compute ROC/AUC.
     3. Experiment with larger windows (e.g. ±5).
     4. Select the smallest window that maximizes AUC without inflating false positives.

3. **ROC Construction**

   * Once labeling is complete, compute model scores (e.g., reconstruction error) and plot the ROC curve, measuring AUC to quantify detection performance.



