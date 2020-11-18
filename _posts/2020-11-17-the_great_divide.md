---
layout: post
title: Berlin Primary schools
description: Vizualizing Berlin School distribution.
comments: false
category: articles
published: true
image:
  feature: the_great_divide/gleimstrasse.PNG
  
---

Using publicly available data from the Berlin Senate, and with an healthy dose of webscrapping, i did a small visualization based on two factors :
- Entry Acceptance Rate of kids per school,
- non-German origin ("NDH") of the kids per school.

The [result](https://public.tableau.com/profile/clement4142#!/vizhome/Book2_16011299004580/Dashboard?publish=yes) is a sad reflection of the current situation.

As a sidenote, using Tableau is pretty straightforward when it come to basic operations, but as soon as some advanced interaction is required, (e.g implement a dynamic filtering on several fields, or even worse, triggering a model computation), the amount of trickery is mindboggling, see for instance how to [implement a basic Sankey Chart in Tableau](https://www.theinformationlab.co.uk/2018/03/09/build-sankey-diagram-tableau-without-data-prep-beforehand/).

An other shortcoming of Tableau is the lack of dynamic setting of data source. There is the [Tableau Web Connector](https://help.tableau.com/current/server/en-us/datasource_wdc.htm), but this only allow the user to define the data source once at the creation of the dashboard.


-----------



