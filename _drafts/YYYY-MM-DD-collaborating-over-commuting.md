---
layout: post
title: Commuting: a case study on collaborating
---

Commuting; most people do it, most people hate it. We know [men do more of the longer commutes](https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/employmentandemployeetypes/articles/thecommutinggapmenaccountfor65ofcommuteslastingmorethananhour/2018-11-07) and our newest analysis published at the beginning of September showed that [women are more likely to leave their job over a long commute](https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/earningsandworkinghours/articles/thecommutinggapwomenaremorelikelythanmentoleavetheirjoboveralongcommute/2019-09-04). 

Our article was picked up in a few places but most notably by the [Government Equalities Office then minister Amber Rudd said](https://www.gov.uk/government/news/women-pick-jobs-closer-to-family-over-bigger-salary-as-government-promises-to-help-them-reach-their-financial-potential), 

> “Women across the country struggle to find a balance between being a parent and their job.

> “These statistics show how women are likely sacrificing a larger paypacket, and career growth, because they are doing the bulk of childcare and unpaid work - like taking care of elderly relatives and their home.
>

It felt like the success was down to this being our most collaborative project yet.  

## The idea

In January I was trying to get an idea off the ground around who does the same commute as you. I emailed some people in our policy team, that lead to another meeting with our labour market team. The meeting notes got circulated round to even more people.

From those meeting notes, Tom Williams got in touch with Phil Leake, a data journalist in our team, to show him some work that Vahé in methodology had done looking at the gender differences in commuting distance. Once we put those two elements together, we had the core of our idea. 

#### Takeaway 1: Putting the right people together takes multiple attempts

We explored a few different avenues of how else we could pull in additional information. I asked people who had worked on admin data whether we could get information about parents but this wasn't feasible. 

#### Takeaway 2: Explore possible avenues early but close down ones that don't look fruitful

But we had seen the Data Science Campus talk about another project using a trip planner to calculate travel time. 

## Calculating commuting time

The Data Science Campus project [access to services](https://github.com/datasciencecampus/access-to-services) looked at how people could travel to difference services, for example GPs, and whether there were black spots. For this project, they had created a tool called [propeR](https://github.com/datasciencecampus/access-to-services/tree/develop/propeR) which run analysis on batches of locations. 

I thought we could use this tool to calculate the commute times instead of using commute distance. We needed a bit of help and the people at the Data Science Campus, especially Michael Hodge, got us up and running with propeR and supplied the necessary public transport timetables. We adapted their open source code to run better for our task which was throwing a million home-work postcodes pairs at it. 

#### Takeaway 3: Keep your networks wide

Although the trip planner was great, it was very fussy about the starting point, it had to be on a road, but we were using the lat-lon of the centroid of a postcode which isn't necessarily on a road. I was a bit stuck on how to fix this so I reached out to the government data science community over slack and asked for some advice. 

Someone from Hackney council suggested using [Open Source Routing Machine](http://project-osrm.org/) which worked.

#### Takeaway 4: Seek help when needed

It took until April to get to a point where I could start crunching the big datasets and to speed things up I took over other people's computers. During this time Vahé also presented the gender difference of commuting distance at the ONS Economic Forum event for comments. 

## Bringing it together

Once the dataset of travel times had been pulled together, it was fairly quick to rerun the analysis using time instead of distance. This helped with making our story more credible and more relevant to people. 

We had regular catch-ups every few weeks until the publication. The core digital content team was Rachel our designer, Phil the data journalist and myself from the data visualisation side. We were joined by Roger Smith and Tom Williams from Labour Market and Vahé from Methodology. 

#### Takeaway 5: Bring together the right mix of skills 

#### Takeaway 6: Regular communication is key, have face-to-face meetings when you need them

There was lots of cross-over of people's expertise. I remember Roger commenting on some draft graphs that made them lots better. There's a risk for egos to become involved but it was really apparent that people were focussed on creating something that really worked for the user.

#### Takeaway 7: Put respect, equality and a common goal at the core of the team

We had hoped to launch the project with a media partner but unfortunately that didn't work out.

#### Takeaway 8: Sometimes things don't go the way you plan and you have to make the most of it

