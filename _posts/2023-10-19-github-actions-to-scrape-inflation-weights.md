---
title: Github actions to scrape inflation weights 
layout: post
---

The ONS recently tightened their [rate limits](https://developer.ons.gov.uk/bots/) for the website and this was causing problems for the [inflation calculator](https://www.ons.gov.uk/economy/inflationandpriceindices/articles/howisinflationaffectingyourhouseholdcosts/2022-03-23). 

We analysed the network traffic and saw it was making about 120 calls to get the inflation rates for all the components of inflation (fuel, food etc) and also the weights (parts per 1000). The weight only change yearly so this was something we could easy scrape and host online and then it would only have to grab one file instead of 60. 

Sam Bennett, who wrote the inflation calculator, specified the format for the data to be in. I wrote a simple [script](https://github.com/ONSvisual/automatic-cpi-weights/blob/main/run.js) written in javascript and run in node on a [Github action](https://github.com/ONSvisual/automatic-cpi-weights/blob/main/.github/workflows/main.yml) to scrape the inflation weights and save it to a csv.

The inflation calculator now grabs the [csv](https://github.com/ONSvisual/automatic-cpi-weights/blob/main/data.csv) from Github saving around 60 calls to the website and now it's below the rate limits. 

In the future we'll look to work with the our dev team to put this on ONS infrastructure probably in an AWS lambda and publish to a static bucket so we can point the interactive at the bucket. 