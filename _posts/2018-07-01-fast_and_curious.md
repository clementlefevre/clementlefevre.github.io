---
layout: post
title: Fast And Curious
description: Testosteron-off.
comments: true
category: articles
published: true
image:
  feature: fast_and_curious/title.png
---


## Monitoring the traffic speed.

Using a Raspberry Pi, and a webcam, i recorded one full month of vehicles speed passing by.

The idea was to have a first experience with image classification with deep neural networks, and get some insight about the speeding behavior.


### Image recording and processing

|Speedcam Screenshot|
|:--:|
|![](/images/fast_and_curious/speedcam1.png)|


I used the  [speedcam project](https://github.com/pageauc/speed-camera), an openCV based script that compute the estimated speed of moving objects, and stored the resulting pictures and speed data on a S3 instance.

The setup and calibration of the raspi with this software is well documented.

#### The Mechanical French

Once data are recorded (one picture per vehicle measured), we can start the classification process.
Using those raw data, i labeled 20 000 pictures, with the help of a homemade product : **The Mechanical French** (as i could not find any opensource tool.). This labeling process took me 15 hours.

|The mechanical french, a revolutionary labelling interface.|
|:--:|
|![](/images/fast_and_curious/mechanicalfrench.png)|


### The deep dive 

Once all training pictures are labeled, we can start training a convolutional network model.
For my first try, i did not use transfer learning like pretrained network. For those interested in this technique, Francois Chollet did an excellent job to explain the concept with an hands-on example [here](https://github.com/fchollet/deep-learning-with-python-notebooks/blob/master/5.3-using-a-pretrained-convnet.ipynb).

Although the training set has been labeled with 10 categories, i used  as a matter of simplification,a binary classifier (car/bike). Indeed, the dataset is very unbalanced (few ambulances vs lots of cars)

The Network structure :




With a low-end graphic card, the model training takes 2 hours.

Finally, using the classifier build from scratch, we can classify the picture. 

|Bikes vs Cars|
|:--:|
|![](/images/fast_and_curious/bike_car.png)|


|Speeding heatmap|
|:--:|
|![](/images/fast_and_curious/heatmap.png)|


|Mean Temperature vs Speeding vs Bikes flow|
|:--:|
|![](/images/fast_and_curious/speed_temp_bike.png)|



|Overall Infrastructure|
|:--:|
|![](/images/fast_and_curious/SpeedCamFlowChart.png)|



|Average speed during a day|
|:--:|
|![](/images/fast_and_curious/traffic_2018-05-11.png)|


-----------



