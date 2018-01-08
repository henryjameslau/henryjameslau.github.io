---
layout: post
title: How to use ONS charts - The preamble
---


The ONS charts have developed in a way that suits our work. To explain how to use them and what type of work they'd be good for read on. If you don't want to read this, skip to [getting your hands dirty](\#handsdirty).

## The goals of the work

The principles of the ONS strategy is laid out in the document "Better Statistics, Better Decisions". In it, it describes many of the principles that guide our work. These include

1. Inform decision making
2. Support democratic debate
3. Improve communication
4. Challenge misuse of statistics

As a result, there is an increased focus on working to the ["enquiring citizen"](https://digitalblog.ons.gov.uk/2014/04/02/the-persona-touch/) persona. In the same way that [research is putting much focus and effort into communicating with the public](http://www.rcuk.ac.uk/innovation/impacts/), the ONS as a statistics bodies is trying to do the same. Our work aims to communicate statistics in a way that support these principles. And the area of work that mostly correlates to that is data journalism; using data and statistics to tell stories that matter to people.

ONS data are published in many many excel files. With each release, a commentary and analysis is published but these are often technical documents with enough detail for the expert user. If you are an expert you'll be familiar with the website you'll be able to find the data and understand everything about it. If you're in an "information forager", you might persist with different search terms and then eventually find your way to what you think might be the right data so you download it and see. Repeat a few times until you find what you really want. The vast majority would turn away at just opening a spreadsheet. We are failing these people. And if we really want to improve the world we need to make sure these people have the information they need to have important conversations. This is where the digital content team comes in. 

## How we work

The team is multidisclipinary and is made up of journalists, designers and developers. 

ORG CHART

The journalistic skills are important for transforming the information about statistics in to something that accurate to the data yet understandable to average citizen. The design and coding skills are about making something that presents the data using the best bits of digital, the ability to reach a large amount of people, in a way that is quick to produce and can be interactive.  



### Generating an idea

Since we are the ONS we have access to vast troves of data that the organisation collects. Each department is in charge of statistics that relate to certain areas eg. HALE (Health and Life Events) - read birth, deaths and marriages. These what we refer to as business areas are the expert in their data and are responsible for how their data is represented. Sometimes they will have found something interesting in their research and feel bringing this to the attention of people will benefit them so they look to us to help them. Or they'll have a big release coming out and you know they'll be some interesting stories to tell there. Some times we are digging around the data published and we find something interesting to we approach the business area to get their opinion of what we've found. 

As the ONS is a large organisation, visibility is an issue to getting to know people and having regular meetings are essential. People need to uderstand what you're trying to do and why so they can support you and commit enough resources. 

### Exploring the data

Once you've found a good idea, it's time to really hone in on what the headline is going to be. What's going to make someone stop and read your article and listen to what you have to say. This takes time, as some times an idea is great but when you look into it, there's more to it. You need to analyse the data. This step uses tools like excel, python or charting tools like plotly, tableau, rawgraphs or datawrapper. It's often best to get feedback from all sides including editorial and the business area on your idea to hone it's focus, check it's viability and ensure it's rigorous. 

### Commission

Once your idea is firm, it is written up as a proforma and send to an internal group Editorial and Comms Group (ECG) made up of deputy directors for each business area. The proforma contains the outline of what you want to say, how you're going to say it, the risks, external factors, other angles. They look over the idea to ensure it's aimed at the right level with the right focus and any concerns are addressed. 

### Development

The article is written and any charts or interactives are developed. Often charts use our templates and if necessary are adjusted to fit the story. Our templates have come out of what have worked in the past and use the most common elements of interactives. The development of interactives and the article happens with regular feedback from the editorial, design and UX as well as the business area. These is the part where the disclipine of data visualisation becomes important as choosing the right chart to tell the story is paramount. I would suggest the FT's visual vocabulary as a starting point. Not forgotten is the digital standards we are working towards including working on a mobile and accessibility. 

 ### Publish

Once it's all finished the article is published. Often we are looking for organisations to syndicate the content so elements are made to be embedded into other people's system. We track how the content goes down with partners, through different distribution channels. 

### Why it works for us

So now you know how the team works you can see why the templates work for us. They allow us to quickly spin out charts to support articles. The charts work well on mobile, are easily configurable, lightweight and embeddable. 

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

