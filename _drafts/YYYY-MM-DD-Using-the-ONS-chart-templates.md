In my last post I talked about the structure of my team and how we work. This post goes into more about how we use templates for charts and interactives.

There are many charts we commonly use. Rather than remake these from scratch each time, we made templates. This allows us to make chart quickly and they include features commonly needed, for example annotations. 

The [ONS chart templates](https://github.com/ONSvisual/Simple-charts) makes charts are designed to work well on mobile, lightweight on the user's bandwidth and [embeddable using pym.js](http://henrylau.co.uk/2017/10/25/how-to-embed-ONS-interactives/). 

Each template is driven by a config file that specify certain variables that are needed. Using these templates, it should be possible to just add in your data and adjust the config to quickly produce charts. 



## Getting your hands dirty

Time to make a chart. You've got a story, you know what statistical relationships you want to show. 

### Step 1. Download the templates

Probably the simplest way is to [clone](https://help.github.com/articles/cloning-a-repository/) or download a zip file off github from the [Simple Charts repository](https://github.com/ONSvisual/Simple-charts).  This contains templates for a variety of different charts. You could also fork the repo and use github pages.

### Step 1. Prep your data

In each folder, there will be a data file, normally called data.csv. You want to try and get your data to match it as much as possible, including the column headings. Some templates will read the heading automatically, but some templates refer to the column headings by name in the code so will need to keep them the same. 

### Step 2. Edit the config.json

Each chart has a config file that contains frequently changed variables such as annotations, aspect ratio, number of ticks on axis etc. Read the [wiki pages](https://github.com/ONSvisual/Simple-charts/wiki) to see how each variable changes that particular template.

### Step 3. Preview the file

You can now see your finished visualisation using a browser. Firefox will run the code in the browser off local files but most browsers won't (Chrome, IE, Safari). In which case, you will either have to run a http server in the directory of your file, or use github pages. 

Now you've made your chart with the ONS templates, you can stop worrying about how your graph is going to behave on mobile and you can work on all the other important bits - annotations, title, the words around the graphic, the structure, etc. 

