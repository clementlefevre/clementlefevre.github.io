---
layout: post
title: Switching to data.table with Zwift
description: the cousin of pandas is a morse.
comments: false
category: articles
published: true
image:
  feature: zwifting_with_data_table/tom_simpson.jpg
  
---

(Tom Simpson / Mont Ventoux,  13th July 1967)

After having used the tidyverse toolkit for a while to wrangle data in R, i recently switched to the data.table package. I found this [page](http://franknarf1.github.io/r-tutorial/_book/tables.html#tables) very helpful to grasp the power of **data.table**.

![alt text](/images/zwifting_with_data_table/logo.png "The data.table logo : an Aha moment once i understood it deepest meaning...")


For dataset bigger than 1GB than can fit into the RAM, read, write, filter and aggregations operations are 10 to 100 times faster than the dplyr/base R tools.

On top of that, i found its syntax extremely concise, like writing Haiku in R.
I started learning R using the dplyr/tidyr packages three years ago, and switching to data.table is a logical evolution.

As a [Zwift](https://zwift.com/) player, i epxlored their API with the help of data.table.

The result can be seen [here](https://zwiftclement.s3.amazonaws.com/EDA_zwift_profiles_short.html)



-----------



