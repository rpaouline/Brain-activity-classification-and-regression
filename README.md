# Brain-activity-classification-and-regression
This capston project consists of two parts: classification of brain activity images from EEG and prediction of time-series from MRI.

## Classification of brain activity from electroencephalograph (EEG)
Electroencephalography is an electrophysiological monitoring method to record electrical activity of the brain. It is typically noninvasive, with the electrodes placed along the scalp. EEG has several tens of electrods (or sensors).
![](images/fig1_small.png)

Raw EEG is N time series, where N is a number of electrods.

![](images/fig2.jpg)

![](images/eeg_alpha1_small.jpg)

If we split every time series into blocks of several seconds and then depict all this signals on a map of the head we can see such pictures:

![](images/noise_small.png)
![](images/not_noise_small.png)