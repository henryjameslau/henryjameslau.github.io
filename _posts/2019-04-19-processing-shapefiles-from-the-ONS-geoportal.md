---
layout: post
title: Processing shapefiles from the ONS geoportal
---

Our [map templates](https://github.com/ONSvisual/maptemplates) can work with different types of geography (local authority, regions, CCG, LSOA, MSOA etc). The problem is that these geographies are often updated. Luckily we have a canonical source of geographies in the [ONS Geoportal](http://geoportal.statistics.gov.uk/). 

To get the various geographies to work with our templates, we have to rename the columns and get rid of any extra information that we don't need. We could do this in QGIS and it would take about 5 minutes. 

But why wait 5 minutes when it could be done in 5 seconds! Hello [bash script](https://gist.github.com/henryjameslau/750474a16001bb77a1b7587047e63223). 

You'll need download the script, make it executable with `chmod u+x process_shapefile.sh` and copy it to `/usr/local/bin`. 

Next point the script at a zip file of a shapefile download from the geoportal.

It will unzip and inside with be a .`topojson` file called `geog.json` which you can use in the templates. 

<div style='position:relative; padding-bottom:calc(70.80% + 44px)'><iframe src='https://gfycat.com/ifr/miniatureweebrownbutterfly' frameborder='0' scrolling='no' width='100%' height='100%' style='position:absolute;top:0;left:0;' allowfullscreen></iframe></div>



