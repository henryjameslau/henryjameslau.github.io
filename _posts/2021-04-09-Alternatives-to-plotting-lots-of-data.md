---
title:Alternatives to plotting lots of data on a page
layout:post
---

Imagine you've got some data with a lot of series and data points over time. You've tried a line chart but there is just too much data. You want it to look good but what are your options for visualising it? 

###Option 1: Just plot the series that matter

It's more work but just reducing the number of series you plot leave you with just the most important data and a cleaner chart. This is easier to understand what's going on at a glance. The hard part comes in choosing which series to plot. 

From this
<div id="returntonormal5"></div>

to this
<div id="returntonormal2"></div>



###Option 2: Use a heatmap

Although this will depend on your dataset and how many timeseries you have. One option to plot data with a time element is to use a heatmap with time running left to right as this is convention (in some societies). This is useful for showing general patterns as you won't be able to show exact values with a colour scale. 

Here are some examples
<div id="heatmap2"></div>
<div id="heatmap1"></div>


### Option 3: Small multiples

Depending on whether what's interesting is happening to individual series rather than between series another option would be to plot each series on a mini chart and have small but multiple version of the chart, one for each series. It would be hard to rely on colour alone to distinguish each series if all the series were on the same chart. What you do lose out on is resolution so this solution is better when you want to look at overall patterns rather than the detail. You'll also want to keep the axis as similar as possible as you'll be naturally comparing across charts so if they are different scales it makes it easier to misread the chart. 

<div id="smallmultiple">
</div>
### Option 4: Multiline

You could plot all the series on one chart, often in a neutral colour and use some way to highlight with a stronger colour a particular series of interest, for example through a dropdown

<div id="dropdown"></div>

or hovering with the mouse

<div id="dropdown2"></div>

This puts the burden on the user to interact with the page to see what they are interested in or what is relevant to them. It also makes comparisons between series more difficult as you may have to select and remember. 

All these solutions have positives and negatives to them and it comes down to what you are trying to say with your chart. 

<script type="text/javascript" src="https://pym.nprapps.org/pym.v1.min.js">
<script>
var pymParent = new pym.Parent('returntonormal5', 'https://www.ons.gov.uk/visualisations/dvc1174/fig2/index.html', {});
var pymParent2 = new pym.Parent('returntonormal2', 'https://www.ons.gov.uk/visualisations/dvc1188/returntonormal/index.html', {});
var pymParent3 = new pym.Parent('heatmap1', 'https://www.ons.gov.uk/visualisations/dvc1234/heatmap/index.html', {});
var pymParent4 = new pym.Parent('heatmap2', 'https://www.ons.gov.uk/visualisations/dvc1263/figure-4-heatmap/index.html', {});
var pymParent5 = new pym.Parent('smallmultiple', 'https://www.ons.gov.uk/visualisations/dvc1276/reasonstoleavehome/index.html', {});
var pymParent6 = new pym.Parent('dropdown', 'https://www.ons.gov.uk/visualisations/dvc1273/vacsregional/index.html', {});
var pymParent7 = new pym.Parent('dropdown2', 'https://www.ons.gov.uk/visualisations/dvc938/timeseriesmultiline2/index.html', {});
</script>



