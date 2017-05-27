---
layout: post
title: No country for XGB Tree.
description: Is altitude a good predictor for election ?
comments: true
category: articles
published: true
image:
  feature: french_elections/lepen1.jpg
---



It's now a well anchored habit in France : before each election, media (re)discover the rise of extrem right.
Afterward, maps flood the internet to provide the best analysis such as: 

<figure>
	<img src="/images/french_elections/maps/renaud_epstein/fn_vs_tchernobyl.jpg">
	<a href="https://twitter.com/renaud_epstein/status/862913534778277889" target="_blank" ><figcaption>Source : Renaud Epstein</figcaption></a>
</figure>

Using some socio-economical features, we too can build a predictive model for the elections outcomes.

A look at the original artwork French voters produced during the first round of the Presidential election : 

<figure>
	<img src="/images/french_elections/maps/pollock.png">
	<figcaption>Hommage à Jackson Pollock : 1st round best candidate per town</figcaption>
</figure>


And focusing on the Front National :


<figure>
<img src="/images/french_elections/maps/cartograms/cartogram_LePen.png" style="width: 85%;">
</figure>



### Elementary, my dear Pearson.

Using data retrieved from the french national statistics office (INSEE), we focus on the two regions where the Front National got the best results :
- The north (Hauts de France)
- The south (Provence-Alpes-Côte d'Azur)


We can draw the highest correlated factors for each regions :



<figure>
<img src="/images/french_elections/correlograms/unnamed-chunk-7-1.png" style="width: 100%;">
</figure>

In **Provence**, Le Pen scores high where : 
- average education level is low,
- the number of private nurses is low,
- service sector is sparse,
- and, weirdly, altitude is low.

This last element deserves a short digression : [André Siegfried](https://fr.wikipedia.org/wiki/Tableau_politique_de_la_France_de_l%27Ouest_sous_la_Troisi%C3%A8me_R%C3%A9publique), son of a Minister, was a french sociologist and geograph at the beginning of the 20th century. After having lost a campaign, Siegfried investigated the possible relationship between geology and political orientation and came to the following conclusion :  *"granite votes right, limestone votes left"*.


<p style="text-align: center;">*</p>



In the **North**, Le Pen scores high where : 
- average education level is low,
- the median income are low,
- unemployment is high.



<p style="text-align: center;">***</p>

Out of sheer curiosity, how about the relationship between Front National and the **percentage of immigrants** ?
<figure>
<img src="/images/french_elections/scatters/immigrants.png" style="width: 100%;">
</figure>
It seems that the more immigrants in town, the less prone are voters to choose the Front National.

<p style="text-align: center;">***</p>

And how about **population density** ?
<figure>
<img src="/images/french_elections/scatters/density.png" style="width: 100%;">
</figure>
As pointed out by Hervé Le Bras, big cities offer more opportunities, thus lowering the Front National score.
But interestingly enough, this is not the case in Provence.

<p style="text-align: center;">***</p>

Education seems to be the most proeminent factor for Le Pen, how does it compare with Macron ?
<figure>
<img src="/images/french_elections/scatters/no_degrees_LePen.png" style="width: 100%;">
</figure>
<figure>
<img src="/images/french_elections/scatters/nodegrees_Macron.png" style="width: 100%;">
</figure>


<p style="text-align: center;">***</p>

And incomes ?
<figure>
<img src="/images/french_elections/scatters/median_income_LePen.png" style="width: 100%;">
</figure>
<figure>
<img src="/images/french_elections/scatters/median_income_Macron.png" style="width: 100%;">
</figure>



<figure>
<img src="/images/french_elections/maps/unemployment_North.png" style="width: 100%;">
<figcaption>Northern France</figcaption>
</figure>
<figure>
<img src="/images/french_elections/maps/north_LePen.png" style="width: 100%;">
<figcaption>Northern France</figcaption>
</figure>

<figure>
<img src="/images/french_elections/maps/abstention_North.png" style="width: 100%;">
<figcaption>Northern France</figcaption>
</figure>


As Hervé Le Bras already mentioned, poors have a low turnout. 
In the north, Le Pen scores well where unemployment is high.


<p style="text-align: center;">***</p>

Finally, how about **elevation** ?
<figure>
<img src="/images/french_elections/scatters/elevation_LePen.png" style="width: 100%;">
</figure>
<figure>
<img src="/images/french_elections/maps/elevation_PACA.png" style="width: 100%;">
<figcaption>Provence-Alpes-Côte d'Azur</figcaption>
</figure>
<figure>
<img src="/images/french_elections/maps/LePen_PACA.png" style="width: 100%;">
<figcaption>Provence-Alpes-Côte d'Azur</figcaption>

</figure>
<figure>
<img src="/images/french_elections/maps/unemployment_PACA.png" style="width: 100%;">
<figcaption>Provence-Alpes-Côte d'Azur</figcaption>

</figure>

Indeed, comparing with an other region with high elevation gradient (Rhône Alpes), Le Pen does score poorly at high altitude.

An other interesting observation is for the area of Nice, where unemployment is low and Le Pen high. This confirm the thesis of a two-headed Front National, one of the North, more social, and an other of the South, closer to Poujade. And following latest development in the french political landscape (as of may 2017), it might augure a **schism within the Front National**.

<p style="text-align: center;">***</p>

### Creating a model

Well, now we have a dataset with 35000 cities and for each, 170 predictors (such as the ratio of camping place per habitant, the proportion of student or the local GDP).

Instead of going through the painful process of features selection (as seen before, lots of multicollinearity here) and regularization, we prefer to hop in the Land Cruiser of Machine Learning :  **XGB Tree**.

<figure>
<img src="/images/french_elections/landcruiser.jpg" style="width: 75%;">
<figcaption>Load the dataset, tune hyperparameters and off we go !</figcaption>
</figure>

For the detailed implementation of the algorithm, see <a href="https://github.com/clementlefevre/france_elections/blob/master/XGB_elections.Rmd" target="_blank">here</a>

<p style="text-align: center;">***</p>

### Confusion Matrix and Statistics


|prediction/real | FILLON| LE.PEN| MACRON| MÉLENCHON|
|:---------------|------:|------:|------:|---------:|
|FILLON          |    995|    358|    205|        48|
|LE.PEN          |    454|   4854|    429|       204|
|MACRON          |    229|    278|   1319|       286|
|MÉLENCHON       |     46|    111|    197|       529|






	Overall Statistics
	                                          
	               Accuracy : 0.7401          
	                 95% CI : (0.7316, 0.7484)
	    No Information Rate : 0.5313          
	    P-Value [Acc > NIR] : < 2.2e-16       
	                                          
	                  Kappa : 0.5864          
	 Mcnemar's Test P-Value : 6.207e-11       

	Statistics by Class:

	                     Class: FILLON Class: LE.PEN Class: MACRON Class: MÉLENCHON
	Sensitivity                0.59605        0.8698        0.6212          0.53140
	Specificity                0.93704        0.7925        0.9104          0.95703
	Pos Pred Value             0.64918        0.8261        0.6397          0.58214
	Neg Pred Value             0.92229        0.8430        0.9037          0.94772
	Prevalence                 0.16350        0.5313        0.2039          0.10125
	Detection Rate             0.09746        0.4621        0.1267          0.05381
	Detection Prevalence       0.15012        0.5594        0.1980          0.09243
	Balanced Accuracy          0.76655        0.8311        0.7658          0.74421


<figure>
<img src="/images/french_elections/xgb/features_importance_XGB.png" style="width: 100%;">
</figure>


**74% accuracy on the testing set** is not so bad, given the model does not take into account the local specificities and history (althought we use the outcome of the previous presidential election). 
But what is striking is the high sensitivity of the Le Pen compared with her challenger, that might be related to the unbalanced aspect of the dataset : She finished first in half of the towns on the first round.

Regarding the features weight, the 2012 results are overwhelmingly the best predictors. Then come :
- the ratio of self-employed in the active population
- population's density,
- ratio of university degrees,
- latitude,
- elevation,
- average income per household.


So, on the scale of France, the elevation does indeed **play a significant role in the vote**. I'll quote Hervé Le Bras : for communities away from main communication axis and thus less prone to mobility, social interactions are stronger and rumours less likely to spread.




### References :

- [Nantes, un bastion socialiste partagé entre les votes Macron et Mélenchon - FR](http://www.metropolitiques.eu/Nantes-un-bastion-socialiste.html)
- [Exode urbain et inégalités : les cartes du vote FN](https://www.franceculture.fr/politique/exode-urbain-et-inegalites-les-cartes-du-vote-fn)
- [Statistics per town - french institute for statistics and economics studies- INSEE](https://www.data.gouv.fr/fr/datasets/data-insee-sur-les-communes/)
- [Presidential elections results - first round](https://www.data.gouv.fr/fr/datasets/election-presidentielle-des-23-avril-et-7-mai-2017-resultats-du-1er-tour-1/)
- [The Economist : daily chart](http://www.economist.com/blogs/graphicdetail/2017/05/daily-chart-5)
