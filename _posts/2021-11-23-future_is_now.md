---
layout: post
title: the future is now.
description: a web application without infrastructure
comments: true
category: articles
published: true
image:
  feature: future_is_now/Erfurt_latrine_disaster.jpg
---

(VGAN generated picture by Erfurt Latrine Disaster @ErfurtLatrine)

I recently had to ship a small interactive tool that for some reasons should not be deployed on a server.
R Shiny or any pythonical alternative would have been a neat option, but the installation process, especially for non-technical user would have been a burden (think software updates).

How about docker running locally ? well, before Windows provided the [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install) option, it was to say the least an interesting experience to learn more about your resistance to pain.

I then gave a try to [golang](https://go.dev/), and found its tooling excellent : setting up the VSCode plugin was a breeze, no time wasted to setup the debugger, the linter etc...
And cherry on the cake, for a compiled language, it's compilation time is excellent (a few seconds for a small project).
One other interesting aspect of golang is that its creator Rob Pike designed golang from the start with concurrency in mind. As a result, writing so-called goroutines (multiples processes running at the same time) in go is quite easy and readable.

<figure>
	<img src="/images/future_is_now/benchmark.PNG" style="width: 95%;" target="_blank" href="https://greenlab.di.uminho.pt/wp-content/uploads/2017/10/sleFinal.pdf">
	<figcaption></figcaption>
</figure>
And, last but not least, golang provides a Webassembly compiler, that let you convert your golang code into a webassembly file.
What does this means ? For people old enough to remember the time before Instagram, there was google Earth, a program also used to stalk your neighbour's life. Google Earth at that time was a desktop application, requiring user to first download and install it to be able to use it.
<figure>
	<img src="/images/future_is_now/aws.PNG" style="width: 95%;">
	<figcaption>Source : Twitter (a popular microblogging application)</figcaption>
</figure>

Nowadays, if you open your browser and open the new [google earth version](https://earth.google.com/web/), you get the same function,
 but this time the whole rendering calculation is done within your browser, thanks to webassembly. You can even run a [jupyter notebook in your browser](https://jupyterlite.github.io/demo/lab/index.html) with a webassembly version of python ! 

Coming back to my local application, i then pretrained a XGB classifier in python, and exported the fitted model as a file. Then, i used a [golang package](https://gowalker.org/github.com/dmitryikh/leaves) to read this model and compute prediction given a user input. The corresponding golang code was finally compiled into a Webassembly file.

I ended then using an ultralight [http server written in golang](https://github.com/ethanpil/sheret) (less than 7MB), serving a VueJs Dashboard with a Webassembly file running the pretrained XGBoost Classifier. And i forgot to mention that golang can very easily generate binary files (e.g. .exe file for Windows), making the delivery of this local application pretty straightforward.
The future is now.

[link to the XGBoost Webassembly demo code](https://github.com/clementlefevre/webassembly_xgboost_demo)
(credits to Vanessa Sochat the original code)

## Reference
https://greenlab.di.uminho.pt/wp-content/uploads/2017/10/sleFinal.pdf