---
layout: post
title: No country for XGB Tree.
description: Is altitude the best predictor for election ?
comments: true
category: articles
published: true
image:
  feature: french_elections/lepen1.jpg
---



It's now a well anchored habit in France : before each election, media (re)discover the rise of extrem right.
Then afterward, charts or dataviz' flood the internet to provide the best analysis : 

<figure>
	<img src="/images/french_elections/maps/renaud_epstein/fn_vs_tchernobyl.jpg">
	<figcaption>Source : Renaud Epstein</figcaption>
</figure>

Using some socio-economical features, we too can build a predictive model for the elections outcomes.

A look at the original artwork French voters produced during the first round of the Presidential election : 

<figure>
	<img src="/images/french_elections/maps/unnamed-chunk-9-1.png">
	<figcaption>Hommage à Jackson Pollock : 1st round best candidate per town</figcaption>
</figure>



### The Voice (of the expert)

The french demograph and historian Herve Le Bras points the following factors to explain the Front National votes:
- exclusion from economical dynamism,
- regional specificity,
- geology ([Siegfried](https://fr.wikipedia.org/wiki/Tableau_politique_de_la_France_de_l%27Ouest_sous_la_Troisi%C3%A8me_R%C3%A9publique)),
- the poor do not votes, but the vote is strongly influenced by their direct environment.

### "Elementary, my dear Pearson !"

Using data retrieved from the french national statistics office (INSEE), we focus on three regions :
- The north (Hauts de France)
- The south (Provence Alpes Cotes d'Azur)
- The west (Bretagne)

We can draw the highest correlated factors for each regions :



<figure>
<img src="/images/french_elections/correlograms/unnamed-chunk-7-1.png" style="width: 100%;">
</figure>

In Provence, Le Pen scores high where : 
- average education level is low,
- the number of freelance nurses is low,
- service sector is sparse,
- altitude is low.



<figure>
<img src="/images/french_elections/correlograms/unnamed-chunk-7-2.png" style="width: 100%;">
</figure>
In North, Le Pen scores high where : 
- average education level is low,
- the median income are low,
- unemployment is high.

<figure>
<img src="/images/french_elections/correlograms/unnamed-chunk-7-3.png" style="width: 100%;">
</figure>
In Bretagne, Le Pen scores high where : 
- average education level is low,
- the median income are low,
- service sector is sparse.


Out of sheer curiosity, how about the relationship between Front National and the **percentage of immigrants** ?
<figure>
<img src="/images/french_elections/scatters/immigrants_LePen.png" style="width: 100%;">
</figure>
The more foreigners, the less prone are voters to choose the Front National.

<p style="text-align: center;">***</p>

And how about **population density** ?
<figure>
<img src="/images/french_elections/scatters/density_LePen.png" style="width: 100%;">
</figure>
As pointed out by Le Bras, big cities offer more opportunities, thus lowering the Front National score.
But interestingly enough, this does not occurs in Provence.

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
<img src="/images/french_elections/maps/North_LePen.png" style="width: 100%;">
</figure>

<figure>
<img src="/images/french_elections/maps/unemployment_North.png" style="width: 100%;">
</figure>

<figure>
<img src="/images/french_elections/maps/abstention_North.png" style="width: 100%;">
</figure>


<p style="text-align: center;">***</p>

Finally, how about elevation ?
<figure>
<img src="/images/french_elections/scatters/elevation_LePen.png" style="width: 100%;">
</figure>
<figure>
<img src="/images/french_elections/maps/elevation_PACA.png" style="width: 100%;">
</figure>
<figure>
<img src="/images/french_elections/maps/PACA_LePen.png" style="width: 100%;">
</figure>
Indeed, comparing with the region with the highest elevation gradient (Rhone Alpes), Le Pen does not score well in high altitude.








### References :

- [Nantes, un bastion socialiste partagé entre les votes Macron et Mélenchon - FR](http://www.metropolitiques.eu/Nantes-un-bastion-socialiste.html)
- https://www.franceculture.fr/politique/exode-urbain-et-inegalites-les-cartes-du-vote-fn
- https://www.data.gouv.fr/fr/datasets/data-insee-sur-les-communes/
- https://www.data.gouv.fr/fr/datasets/election-presidentielle-des-23-avril-et-7-mai-2017-resultats-du-1er-tour-1/
