---
layout: post
title: Take my breath away
description: Air particles sensors accuracy
comments: false
category: articles
published: true
image:
  feature: take_my_breath_away/Claude_Monet_Les_coquelicots.jpg
---


The idea is to find out if the [Luftdaten sensors](https://luftdaten.info/) inacurracy can be compensated with a statistical model.

For this, i compare the measurements from the official Weather station of the German Weather Service with the nearest Luftdaten sensors.
There are two related structural flaw with those Luftdaten Sensors (which by the way is an excellent citizen initiative : 
- the SDS011 laser particle sensors spin out once the humidity is above 70%
- the cheap (but easy to plug, e.g. without soldering) humidity sensors DHT22 that is used by 80% of the installation performs badly.


Work in progress see the shiny app [here](https://clementlefevre.shinyapps.io/Air_square/)


-----------



