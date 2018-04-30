#How to make responsive d3.js interactives

What happens to our visualisations on a mobile is important. To reach people with our content, we need to make it syndicatable; to make it syndicatable we need it to work on mobile. 



We do a few things to make our interactives work on mobiles. 

## Breakpoints

We use three breakpoints for our interactive (roughly mobile, tablet, desktop). The interactives may behave differently or we may choose to show or not show bits depending on if there's space. 

We sense the width of the body or a div on the page where we want to put stuff.

`d3.select("body").style("width")`

which gives us something like

`"800px"`.

We just need the 800 part so we can add `parseInt()` in front so it's now `parseInt(d3.select("body").style("width"))`

Now we know the width of our browser we can make our interactive accordingly. Some of the things we change in respect to the width are

- height of the svg is calculated with an aspect ratio and the width
- margins


- tick formats, going from 2008 on desktop to '08 on mobile
- the number of ticks
- which annotations to show and and where they appear.

One thing to note is that the width is only sensed when that code is run which is normally on load. The interactive may load great, but if the browser is resized it may no longer optimally fit. This is where pym comes in.

## pym.js

[pym.js](http://blog.apps.npr.org/pym.js/) is a javascript library developed by NPR. pym is our way of embedding iframes so they behave responsibly. 

Our interactives are built as standalone and embedded as iframes into webpages. They are embedded into our reports, but that means they can be embedded anywhere. 

Normally with an iframe you specify the height and width. With pym, the height of the iframe is detected and adjusted automatically. This means the iframe can change size with the interactive. 

pym works as a parent-child relationship. The parent page is the place where the interactive will be embedded in an iframe. In our case, the parent is the main ONS site. The interactive, which is a standalone page in itself, is the child. 

On the parent page, to set up a new child in your visualisation use

`new pym.Parent(parent_id, child_url);`

This tells pym to put the iframe in `parent_id` and the child page is from `child_url`.

On the child page side, our interactive, we need to tell pym this is a child page. This is done with `pymChild = new pym.Child();`. 

To make the content resize when the browser changes, we need to structure our code in a certain way. We make a function that contains everything to draw the graphics. This function is called `drawGraphic` and is fired every time the browser is resized by adding a renderCallback to the pym when we set it up. So now we start pym with `pymChild = new pym.Child({ renderCallback: drawGraphic});`. 

This means that the interactive is destroyed and redrawn when the browser is resized. Because d3.js is so fast it seems like the graph is changing as your change the size of the browser. 

As part of `drawGraphic` we can set pym to tell the parent page how big the child is and set the right iframe size to fit the child. This is done with `pymChild.sendHeight();`. This is normally left until the end once everything has been drawn. 

One thing we have to be careful with is when we are developing, we are often working on the child page. It's only when the interactive is embedded in a parent page do we see whether the iframe is resizing properly. We use a dummy parent page to test the iframes are resizing correctly. 

Other organisations like the BBC already use pym.js so it makes it easier from them to life our interactives into their site.

## Bootstrap Grid

Finally, we use the [bootstrap grid](https://getbootstrap.com/docs/4.0/layout/grid/) to make content blocks flow under each other depending on the width of the browser. We can also hide and show certain elements for mobile. 

## Postscript

On a side note, I came across [another way to make responsive SVGs](https://brendansudol.com/writing/responsive-d3) from the [d3js Slack group](https://d3-slackin.herokuapp.com/). 



