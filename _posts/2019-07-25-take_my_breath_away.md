---
layout: post
title: Air Square
description: Air particles sensors accuracy
comments: false
category: articles
published: true
image:
  feature: air_square/Claude_Monet_Les_coquelicots.jpg
---


The idea is to find out if the [Luftdaten sensors](https://luftdaten.info/) inacurracy can be compensated with a statistical model.

For this, i compare the measurements from the official Weather station of the DWD (German Weather Service) with the nearest Luftdaten sensors.
There are two related structural flaw with those Luftdaten Sensors (which by the way is an excellent citizen initiative) : 
- the SDS011 laser particle sensors spin out once the humidity is above 70%
- the cheap (but easy to plug, e.g. without soldering) humidity sensors DHT22 that is used by 80% of the installation performs badly.

The bulgarian counterpart of this project uses exclusively the better BOSCH BME280 for temperature and humidity measurements.

There are already some publications on that topics, and i tried to follow the path of [Norbert Streibl](https://www.researchgate.net/publication/320474792_Influence_of_Humidity_on_the_Accuracy_of_Low-Cost_Particulate_Matter_Sensors)

By focusing on the Luftdaten sensors within a range of less than 2 kilometers from a DWD station, and filtering on Luftdaten sensors with BME280 only, we can analyse a pool of roughly 200 locations datasets, and check whether the different compensation formula proposed by Mr Streibl fit with the "reference" values provided by the DWD.


All the scrapping scripts for both Luftdaten and DWD are available on the [github repo](https://github.com/clementlefevre/luftdaten)



Work in progress see the shiny app [here](https://clementlefevre.shinyapps.io/air_square/)


-----------



