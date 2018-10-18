# Brain-activity-classification-and-regression

I was always fascinated with medicine and biology. Particularly, I'm interested in the prevention of the diseases as opposed to their treatment. One of my friends, a scientist, captivated my attention with a really cool biofeedback study, where a person lies inside the magnetic resonance imaging (MRI) scanner, sees his indicators and changes them with an effort of will. Alternatively, a person wears a heart rate monitor and by augmenting the will he or she changes the pulse. As another option, he or she sees signals from an electroencephalograph and also changes those.
I am particularly impressed that my friend's study is focused on people suffering from depressive disorders. I believe that such a treatment is the future. The body ceases to be a black box, at the entrance of which it is served with medications, while at the exit it gets relief from pain or depression. On the other hand, within the approach of my friend, a person sees what is actually happening in his head, and receives not only understanding, but also control over these processes. This idea captured me completely. Being a data scientist, I decided to join this process.

This capston project consists of two parts: classification of brain activity images from EEG and prediction of time-series from MRI. 

## Classification of brain activity from electroencephalograph (EEG)

### Problem

Electroencephalography is an electrophysiological monitoring method to record electrical activity of the brain. It is typically noninvasive, with the electrodes placed along the scalp. EEG has several tens of electrods (or sensors).
![](images/fig1_small.png)

Raw EEG is N time series, where N is a number of electrods.

![](images/fig2.jpg)

EEG recording is a mixture of both target signals and multiple third-party signals, noise artifacts. The noise complicate not only the visual presentation of signal, but also algorithmic post-processing. Clearing data from noise artifacts is a very important and time-consuming task requiring expert level of knowledge and experience of the experimenter. It leads to bad reproducibility of results not only between different teams, but even inside one team and inside one experiment, since the work of an expert is subject to many human factors (fatigue, time limit, errors). Also, if during processing the experimenter decides to change the design processing, then, as a rule, this leads to the need to perform cleaning again.

![](images/eeg_alpha1_small.jpg)

Many other physiological components can also be removed if their characteristic signal is not in the area of interest of the experimenter. For the classification of components by the experimenter, there are several methods of graphical representation, among which the most popular are spectral power, the intensity of the component on the electrodes, and the intensity in time.

If we split every time series into blocks of several seconds and then depict all this signals on a map of the head we can see such pictures (left - noise, right - target signal):

![](images/noise_small.png)
![](images/not_noise_small.png)

My task is to create a convolutional neural network (CNN) for classifying this components into noise and signals.

### Data preprocessing

At the enter of the project I had 7,241 images, 1,700 of them are noise. It's a large enough dataset but it can be better. Firsf of all I flipped every image horizontally, so I've got 14,482 images. Then I balanced classes - I bootstrapped set of 11,082 images from 3,400 noise images. Now I had 22,164 images, e.g. three times more than I had at the start.

### Modelling

For classification I have chosen a convolitional neural network (CNN). It has 4 convolutional layers, 4 max-pooling layers, 2 flatten layers and 2 full layers. As a result I have got a model that classify images with 94.5% accuracy.
