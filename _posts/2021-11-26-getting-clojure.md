---
layout: post
title: Unknow Clojure.
description: immutable data pipeline
comments: true
category: articles
published: true
image:
  feature: getting_clojure/joy-division-closer2.jpg
---

(The  Appiani family tomb in Genoa, cover for Joy Division - Closer 1980)

Running a data pipeline during the development phase can be burdensome, especially when requirements are highly volatile.
I decided to give Clojure a try, and so far i am enjoying it.

For the context, after having worked several years with Java, i developped an acute [Spring Framework Stress Disorder](https://www.youtube.com/watch?v=0p_1QSUsbsM&ab_channel=QueenOfficial). On the other hand, having to share R/python applications with end users when no IT infrastructure available can quickly turns burdensome.

In my previous post, i exposed the benefits of having your code running as binary for quick prototyping (with a minimum knowledge of a javascript framework).

With Clojure, so far, i found the best of both worlds : a language offering a real REPL for development (think R : small snippets of code and validating them on the fly) and the ability to deliver your code as a binary file.

<figure>
	<img src="/images/getting_clojure/excel_forever.png" style="width: 95%;">
	<figcaption>Source : Twitter (a popular microblogging application)</figcaption>
</figure>


A typical use case in my context : load some Excel files, add a few database tables, filter, join, parse and push it back in a database.
Of course we could do it with R in a breeze, but installing and setting up the whole R machinery on your users machines, even the portable version one, can turn into a painful experience.

Clojure offers a [dataframe library](https://scicloj.github.io/tablecloth/index.html), sitting on an implementation of the [BLAS](https://github.com/bytedeco/javacpp-presets/tree/master/openblas) (Basic Linear Algebra Subprograms) 

A quick benchmark shows that a 1 millions rows csv, the loading time is roughly three times slower than the R "Marco Pantani" [data.table package](https://cran.r-project.org/web/packages/data.table/vignettes/datatable-intro.html)

Cherry on the cake, out of the box interoperability with Java grant you access to all the maven world.
And honey on the sugar, you can generate binary file for your end user with the help of GraalVM.

Link to a [minimalistic demo](https://github.com/clementlefevre/clojure_for_data_manipulation).










