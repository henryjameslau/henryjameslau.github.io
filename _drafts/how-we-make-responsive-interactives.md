#How we use pym.js to make our interactives responsive

A few notes on pym. Pym.js is a javascript library developed by NPR. Pym is our way of embedding iframes so they behave responsibly. Normally with an iframe you specific height and width. With pym, you set up a parent page in our case the visual.ons wordpress blog or the main ONS site, and the visualisation is embedded in an iframe. The visualisation becomes the child. The child looks at the height of the body and tells the parent what size to change the iframe to. 

On the parent page, to set up a new child in your visualisation use

`new pym.Parent(parent_id, child_url);`

This tells pym to put the iframe in `parent_id` and the child element is from `child_url`.

When constructing the code, for the visualisation the code is made in such a way that the code that tells things what to do is made inside a function called drawGraphic. This function is called whenever the browser is resize and effectively redraws the whole graph. Because d3 is so fast it seems like the graph is changing as your change the size of the browser. 



In the child page, our visualisation, you can tell pym to sense the size of what's going on and resize the iframe accordingly. 





You can tell pym to fire whenever is resized by using
Function(drawgraphic){…..RenderCallback:drawgraphic}

Pymchild.sendheight() – tells the parent to resize.

Get the parent code set up in your cms. Other people use it like the BBC use it, so can just lift stuff straight from your site to theirs.

Can create wrapper that embeds child to test parent functions



Here's another way to make responsive graphics

https://brendansudol.com/writing/responsive-d3

