---
layout: post
title: Funny Games
description: Finding the missing podcast
comments: false
category: articles
published: true
image:
  feature: funny_games/medusa_caravaggio.jpg
---

(Medusa, Caravaggio)

## The missing podcast
i rode my bike accross Bretagne while listening to a nice serie of podcasts about [Michael Haneke work](https://www.franceculture.fr/emissions/les-nouveaux-chemins-de-la-connaissance/philosopher-avec-michael-haneke-14-le-cinema-sans)

But the last part was not properly linked and instead of a psychanalysis of "La pianiste", i got a boring interview of Alain Badiou and Socrate in Da Hood.
Well, i was very frustrated and, once at home, i decided find the missing episode.

For this i first downloaded all the 1435 episodes of the "Chemins de la Connaissance" and looked at what is the current "state of the Art" for french speech to text.

Seems that AWS does not perform well in english. 

Mozilla on its side has the deep speech project (based on Tensorflow), but there is a of today no french pretrained model to use.

I thus used the experimental Google Speech to Text API with the diarization feature. This means the speech will be transcribed into a conversation rather a plain transcription.

The results was really nice , especially it could recognize the name of the actors.

The only downside is that looking at my Google billing, i would end with more than 2000 euros to transcribe all episodes. I found out that it would worthier to analyse myself the movie.

[link to the google colab notebook](https://github.com/clementlefevre/dictee_magique/blob/master/france_culture_mp3_storage.ipynb)




-----------



