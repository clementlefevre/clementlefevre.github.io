---
layout: post
title: Populist Component Analysis
description: Quantify MEP votes.
comments: false
category: articles
published: true
image:
  feature: populist_component_analysis/hans-baluschek-nuit-decc81tecc81-1928.jpg
---

(SommerabendBaluschek, Hans 1870–1935)

## Is there a pattern in our MEP vote behavior ?


Using the data retrieved from the Vote Watch NGO website for the 2014-19 European Parliementary session,
i tried to rebuild this [nice plot from the economist](https://www.economist.com/graphic-detail/2019/06/01/centrist-liberals-gained-the-most-power-in-the-eu-parliament) :

![alt text](/images/populist_component_analysis/the_economist.png "The economist")


You can see the vizualisation [here](https://clementlefevre.shinyapps.io/mep_term8_pca/) and download the raw data from the *about* section.

The source code is available [here](https://github.com/clementlefevre/mep_votewatch)


### Methodology

i first scrapped the complete voting history for all the 800+ MEP members.
Then i used a PCA on the member / votes matrix.
The resulting visualization shows the first and second Principal Components (between 91 an 98% of the explained variance).

-----------



