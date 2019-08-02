---
layout: post
title: Running a population model in the browser
---

Over a year ago, I started work on a project looking at our ageing population and specifically one measure called the Old Age Dependency Ratio (OADR). This measure compares the number of people who are above the retirement age to people of working age (16 to retirement age). 

Although this measure has its limitations because people are delaying joining the workforce because of education and people are working past their retirement age, it is still useful when comparing internationally and still gives an indication of the financial implications of our population when considering pensions and health care for example.

We wanted to explain a bit more about what factors were involved in how this OADR ratio changed in the future. Some variables have more of an effect than others. 

We wanted an easier way to understand the technical aspect behind demography and modelling population in the future.

We also want to dispel the misconception people may have had about migration and the magnitude of the effect it would have on the population. 

We wanted to use an interface that brought elements of gamification. 

At the end of June, this project was finally published - [How would you support our ageing population](https://www.ons.gov.uk/peoplepopulationandcommunity/birthsdeathsandmarriages/ageing/articles/howwouldyousupportourageingpopulation/2019-06-24). 

### The Excel beginning 

My starting point was an excel model that colleagues in the office had built that use the National Population Projection variants. This excel sheet calculated the population given some numbers about fertility, migration and mortality. 

By using different variations you could see what choices your did to the population. There was a custom option where you could enter your own numbers but you had to enter something for every age and every year. This isn't really something that's intuitive. And the results it gave was a table of the population at each age over each year. 

This spreadsheet did give you a lot of combinations to play about with but it still wasn't something you could do easily in the browser. 

### Building it for the browser

Once I got my head round the calculations in the excel sheet (using a lot of the excel function Trace dependents). I had to then think about what people would change, and trying to get this down to one input. In the end I decided to fix a target amount 25 years down the line for the three inputs (mortality, migration and fertility), with some linear interpolation along the way. I scaled the single year of age numbers by an amount to match the interpolated target for each year. I did this in Excel and showed this to the business area for them to approve.

Mortality was the difficult one. There are cohort effects which travelling through age groups. Also using something like life expectancy at birth, while familiar to people, is not sensitive to changes at the higher ages. And it's these higher ages where we are interested in. In the end we settled on displaying the life expectancies associated with 5 mortality variants and the slider snaps to these values. 

Once they were happy with the process, I recreated the calculations in the browser. In Excel, it's hard to see the order of things as it just appears to run all at once, but in JavaScript it's much more linear. It's actually quite simple, just doing a lot of adding and subtracting for people migrating in or being born and dying. And looping over the years into the future.

### The interface

We wanted a simple way to interact with the controls and I found [d3-simple-slider](https://github.com/johnwalley/d3-simple-slider), a library for making sliders. Initially we had 4 sliders going horizontally but this took up quite a lot of space so we went for 4 vertical ones which looked like a mixing desk.

![Sketch of design](http://henryjameslau.github.io\_media\screenshot_2019-03-28_at_12.09.05.png)

The sliders took a bit of extra styling and messing around with the library so it's ended up quite customised but I'm pleased with the result. For mobile, we show one horizontal slider at a time and store the results in hidden inputs. 

We used tooltips to add in extra information where something might have been misinterpreted. 

### Displaying the results

The population models reruns every time you change any of the sliders or inputs and updates the results you see on the page. Keeping the results in view was important so you could see your changes happening in front of your eyes. 

Other examples we'd seen include an FT example where you had to decide how you'd spend the BBC licensing fees between the stations and channels.

We also wanted to give feedback about what people's choices were in respect to todays numbers and what it would mean for them. This is done in a couple of ways, there's the text box that spells out what the numbers are but also lines on the sliders to indicate 2017 levels. 

### Technical achievements

It's the first d3.v5 project we've done in the team. I decided to do this because v5 uses promises so you have more control when code block executes. This avoided doing calculations without the numbers from the previous step.

I've learnt a lot more about how to use bootstrap-grid properly. [Bluebird.js](http://bluebirdjs.com/docs/getting-started.html) to compatibility promises for IE. [Tippy.js](https://atomiks.github.io/tippyjs/) for tooltips.

## What did we learn

We used Google Tag Manager to find out how people were using the tool and what they were inputting. 

We looked at the OADR in 2042 people were getting from their chosen inputs. The biggest peak is from loading the interactive and people making small changes. The periodic jumps are from people changing the pension year. What's interesting to note is the secondary peak around 300. This is because people are trying to match the 2016 level of OADR. We put feedback into the results box and it's clear this element of gamification is helping. 

<iframe title="What happened to the OADR with people's inputs" aria-label="Interactive line chart" id="datawrapper-chart-ASdhA" src="//datawrapper.dwcdn.net/ASdhA/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="400"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",function(a){if(void 0!==a.data["datawrapper-height"])for(var e in a.data["datawrapper-height"]){var t=document.getElementById("datawrapper-chart-"+e)||document.querySelector("iframe[src*='"+e+"']");t&&(t.style.height=a.data["datawrapper-height"][e]+"px")}})}();</script>
We can also see that people like round numbers as well as the ends of the scales. Here's what users selected for migration with peaks on the hundred thousands.

<iframe title="What users selected for migration" aria-label="Interactive line chart" id="datawrapper-chart-2Dv7Y" src="//datawrapper.dwcdn.net/2Dv7Y/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="400"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",function(a){if(void 0!==a.data["datawrapper-height"])for(var e in a.data["datawrapper-height"]){var t=document.getElementById("datawrapper-chart-"+e)||document.querySelector("iframe[src*='"+e+"']");t&&(t.style.height=a.data["datawrapper-height"][e]+"px")}})}();</script>

