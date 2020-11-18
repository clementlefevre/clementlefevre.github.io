---
layout: post
title: Berlin Primary schools
description: Vizualizing Berlin School distribution.
comments: false
category: articles
published: true
image:
  feature: the_great_divide/gleimstrasse.PNG
  caption: "the Berliner Biofilter"
  
---

Using publicly available data from the Berlin Senate, and with an healthy dose of webscrapping, i did a small visualization based on two factors :
- Entry Acceptance Rate of kids per school,
- non-German origin ("NDH") of the kids per school.

The [result](https://public.tableau.com/profile/clement4142#!/vizhome/Book2_16011299004580/Dashboard?publish=yes) is a sad reflection of the current situation.

As a sidenote, using Tableau is pretty straightforward when it comes to basic operations, but as soon as some advanced interactions are required, (e.g implement a dynamic filtering on several fields, or even worse, triggering a model computation), the amount of trickery becomes mindboggling, see for instance how to [implement a basic Sankey Chart in Tableau](https://www.theinformationlab.co.uk/2018/03/09/build-sankey-diagram-tableau-without-data-prep-beforehand/).

An other shortcoming of Tableau is the lack of dynamic setting of data source. There is the [Tableau Web Connector](https://help.tableau.com/current/server/en-us/datasource_wdc.htm), but this only allows users to define the data source once at the creation of the dashboard.

That is why when you need a real dynamic binding between your dashboard and the backend (think compute a new prediction), i definitely would stick on Javascript (the D3js library and its wrapper offers endless possibilities and customization), especially as current Javascripts frameworks (react, vue) have become mature and well maintained.

[Source Code](https://github.com/clementlefevre/berlin_grundschulen_2019_2021)
-----------



