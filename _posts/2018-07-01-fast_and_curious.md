---
layout: post
title: Fast And Curious
description: Speed Camera.
comments: true
category: articles
published: true
image:
  feature: fast_and_curious/title.png
---


## Monitoring the traffic speed in my street.

Using a Raspberry Pi, and a webcam, i recorded one full month of vehicles speed passing by.

The idea was to have a first experience with image classification with deep neural networks, and get some insight about the speeding behavior.


## Image recording and processing
|Speedcam Screenshot|
|:--:|
|![](/images/fast_and_curious/speedcam1.png)|

I used the  [speedcam project](https://github.com/pageauc/speed-camera), an openCV based script that compute the estimated speed of moving object, and stored the resulting pictures and speed data on a S3 instance.

The setup and calibration of the raspi with this software is well documented.

## The Mechanical French : label your pictures by hand.

Using those raw data, i labeled all the records, with the help of a homemade product : **The Mechanical French**, whose hourly rate is significantly lower than its foreign counterpart. Managed to classify 20000 pictures within 15 hours. Joke apart, it is a simple Flask app i wrote, as i could not find any opensource tool.

|The mechanical french, a revolutionary labelling interface.|
|:--:|
|![](/images/fast_and_curious/mechanicalfrench.png)|


## The deep dive 

Once all training pictures are labellized, we can start training a convolutional network model.


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



