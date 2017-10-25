---
layout: post
title: How to embed ONS interactives
---


At the end of every post on [Visual.ONS](https://visual.ons.gov.uk/) is some code about how to use an iframe to embed any interactives elsewhere. This is to encourage syndication elsewhere by for example news organisations who might want to rewrite the words around an interactive to suits their style or readership. 

In [this article about house price by area](https://visual.ons.gov.uk/house-prices-how-much-does-one-square-metre-cost-in-your-area/) it says "To embed the floorplan in your site use the following code:"

```html
<iframe width="100%" height="1200px" src="https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html" scrolling="no" frameborder="0"/>
```

This would work for most people but it wouldn't be reponsive. 

## Making your embed responsive
We use a javascript library called [pym.js](http://blog.apps.npr.org/pym.js/) to make our interactives reponsive. The basic idea is that on resizing, the interactives are redrawn to fit the new iframe. If the width of the interactive is small i.e. a mobile screen, the interactive is designed to behave differently. 

To embed a responsive graphic, you need to use pym.js on the site you're embedding on. This is quite simple to do if you can add scripts to your page. This website is refered to as the parent. The page you're embedding from is called the child. 

The example on the pym.js page says use code like this

```html
<div id="example"></div>
<script type="text/javascript" src="https://pym.nprapps.org/pym.v1.min.js"></script>
<script>

var pymParent = new pym.Parent('example', 'https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html', {});

</script>
```
## Code walkthrough
Let's talk throught what's going on. First create a `div` and give it the `id=example`. 

Next, load the pym.js script from the NPR website `<script type="text/javascript" src="https://pym.nprapps.org/pym.v1.min.js"></script>`.

Finally make another `<script>`, make a variable and then use a function to make this page a parent for pym.js `var pymParent = new pym.Parent(`, put it in the `'example',` div, then choose what will be the child page` 'https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html'` then some more bit to say we're not using any of the optional extras `, {}` and finally close everything `);</script>`.

Hopefully that made sense. Now let's see it in action.

## Responsive embed
<div id="example"></div>
<script type="text/javascript" src="https://pym.nprapps.org/pym.v1.min.js"></script>
<script>

var pymParent = new pym.Parent('example', 'https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html', {});

</script>

## Non-responsive embed
Try resizing your browser or rotating your phone and compare this to the non-responsive version where the boxes don't resize.

<iframe width="100%" height="1200px" src="https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html" scrolling="no" frameborder="0"/>

