---
title: Using Github flat to automate making geoportal boundaries as topojson
layout: post
---
Just a really quick note about a little resource I created to help with maps in the data visualisation team. The boundaries for loads of different areas are held on the ONS [geoportal](https://geoportal.statistics.gov.uk/). To turn them into files that we can use for our [map templates](https://github.com/ONSvisual/maptemplates), we had to do a few steps to rename fields and drop unnecessary fields to reduce the file size and turn it into the topojson file format. 

I have a [bash script](https://gist.github.com/henryjameslau/750474a16001bb77a1b7587047e63223#file-process_shapefile-sh) that I used to run on the zip files that I used to download and that was really quick but I saw [Github flat](https://next.github.com/projects/flat-data/) which can automate tasks and thought this would be great to regularly grab boundaries from the geoportal and convert them ready for our map templates. 

The end results is the repository [geoportal boundaries as topojson](https://github.com/henryjameslau/geoportal-boundaries-as-topojson) which is an always up to date place to look for boundaries files for our map templates. 

Here's an explanation of what it's doing.

## Step 1: Setup github flat

A [flat.yml](https://github.com/henryjameslau/geoportal-boundaries-as-topojson/blob/main/.github/workflows/flat.yml) file will instruct Github to run a workflow that will grab a .json file from the geoportal daily and save it [the file](https://github.com/henryjameslau/geoportal-boundaries-as-topojson/blob/main/geoportal.json) to the repo. This file lists all the boundaries available on the geoportal. 

## Step 2: Set up python for postprocessing

In the workflow, it says to [run postprocess typescript](https://github.com/henryjameslau/geoportal-boundaries-as-topojson/blob/main/.github/workflows/flat.yml#L29) after the file has been downloaded. However I'm not as familiar with how to process stuff in typescript so I'm following an [example](https://github.com/pierrotsmnrd/flat_data_py_example) where the [typescript file](https://github.com/henryjameslau/geoportal-boundaries-as-topojson/blob/main/postprocess.ts) loads up a python environment to do some analysis. 

## Step 3: Make the topojsons

The [python script](https://github.com/henryjameslau/geoportal-boundaries-as-topojson/blob/main/postprocess.py) loops through all the areas available and ignores anything that's not a boundary file, for example a lookup between different areas. It then looks strips out any unnecessary fields, renaming relevant fields and converts it to topojson for our map templates. And that's pretty much it, set it up once and let it run forever hopefully.

