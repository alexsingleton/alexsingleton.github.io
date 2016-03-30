---
author: Alex Singleton
layout: post
title: 2011 Census Open Atlas Project
categories:
- r
---

![CensusAtlas](/public/images/CensusAtlas.jpg)This month has seen the release of the 2011  census data for England and Wales at Output Area Level.

This offers the possibility to map various attributes about people and places for very small geographic areas. Output Areas represent the most detailed geography for which Census data are released and are the building blocks for many popular products such as geodemographic classifications.

Because the data and boundaries are available under an [open government licence](http://www.nationalarchives.gov.uk/doc/open-government-licence/), and that these data have been usefully placed online as direct downloads ([data](http://www.nomisweb.co.uk/census/2011/bulk/r2_2), [boundaries](http://www.ons.gov.uk/ons/guide-method/census/2011/census-data/2011-census-prospectus/new-developments-for-2011-census-results/2011-census-geography/2011-census-geography-prospectus/index.html)), it makes it  possible to create maps for England and Wales in a highly automated way.

As such, since launch of the Output Area level data I have been busy writing (and then running - around 4 days!) a set of R code that would map every Key Statistics variable for all local authority districts. The code for doing this is fully reproducible, and I have dropped this on my [Rpubs blog](http://rpubs.com/alexsingleton/openatlas).

<u>**[THERE IS A NEW VERSION OF THE ATLAS AVAILABLE HERE](/r/2014/02/05/2011-census-open-atlas-project-version-two/)**</u>

All maps can be downloaded here: [https://data.cdrc.ac.uk/product/cdrc-2011-census-open-atlas](https://data.cdrc.ac.uk/product/cdrc-2011-census-open-atlas)

**[IF YOU THINK ANY OF THE INFORMATION I HAVE CREATED IS USEFUL, INTERESTING OR OF VALUE, THEN PLEASE  READ THIS BLOG POST AND HELP PROTECT THE NEXT CENSUS!](http://cdublogger.wordpress.com/2013/02/04/small-area-population-data/)**

## Why have I created these atlases?

  1. To demonstrate the value of the 2011 census
  2. Provide a free 2011 static Census atlas to anyone who wants one
  3. Because I do not believe web maps should necessarily be the default way of distributing geographic data
  4. To illustrate how open data and software can be used in creative ways to generate insight
  5. An attempt to save local authorities money who might be thinking of doing these type of analyses themselves
  6. To provide reproducible code that enable others to generate similar maps at Output Area level
  7. For fun!
  8. [Because R is awesome!](http://www.r-project.org)
  9. [Because R really is awesome!](http://www.r-project.org)

## What is in each atlas?

Each atlas contains a series of vector PDF maps for each Key Statistics variable. The following is a map from the Liverpool Atlas and shows the percentage of "White: English/Welsh/Scottish/Northern Irish/British" for each Output Area in Liverpool.
[![white](/public/images/white-227x300.jpg)](/public/images/white.jpg)

## About the data and maps
Almost every non count variable (apart from Hectares) was mapped from the  Key Statistics data disseminated by Nomis, and are either percentage scores or some type of ratio / average. Maps were excluded where there were only a few scores within a local authority district - you can see further explanation of this on the Rpubs page accompanying the analysis. A couple of further points...

  * The variables mapped were based on the calculations that were part of the Nomis data.
  * I have always been a fan of blue choropleth maps which was why the particular colour scheme was chosen.
  * The cartography was automated for all the maps - this means it is more successful for some local authority districts than in others. Some issues I have noted;
  * Those local authorities with many wards appear a little busy with labels (e.g. [Cornwall](http://138.253.67.7/~alex/downloads/openatlas/E06000052.pdf))
  * [Cardiff ](http://138.253.67.7/~alex/downloads/openatlas/W06000015.pdf) appears to have a rogue polygon which may be issue with the OA to higher geography lookup table. I will investigate this in a future release.... [Power of the crowd reveals that this is in fact [Flat Holm island ](https://maps.google.co.uk/?ll=51.377781,-3.120117&spn=0.079182,0.138016&t=h&z=13)- thanks to [@geospacedman](https://twitter.com/geospacedman)]
  * It would be nice to add scale bars and north arrows to the maps, however, this was proving to be problematic when outputting to PDF. Again, I will try and fix this in a future release.
  * The boundaries used are the generalised files to increase mapping speed and reduce file size - these could be supplemented for the full resolution boundaries in the future
  * These maps are without guarantee or warranty / [feel free to fix my code](http://rpubs.com/alexsingleton/openatlas)!

