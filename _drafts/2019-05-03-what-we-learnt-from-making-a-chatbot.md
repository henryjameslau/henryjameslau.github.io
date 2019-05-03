---
title: What we learnt from making a StatsBot
layout: post
---

At the end of March, the ONS published an article looking at [the types of jobs at risk from automation](https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/employmentandemployeetypes/articles/whichoccupationsareathighestriskofbeingautomated/2019-03-25). We thought it would be ironic to be able to query the results through a chatbot interface. 

[Other journalism organisations are using chatbots to explain complex topics](https://www.niemanlab.org/2018/02/with-in-article-chat-bots-bbc-is-experimenting-with-new-ways-to-introduce-readers-to-complex-topics/). They've said that although not every one engages with the chat bots, when people do they have a deep engagement.

I have to say that [Jure](https://twitter.com/JureStabuc) almost all the work on this project. Our first challenge was finding a chatbot library that didn't involve any backend. In the end, we found [chat-bubble](https://github.com/dmitrizzle/chat-bubble) that runs completely off javascript. 

Design was also a challenge. With the BBC chat bots, it's basically multiple choice buttons and it gives you different answers depending on which button you choose. The data we had was about the risk of automation to occupation and also who was doing that job for example gender, region, age. 

We designed a few questions to try to figure out all these characteristics through elimination, e.g. what decade were you born in? with the answers being 60s, 70s, 80s, 90s, 00s.

What was more difficult was trying to work out occupation. You could ask people to try to navigate the [Standard Occupation Codes](https://www.ons.gov.uk/methodology/classificationsandstandards/standardoccupationalclassificationsoc/soc2010) (SOC) down the tree to find the job they wanted to see info about but we knew this was clumsy.

In the end, we decided to let users type in an occupation and let the [ONS occupation coding tool](https://onsdigital.github.io/dp-classification-tools/standard-occupational-classification/ONS_SOC_occupation_coding_tool.html) match what the input to the SOC. This introduced a text box for people to use in the chat interface. This wasn't ideal as on mobile the keyboard takes up a lot of space. But we felt this was better than navigating the SOC hierarchy. 

The article got widely picked up but the [BBC](https://www.bbc.co.uk/news/business-47691078) pushed a lot of traffic to our site. 

Our standard timeframe for considering metrics is a week. After a week we had almost 14 thousand unique visits, 11 thousand of which happened during the first day.

A third of people who visited the site wanting to know what the risk of automation was for an occupation. 91% of those entered an occupation. 

The top 5 occupations entered were

1. Accountant
2. Teacher
3. Software Engineer/Developer
4. Solicitor
5. Doctor

11% of people who visited choose to read about general facts. Information about location, age and gender were less popular still, with 4%, 3% and 2% respectively. 

One thing we debated a lot was the speed of the chat bubbles. Should we make it quicker like the BBC's or slow so that people can actually read it and not skim?