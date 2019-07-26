---
layout: post
title: Lidar maximo !
description: playing with lidar data.
comments: false
category: articles
published: true
image:
  feature: lidar_maximo/bruno-ganz.jpg

---


First i discovered the amazing package [Rayshader](https://github.com/tylermorganwall/rayshader) for R and [played a little bit with.](https://github.com/clementlefevre/litto3d)



After having stumbled upon this nice vizualisation from Fabien Lezeau @LzuFabien :
![alt text](/images/lidar_maximo/Fabien_Lezeau.jpeg "Map of Lebanon")

i followed this excellent tutorial from [Daniel Huffman @pinakographos](https://somethingaboutmaps.wordpress.com/2017/11/16/creating-shaded-relief-in-blender/)

On top of that i retrieved the [2018 Lidar data from Berlin](https://fbinter.stadt-berlin.de/fb/) (look for "ATKIS® DOM - Digitales Oberflächenmodell")

Finally, and before my desk began to burn with the CPU overheat, i found a way to run Blender on Google Colab.
This is really nice, (and free), as you can simply upload your raster files and blender on google drive and run the rendering from your browser with a Tesla K80 GPU. What required 5 hours on my old laptop takes 6 minutes, which i considere an improvement.

Just open the picture in a new tab to zoom, or better, download them to open them with an image viewer :

![alt text](/images/lidar_maximo/berlin_humboldthain.png "Berlin Humboldthain")

![alt text](/images/lidar_maximo/berlin_mitte.png "Berlin Mitte")

![alt text](/images/lidar_maximo/tegel.png "Berlin Tegel")


And for this one, i used the [IGN Litto3d data](https://diffusion.shom.fr/pro/risques/altimetrie-littorale.html) :

![alt text](/images/lidar_maximo/camaret_MNT1_worked.png "Bretagne - Camaret")



Quick walkthrough to render on Google Colab:

- open a GPU enable google colab notebook
- use the [*blender_test.ipynb*](https://github.com/clementlefevre/litto3d/blob/master/blender_test.ipynb) from the github as template.
- adjust the [*config.py*](https://github.com/clementlefevre/litto3d/blob/master/config.py) file from the github repo (set raster & tiles files names)
- upload on your google drive the raster file, the tile file (both .tiff), the .blend file and the config.py.
- run the notebook, it will first install blender, compile CUDA, anf finally render into the ouput.png file (see the left tab "file" in the notebook,click "refresh")




-----------



