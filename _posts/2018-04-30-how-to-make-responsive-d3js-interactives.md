---
layout: post
title: How to make responsive d3.js interactives
---
What happens to our visualisations on a mobile is important. To reach people with our content, we need to make it syndicatable; to make it syndicatable we need it to work on mobile. 



We do a few things to make our interactives work on mobiles. 

## Breakpoints

We use three breakpoints for our interactive (roughly mobile, tablet, desktop). The interactives behave differently at different widths or we may choose to show or not show bits depending on if there's space. 

We sense the width of the body or a div on the page where we want to put stuff using `d3.select("body").style("width")` which gives us something like `"800px"`.

We just need the 800 part so we can add `parseInt()` in front so it's now `parseInt(d3.select("body").style("width"))`.

Now we know the width of our browser we can use this to set bits of our interactives. Some of the things we change in respect to the width are

- the height of the svg is calculated with an aspect ratio and the width
- margins
- tick formats, going from 2008 on desktop to '08 on mobile
- the number of ticks
- which annotations to show and and where they appear.


One thing to note is that the width is only sensed when that code is run, which is normally when the page is loaded. The interactive may load great, but if the browser is resized it may no longer fit. This is where pym comes in.

## pym.js

[pym.js](http://blog.apps.npr.org/pym.js/) is a javascript library developed by NPR. Our interactives are built as standalone pages and embedded as iframes. They are embedded on the ONS site, but they can be embedded anywhere. Using pym makes our embedded iframes behave responsively. 

Normally with an iframe you specify the height and width. The content of the page will change depending on the width, for example text may wrap and then the height changes too. With pym, the height of the iframe is detected and adjusted automatically. This means the size of the iframe can change responsively. 

### How pym works 

pym works as a parent-child relationship. The parent page is the place where the interactive will be embedded in an iframe. In our case, the parent is the main ONS site. The interactive, which is a standalone page in itself, is the child. 

On the parent page, set up pym with

`new pym.Parent(parent_id, child_url);`

This tells pym to put the iframe in a div with the id `parent_id` and the child page is `child_url`. That's it for the parent. Most of the work is done on the child page. 

On the child page, our interactive, we need to tell pym this is a child page. This is done with `pymChild = new pym.Child();`. 

To make the content resize when the browser changes, we need to structure our code in a certain way. We make a function that contains everything to draw the interactive. This function is called `drawGraphic`. We tell pym to fire `drawGraphic` every time the browser is resized by adding a renderCallback when we set up pym. Now we instead start pym with `pymChild = new pym.Child({ renderCallback: drawGraphic});`. 

As part of the `drawGraphic` function we can set pym to tell the parent page how tall the child page is. This sets the iframe's height on the parent page to fit the child's height. This is done with `pymChild.sendHeight();`. This is normally left until the end of `drawGraphic` once everything has been drawn. 

Resizing the page destroys the interactive, calls the function `drawGraphic` and everything is redrawn. Because d3.js is so fast it seems like the graph is changing as your change the size of the browser. However if you have delays or transitions, it will reset them on resizing. 

When we are developing our interactives we are working on the child page. Issues with the iframe resizing may not appear so it's important to test with a dummy parent page before publishing. 

Other organisations like the BBC already use pym.js so it makes it easier from them to lift our interactives into their site.

## Bootstrap Grid

Finally, we use the [bootstrap grid](https://getbootstrap.com/docs/4.0/layout/grid/) to make content blocks flow under each other depending on the width of the browser. We can also hide and show certain elements for mobile. 

## Postscript

On a side note, I came across [another way to make responsive SVGs](https://brendansudol.com/writing/responsive-d3) from the [d3js Slack group](https://d3-slackin.herokuapp.com/). 



