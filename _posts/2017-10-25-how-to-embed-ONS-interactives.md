---
layout: post
title: How to embed ONS interactives
---


At the end of some posts on [Visual.ONS](https://visual.ons.gov.uk/) is some code about how to use an iframe to embed any interactives elsewhere. This is to encourage syndication elsewhere, for example news organisations who might want to rewrite the words around an interactive to suit their style or readership.

## Using an iframe to embed

In [this article about house price by area](https://visual.ons.gov.uk/house-prices-how-much-does-one-square-metre-cost-in-your-area/) it says "To embed the floorplan in your site use the following code:"

```html
<iframe width="100%" height="1200px" src="https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html" scrolling="no" frameborder="0"/>
```

If you copied this into your website or CMS, this would make an iframe which acts like a window where the view is the ONS interactive. The window view is set with the `width="100%"` and `height="1200px"`. This will create a window that fills 100% of the width of where you put it and a height that's set manually. The width is sensed when the page is loaded and set to fill the whole width. The height should be set to something that doesn't cut off the bottom of the interactive.

This would work fine for most circumstances. But if you were changing the size of your window for example rotating your mobile or changing the resizing your browser, the width that was set when the page loaded would no longer correspond with the width of your browser.

## Making your embed responsive
We use a javascript library called [pym.js](http://blog.apps.npr.org/pym.js/) to make our interactives responsive. The basic idea is that on resizing, the interactives are redrawn to fit the new iframe. If the width of the interactive is small, like a mobile screen, the interactive is designed to behave differently.

To embed a responsive graphic, you need to use [pym.js](http://blog.apps.npr.org/pym.js/) on the site you're embedding on. This is quite simple to do if you can add scripts to your page. This website is referred to as the parent. The page you're embedding is called the child.


The example on the pym.js page says use code like this

```html
<div id="example"></div>
<script type="text/javascript" src="https://pym.nprapps.org/pym.v1.min.js"></script>
<script>

var pymParent = new pym.Parent('example', 'https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html', {});

</script>
```
## Code walkthrough
Let's talk through what's going on. First create a `div` and give it the `id=example`.

Next, load the pym.js script from the NPR website `<script type="text/javascript" src="https://pym.nprapps.org/pym.v1.min.js"></script>`.

Make another `<script>`, make a variable and then use a function to make this page a parent for pym.js `var pymParent = new pym.Parent(`.

Use the div id to say where to put it, in this case the `'example',` div.

Choose what will be the child page. This is going to be the interactive we've chosen and we get the page from the embed code in the article` 'https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html'`.

Then some more bit to say we're not using any of the optional extras `, {}` and finally close everything `);</script>`.

Hopefully that made sense. Now let's see it in action.

## Responsive embed
<div id="example"></div>
<script type="text/javascript" src="https://pym.nprapps.org/pym.v1.min.js"></script>
<script>

var pymParent = new pym.Parent('example', 'https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html', {});

</script>

## Non-responsive embed
Try resizing your browser or rotating your phone and compare this non-responsive version where the boxes don't resize.

<iframe width="100%" height="1200px" src="https://www.ons.gov.uk/visualisations/dvc434/floorplan/index.html" scrolling="no" frameborder="0"/>
