They allow us to quickly spin out charts to support articles. The charts work well on mobile, are easily configurable, lightweight and embeddable. 

## Getting your hands dirty

Time to make a chart. You've got a story, you know what you want to say.

### Step 1. Download the templates

Probably the simplest way is to download a zip file off github from the simple charts repository.  This contains templates for a variety of different charts. You could also fork the repo and use github pages.

### Step 1. Prep your data

In each folder, there will be a data file, normally called data.csv. You want to try and get your data to match it as much as possible. Including the column headings. Some templates will read the heading automatically, but some templates refer to the column headings by name in the code so will need to keep them the same. 

### Step 2. Edit the config.json

Each chart has a config file that contains frequently changed variables such as annotations, aspect ratio, number of ticks on axis etc. Read the wiki page to see how each variable changes the chart.

### Step 3. Preview the file

You can now see your finished visualisation using a browser. Firefox will run the code in the browser off local files but most browsers won't (Chrome, IE, Safari). In which case, you will either have to run a http server in the directory of your file, or load it up on github and use github pages. 

### Addendum - A few notes on pym.js

A few notes on pym. Pym.js is a javascript library developed by NPR in America. Pym is our way of embedding iframes so they behave responsibly. Normal with an iframe you specific height and width. With pym, you set up a parent page in our case the visual.ons wordpress blog, and the visualisation is embedded in an iframe. The visualisation page becomes the child. The child looks at the height of the body and tells the parent what size to change the iframe to. 

To set up a new child in your visualisation use

Var pymchild = new ….

This calls pym and tell it there’s a child element.

You can tell pym to fire whenever is resized by using
Function(drawgraphic){…..RenderCallback:drawgraphic}

Pymchild.sendheight() – tells the parent to resize.

Get the parent code set up in your cms. Other people use it like the BBC use it, so can just lift stuff straight from your site to theirs.

Can create wrapper that embeds child to test parent functions