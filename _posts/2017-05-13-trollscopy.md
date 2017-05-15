---
layout: post
title: Trolloscopy.
description: Pro-Kremlin comments in the Financial Times.
comments: true
category: articles
published: true
image:
  feature: trolloscopy/ft_no_comment.png
---



Beeing a regular reader of the FT, i find the quality of the comments section far above the standard level we can expect those days. The fact that only suscribers can comment gives it a touch of Gentleman's club.
This makes the comment section an interesting study field for the Kremlin supporting members : no invective or so-called "meme", but rather structured debates. 

I started by  retrieving the comments for articles related to the following keywords :
**Syria, Gazprom, Brexit, MH17, NATO, Trump, Assad, Georgia, IOC, Doping, Putin, Merkel, Refugees, Afd, Le Pen, Obama, Russia**. 

From February 2009 to Sept 2016, it produces a dataset of 240 000 comments for 10 000 articles.


<figure>
	<img src="/images/trolloscopy/top_commentators.png" style="width: 95%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>


A "Like" option allows commentators to tag the others.


Those are the top likers :

<figure>
	<img src="/images/trolloscopy/top_likers_barchart.png" style="width: 75%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>


And the top liked :
<figure>
	<img src="/images/trolloscopy/top_liked_barchart.png" style="width: 75%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>


And summarized in a matrix :

<figure>
	<img src="/images/trolloscopy/like_matrix.png" style="width: 85%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>


Astonishingly, the top 10 commentators in term of quantity and "quality"(if we considere the number of likes a reasonable metrics) are pro-Kremlin !


Now, taking the top commentators, how do their activity look like :

__Nota Bene : UTC+3 corresponds to Saint Petersburg.__

<figure>
	<img src="/images/trolloscopy/timeline.png" style="width: 100%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>

<figure>
	<img src="/images/trolloscopy/timeline2.png" style="width: 100%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>

<figure>
	<img src="/images/trolloscopy/timeline3.png" style="width: 100%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>

Well, looking at the activity curves, my take is those are people doing extra jobs as commentators.

<figure>
	<img src="/images/trolloscopy/top2liker_timeline.png" style="width: 100%;">
	<figcaption>Source : Financial Times</figcaption>
</figure>

Well, there is a pattern here :
- March 2014 : Crimean annexion
- Sept 2015 : Putin intervenes in Syria
- October 2016 : Doping scandal



Now, using word vectorization and TFIDF (Term Frequency-Inverse Document Frequency), we can extract the main components describing the best the variance between the top commentators :


<figure>
	<img src="/images/trolloscopy/pca.png" style="width: 100%;">
	<figcaption>PCA for the two heaviest eingenvectors (top commentators) - Source : Financial Times</figcaption>
</figure>


Here my take is that Njegos and Maljoffre are the same person.



### References :

- [Bakamo Media - French Presidential Election study](https://www.bakamosocial.com/frenchelection/)
