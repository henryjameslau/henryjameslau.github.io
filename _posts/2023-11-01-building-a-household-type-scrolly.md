---
title: Household composition by single year of age 
layout: post
---
A little while ago [Patrick Scott](https://twitter.com/patrick_e_scott?lang=en) spotted this interesting graphic about the [UK population by household type](https://twitter.com/resi_analyst/status/1100346740144852996) thinking it would be great over time. 

He also thought it would fit well into a scrolly format, similar to [this article looking at Donald Trump's finances](https://www.nytimes.com/interactive/2020/09/27/us/donald-trump-taxes-timeline.html) from the New York Times. 

Ahmad's been working on [svelte-components](https://github.com/ONSvisual/svelte-components) and I thought it would be a good time to try it out. Ahmad and Andrew have been working on using [storybook.js](https://storybook.js.org/) to make it more usable with [documentation](https://onsvisual.github.io/svelte-components/?path=/docs/intro--docs) of how to use the different component. There's a [scrolly](https://onsvisual.github.io/svelte-components/?path=/docs/templates-feature-article--docs) in the template so it was just a case of adapting that. 

However I did come across an issue when I was trying to implement the area chart. The way [svelte-charts](https://github.com/ONSvisual/svelte-charts) handles transitions is that it expects all the data to be present and it can't handle enter-exit. 

After a conversation with Ahmad about how best to handle this, we agreed to just set all the series to be zero except the first area and then transition to numbers as you scrolled so the lines are all there to start with. 

And here's the [scrolly about household type in action](https://main--regal-unicorn-29402c.netlify.app/).

I got the data from the [Create a custom dataset](https://www.ons.gov.uk/datasets/create) service where you can select different geographies and combinations of different variables at different levels of details. For this I chose England and Wales, all 101 ages and all 12 household types [link to dataset](https://www.ons.gov.uk/datasets/create/filter-outputs/acc41ec4-ec39-420c-a728-789d2ded3f01#get-data). 

I had to run some R code to condense the 12 categories down to something similar to the original image.

```R
df %>%mutate(hhtype=case_when(Household.type..12.categories..Code == 2 | Household.type..12.categories..Code==4 | Household.type..12.categories..Code == 6~ "Couple: Dependent children",Household.type..12.categories..Code == 3 | Household.type..12.categories..Code == 5 | Household.type..12.categories..Code ==7 ~ "Couple: No dependent children",Household.type..12.categories..Code == 1 ~ "One-person household",Household.type..12.categories..Code == 8 ~ "Lone parent: Dependent children",Household.type..12.categories..Code == 9 ~ "Lone parent household: No dependent children",Household.type..12.categories..Code == 10 ~ "Multi-person household: All students",Household.type..12.categories..Code == 11 ~ "Multi-person household: Other",.default = "Does not apply")) 
 df2%>%group_by(Age..101.categories..Code,hhtype) %>% summarise(obs=sum(Observation))
```
In the svelte code there are a couple of interesting bits to pull out. One is how it handles what data to present. Data for svelte chart is in a tidy data format and we want to filter multiple categories. I found an easy way of filtering by including the series to filter in an array and using this method as set out in this [stackoverflow answer](https://stackoverflow.com/questions/46894352/filter-array-of-objects-based-on-another-array-in-javascript). 

The generic format is `data.filter(d=>[array of series to filter by].includes(d.series))`. Previous I had said that we had to set the values to 0 if we don't want the line to be seen as it needs to be there so it doesn't enter in but not seen. We do this with a `.map` and if the series is in the ones to be included we return all the data, otherwise return 0. This is how it's handled in the demo.

```javascript
linechartdata = data.places.map(d=>{if(filterfuncs[e.detail.index].includes(d.hhtype)){return d}else{return {age:d.age,obs:0,hhtype:d.hhtype}}})
```
It's a bit hard coded to set it to zero and is a funny way round svelte charts but it works. 

