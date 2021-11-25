---
layout: post
title: golang and one step clojure.
description: 
comments: true
category: articles
published: true
image:
  feature: getting_clojure/joy-division-closer2.jpg
---

*The  Appiani family tomb in Genoa  (cover for Joy Division - Closer 1980).*

#### go go go !
I recently had to ship a small interactive tool that for some reasons should not be deployed on a server.
R Shiny or any pythonical alternative would have been a neat option, but the installation process, especially for non-technical user would have been a burden (think software updates).

How about docker running locally ? well, before Windows provided the [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install) option, it was to say the least an interesting experience to learn more about your resistance to pain.

I then gave a try to [golang](https://go.dev/), and found its tooling excellent : setting up the VSCode plugin was a breeze, no time to waste to setup the debugger, the linter etc...
And cherry on the cake, for a compiled language, it's compilation time is excellent (a few seconds for a small project).
One other interesting aspect of golang is that its creator Rob Pike designed golang from the beginning with concurrency in mind. As a result, writing so-called goroutines (multiples processes running at the same time) in go is quite easy and readable.

<figure>
	<img src="/images/getting_clojure/benchmark.PNG" style="width: 95%;" target="_blank">
	<figcaption>right-click - "open in a new tab" to zoom in</figcaption>
</figure>
And, last but not least, golang provides a Webassembly compiler, that let you convert your golang code into a webassembly file.
What does this means ? For people old enough to remember the time before Instagramm, there was google Earth, a desktop application that let us observe our neighbours's garden thanks to the satellite imagery.
<figure>
	<img src="/images/getting_clojure/aws.PNG" style="width: 95%;">
	<figcaption>Source : Twitter (a popular microblogging application)</figcaption>
</figure>

Nowadays, if you open your browser and open the new [google earth version](https://earth.google.com/web/), you get the same function,
 but this time the whole rendering calculation is done within your browser, thanks to webassembly. You can even run a [jupyter notebook in your browser](https://jupyterlite.github.io/demo/lab/index.html) with a webassembly version of python !

Coming back to my application, i ended then using an ultralight [http server written in golang](https://github.com/ethanpil/sheret) (less than 3MB), serving a VueJs Dashboard with a Webassembly file running a pretrained XGBoost Classifier. And i forgot to mention that golang can very easily generate binary files (e.g. .exe file for Windows), making the delivery of this local application pretty straightforward.
The future is now !

[link to the XGBoost Webassembly code](https://github.com/clementlefevre/regression-wasm)









``` clojure
(ns clojure-sandbox.databaseservice  (:require 
[next.jdbc :as jdbc] [tablecloth.api :as tc]))
;; set the DB Connection
(def ds (jdbc/get-datasource {:jdbcUrl "my_url"  :user "my_name"
                              :password "my_pwd" }))

;; query DB
(def raw_rs (jdbc/execute! ds ["SELECT * FROM  TABLE_1"]))

;; convert to a dataset:
(def ds (-> raw_rs (tc/dataset  {:key-fn keyword})))

;; and do your stuff:
(def ds (-> df (tc/unique-by :Year)
                    (tc/select-columns :Year)
                    (tc/replace-missing  :Year :value -999)
                    (tc/convert-types {:Year :int32})
                    (tc/order-by :Year)))

```


### References :

