---
layout: post
title: Golang and one step clojure.
description: The  Appiani family tomb  (cover for Joy Division - Closer 1980).
comments: true
category: articles
published: true
image:
  feature: getting_clojure/joy-division-closer.jpg
---

I recently had to ship a small interactive tool that for some reasons could not be deployed on a server.
R Shiny would have been a neat option, but the installation process for R, especially for non-technical user would have been a burden, especially when planning software updates.
How about docker running locally ? well, before Windows provided the WSL2 option, it was to say the least an interesting experience.
I then gave a try to golang, and found its tooling excellent : setting up the VSCode plugin was a breeze, and the compilation times is amazing.


https://github.com/clementlefevre/regression-wasm


``` clojure
(ns clojure-sandbox.databaseservice  (:require [next.jdbc :as jdbc] [tablecloth.api :as tc]))
;; set the DB Connection
(def ds (jdbc/get-datasource {:jdbcUrl "my_url"  :user "my_name"
                              :password "my_pwd" }))

;; query DB
(def raw_rs (jdbc/execute! ds ["SELECT * FROM  TABLE_1"]))

;; convert to dataframe and do your stuff:
(def df (-> raw_rs (tc/dataset  {:key-fn keyword})))

(def df_baujahr (-> df (tc/unique-by :BAUJAHR)
                    (tc/select-columns :BAUJAHR)
                    (tc/replace-missing  :BAUJAHR :value -999)
                    (tc/convert-types {:BAUJAHR :int32})
                    (tc/order-by :BAUJAHR)))

```


### References :

