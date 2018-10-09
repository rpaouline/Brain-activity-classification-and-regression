# Brain-activity-classification-and-regression

This capston project consists of two parts: classification of brain activity images from EEG and prediction of time-series from MRI.

## Classification of brain activity from electroencephalograph (EEG)

### Problem

Electroencephalography is an electrophysiological monitoring method to record electrical activity of the brain. It is typically noninvasive, with the electrodes placed along the scalp. EEG has several tens of electrods (or sensors).
![](images/fig1_small.png)

Raw EEG is N time series, where N is a number of electrods.

![](images/fig2.jpg)

![](images/eeg_alpha1_small.jpg)

If we split every time series into blocks of several seconds and then depict all this signals on a map of the head we can see such pictures (left - noise, right - not noise):

![](images/noise_small.png)
![](images/not_noise_small.png)

### Data preprocessing

At the enter of the project I had 7,241 images, 1,700 of them are noise. It's a large enough dataset but it can be better. Firsf of all I flipped every image horizontally, so I've got 14,482 images. Then I balanced classes - I bootstrapped set of 11,082 images from 3,400 noise images. Now I had 22,164 images, e.g. three times more than I had at the start.

### Modelling

For classification I have chosen a convolitional neural network (CNN). It has 4 convolutional layers, 4 max-pooling layers, 2 flatten layers and 2 full layers. As a result I have got a model that classify images with 94.5% accuracy.