And here's fertility. The peak around 1.75 is when the model loads. There's big peak around the round numbers (1,2,3) and the ends of the scales. 

<iframe title="What users chose for fertility" aria-label="Interactive line chart" id="datawrapper-chart-PVl0W" src="//datawrapper.dwcdn.net/PVl0W/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="400"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",function(a){if(void 0!==a.data["datawrapper-height"])for(var e in a.data["datawrapper-height"]){var t=document.getElementById("datawrapper-chart-"+e)||document.querySelector("iframe[src*='"+e+"']");t&&(t.style.height=a.data["datawrapper-height"][e]+"px")}})}();</script>



### Feedback

We are still collecting feedback about the tool but here two choice picks that show that we are meeting the aims of the project. 

<blockquote
 class="twitter-tweet"><p lang="en" dir="ltr">Superb <a 
href="https://twitter.com/hashtag/interactive?src=hash&amp;ref_src=twsrc%5Etfw">#interactive</a>
 <a 
href="https://twitter.com/hashtag/dataviz?src=hash&amp;ref_src=twsrc%5Etfw">#dataviz</a>
 in support of a more informed and thoughtful electorate. I like this. 
Of course it raises many more questions but you have to start somewhere.
 I&#39;m about to visit my parents in-law but maybe I won&#39;t 
show them this. <a 
href="https://t.co/lZvjzGkXgK">https://t.co/lZvjzGkXgK</a></p>&mdash;
 Robert Grant (@robertstats) <a 
href="https://twitter.com/robertstats/status/1143128036642041856?ref_src=twsrc%5Etfw">June
 24, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" 
charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">This whole thread is essential reading. The UK population is ageing fast, and this will have more impact on public spending than even the most extreme model for immigration. Pretty much everything in our current crisis comes from people wrongly thinking it&#39;s the other way round. <a href="https://t.co/t3mzOJVQmw">https://t.co/t3mzOJVQmw</a></p>&mdash; Matt Locke (@matlock) <a href="https://twitter.com/matlock/status/1143146862142210049?ref_src=twsrc%5Etfw">June 24, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 
During the project, we found out there was another project looking at an alternative measure to the OADR. We decided to align the projects and this took a bit of extra time and effort and changed the way the article turned out as we referenced each other. We also felt it diminished the impact we could have had with the media. 

Overall, I'm happy with how the project turned out. People are using the tool and taking the messages away that we wanted them to leave with. Now with a working population model that projects into the future we can use it for future projects. If you've got any good ideas, let me know.