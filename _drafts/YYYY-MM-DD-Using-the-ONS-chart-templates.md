The ONS chart templates allow us to quickly spin out charts to support articles. They are based off charts we've used a lot in the past and have been built in response to feedback and to incorporate features we need. The charts work well on mobile, are easily configurable through a config file, lightweight and embeddable. 

As with many things, our code borrows heavily from other people, so big shoutout to people who make their code freely available. 

## Getting your hands dirty

Time to make a chart. You've got a story, you know what you want to say.

### Step 1. Download the templates

Probably the simplest way is to download a zip file off github from the simple charts repository.  This contains templates for a variety of different charts. You could also fork the repo and use github pages.

### Step 1. Prep your data

In each folder, there will be a data file, normally called data.csv. You want to try and get your data to match it as much as possible, including the column headings. Some templates will read the heading automatically, but some templates refer to the column headings by name in the code so will need to keep them the same. 

### Step 2. Edit the config.json

Each chart has a config file that contains frequently changed variables such as annotations, aspect ratio, number of ticks on axis etc. Read the wiki pages to see how each variable changes the chart.

### Step 3. Preview the file

You can now see your finished visualisation using a browser. Firefox will run the code in the browser off local files but most browsers won't (Chrome, IE, Safari). In which case, you will either have to run a http server in the directory of your file, or put it up on github and use github pages. 

### Addendum - A few notes on pym.js

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