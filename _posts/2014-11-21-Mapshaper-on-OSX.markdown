---
author: Alex Singleton
layout: post
title: Simplify a Shapefile with Mapshaper on OSX
categories:
- Software
---


Yesterday I needed to simplify a shapefile quite substantially to get the size down enough that it could be loaded into CartoDB. Using QGIS this tended to leave [sliver or gaps between polygons](http://de.wikipedia.org/wiki/Sliver_Polygon), but I came across [Mapshaper](https://github.com/mbloch/mapshaper). This is primarily a command line tool and is built on [node.js](http://nodejs.org/). However, a [web version](http://www.mapshaper.org/) also exists. There are a load really useful GIS functions such as simplifying, clipping, dissolve, joins and merges. 


##Using Mapshaper on OSX
From install to use (including node.js) was about two minutes...

The first step is to install [node.js](http://nodejs.org/); visit the website and download the package by clicking the install button on the homepage. Run the install and follow through the instructions. This will install node.js on your computer - this is a platform built on Chrome's JavaScript runtime for developing applications. Node.js is cropping up in lots of new applications - for example, the new blogging system [Ghost](https://ghost.org/).

![node.js](/public/images/node.png)

After install of node.js, you need to install Mapshaper which can be done by running the following on the terminal:

~~~
npm install -g mapshaper
~~~

If you get an error about permissions when running the above, you might have to preface the command with sudo (which will ask you for a password):

~~~
sudo npm install -g mapshaper
~~~

After this you are done. In my case, I was interested in simplifying a shapefile (located in my Dropbox) which I could complete with the following command (the % are the percentage of removable points to retain). The first shapefile listed is the input, and the second the desired output.

~~~
mapshaper /Users/alex/Dropbox/US_tract_clusters_new.shp -simplify 1% -o /Users/alex/Dropbox/US_tract_clusters_new_05pct.shp
~~~

Examples of the output:

![Original Shapefile](/public/images/orig.png)


![Simplified Shapefile](/public/images/new.png)

[Thanks to the developers](https://github.com/mbloch/mapshaper/graphs/contributors).
