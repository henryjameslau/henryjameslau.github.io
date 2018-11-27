---
layout: post
title: National Trust Project
---
When I moved jobs to work at the Office for National Statistics, I moved from London to Hampshire. And I had suddenly had more places to visit. Some of these places were National Trust, some were English heritage. I wanted to know would I visit enough places to merit buying membership. 

I wanted to build a calculator where you put in your group size (adult, pair of adults, family) and whether you wanted to pay gift-aid or not. You could then see a map with National Trust attractions and you could click to add the one you might visit and if would tell you if that total amount went over the threshold of membership and it was better value to get membership. 

This ended up being quite complicated to I decided to make a MVP (minimum viable product) of a map with all national trust attractions with prices for adults with gift-aid.

<div class="flourish-embed" data-src="visualisation/167193"></div>undefined<script src="https://public.flourish.studio/resources/embed.js"></script>

## Methodology
First had to [scrape](https://github.com/henryjameslau/national-trust-scraper/blob/master/Scraper/Nat%20Trust.ipynb) the National Trust website. This was my first go at learning how to scrape with python and it was quite easy. Thanks to [Jure](https://twitter.com/JureStabuc) for teaching me. 

Second, I found out each National Trust place comes with the titles for it's tickets. For example there was 

> 1 adult and up to 3 children
>
> 1 adult & up to 3 children
>
> 1 adult 3 children

So I used OpenRefine to cluster these into one entry. [Here's the data that's been cleaned and clustered](https://github.com/henryjameslau/national-trust-scraper/blob/master/Scraper/NatTrust-clustered.xlsx). 

I realised I had scraped my data in a funny way to used the reshape packed in R to fiddle about with it. The plan to make a calculator was out the window so I just filtered the data for an adult paying gift aid. Now my data was ready to map. 

I wanted a simple map to just show places and allow people to click through and see what was around their area and prices. I settled on using [flourish](https://flourish.studio/) and was impressed with the configurability of their maps. 

Lesson for future me is to get into the mindset of not letting projects drag on and getting overwhelmed by their scope and just make something. 

