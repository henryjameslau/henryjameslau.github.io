---
type:post
title:Design data visualisations for accessibility
---

Trying to do accessible colours

- they look naff
- contrast ratio is too restrictive
- doesn't taken into account how colour is going to be used (small, large shapes)

smerhurst  http://smethur.st/posts/176135868 



Argument that making stuff naff is more dangerous as people won't use it

- make it difficult for other users, e.g. dyslexic, those who print it out in black and white.

Provide another accessible means of accessing the data

Law about what we have to comply with





**Colourblindnessawareness response**



I finally had a reply from someone at the colour blindness org, and she has pretty much backed up our approach from what we discussed last time. 

 

I think we need to think more about conveying information in ways other than colour, which is obviously going to be tricky with the constraints of chart builder, but maybe a longer-term goal. 

Something to discuss in our meeting next Friday

 

Rachel

 

**From:** [kathryn@colourblindawareness.org](mailto:kathryn@colourblindawareness.org) <[kathryn@colourblindawareness.org](mailto:kathryn@colourblindawareness.org)> 
 **Sent:** 22 July 2019 14:32
 **To:** Price, Rachel <[Rachel.Price@ons.gov.uk](mailto:Rachel.Price@ons.gov.uk)>
 **Subject:** RE: Colour considerations for data visualisations

 

Dear Rachel

 

Many apologies for the long delay in replying. I think this was partly down to knowing you’d said ‘no rush’ - I can’t believe that was over a month ago!

 

I’ve replied below in blue for ease.

 

I hope my comments make sense! We can provide training too but we do charge for this service.

 

Best wishes

 

Kathryn

 

**From:** Price, Rachel <[Rachel.Price@ons.gov.uk](mailto:Rachel.Price@ons.gov.uk)> 
 **Sent:** 07 June 2019 16:33
 **To:** [info@colourblindawareness.org](mailto:info@colourblindawareness.org)
 **Subject:** Colour considerations for data visualisations

 

Hello,

 

I work in the design team at the Office for National Statistics, and along with colleagues in the data visualisation team, have been looking into our colour palettes for charts/graphs.

 

Oliver Daddow suggested on Twitter that we get in touch with your organisation to see if you could support us with this work (https://twitter.com/oliver_daddow/status/1131911048301285376)

 

I was wondering if you could advise on a couple of things:

 

·         I have been using colour blindness simulation tools to help with testing out colour palettes, but I’ve found different tools can give vastly different results. I’ve attached examples here. Do you know if any of them are more accurate than others and which we should trust? Unfortunately none of the simulations tools are 100% accurate, therefore we only use simulations we have ‘tested’ on colour blind people and which we know are accurate for every specific simulation for the type of colour blindness we are seeking to simulate. None are accurate for all types of dichromatic vision, accuracy levels for each seem to depend upon the actual colours being simulated and how each algorithm reacts to those specific colours. The best we can say is that some are accurate for one or more types some of the time. This means they can only give an impression of where potential issues *might* occur. ColorOracle is considered to be the best from your selection but you can’t rely on it 100%.

 

·         I have put together a proposed palette to start working with, also attached. Do you have any feedback about this palette? See below.

 

We are trying to find a balance between these things:

\-        Colour contrast ratio against white of 3:1 or above (as per [WCAG guidelines](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast))

\-        Colour contrast between the colours so they can be differentiated, also in greyscale as they are often printed

\-        Colours that work for those with different colour vision deficiencies

\-        Visually appealing palette that works together and fits in with our brand

 

 

Unfortunately you won’t be able to achieve what exactly you want! 

 

As a Government funded organisation you must comply with WCAG 2.1.Sometimes this will mean a minimum colour contrast ratio of 4.5:1, depending upon a number of factors such as font size.

 

If you comply with WCAG 2.1 then when you print into greyscale all the information will be accessible.

 

It’s not possible to have a set of colours which work for all types of colour blindness if you want to have more than 4 colours because you will fall foul of the 3:1/4.5:1 contrast ratio minimums, as you’ve already discovered. So in these instances there is no option but to also convey the information in colour by some other means i.e. you can still use the colours but you have to add a secondary label such as text, patterns, symbols etc. The secondary labels must meet the minimum contrast ratios though, so you can’t have red text on a black background, yellow text against white etc. 

 

For example, you can use different colours for line graphs provided you give each coloured line a different pattern as well. For your ‘dots’ chart use colours *and* a different shape to denote each colour.

 

You can have any visually appealing palette provided any *information* is given in such a way that it meets the WCAG 2.1 or has secondary labelling. The key thing to note is that colour blind people don’t use colour to navigate information, colour is generally ignored. They will still recognise a logo/your colour scheme for example, but only as they perceive it.

 

Photos are a different issue so when adding information over a photo any text/information should be given against a solid background, not directly onto the photo and not via a semi-transparent overlay.

 

There’s not much point trying to create a colour scheme which is attractive to people with CVD due to the ran eof types/severities therefor, we’d advise you to concentrate on attracting in those with normal colour vision via your chosen colour scheme whilst at the same time ensuring you’re not excluding those with CVD (or the other visual impairments supported by WCAG 2.1) from any actual information.

 

Thanks in advance for any advice you can provide. I’m out of the office next week so no rush on getting back to me. 

 

Kind regards,

Rachel

 



**Solutions** 

Direct label lines https://depictdatastudio.com/directly-labeling-line-graphs/ 



Do we have information about alternative ways for people to consume information. Alt text, descriptive titles, tables.



**DVS Thread**

https://datavizsociety.slack.com/archives/CGLNXR332/p1564326187014600?thread_ts=1564326187014600&cid=CGLNXR332 

 

Thread

[topic-best-practices](https://datavizsociety.slack.com/archives/CGLNXR332/p1564326187014600)

[Will Chase](https://app.slack.com/team/UGJN75T5Z) [28 Jul at 16:03](https://datavizsociety.slack.com/archives/CGLNXR332/p1564326187014600)
 Hi all, I'm working on a presentation about design guidelines for dataviz, so I'd like to crowdsource some content from the experts here. I'm planning on featuring [@Amy Cesal](https://datavizsociety.slack.com/team/UFFTLE516)'s collated list of style guides, as well as some other resources and discussions from Slack and around the interwebs, but there's a few places I feel like content is missing and I need your help.Something that I think doesn't get a lot of attention is the non-data and non-text portion of charts: think backgrounds, axes, axis ticks, grid marks. I know these are pretty minor elements, but I tend to obsess over them and I think they can have a pretty big influence on how a chart looks and functions. So, does anyone have any resources or thoughts on these elements? When should we include grid marks or remove them? How should they be styled (high contrast, barely noticeable, dashed lines...)? What about axes, are there guidelines for what axis elements need to be included or excluded and how best to format them?

22 replies

​    

[Will Chase](https://app.slack.com/team/UGJN75T5Z)  [3 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564326380014700?thread_ts=1564326187.014600&cid=CGLNXR332)
 Also, if you have any "holy grail" or "must read" blog posts or resources on dataviz design, please send them my way!

[Jason Forrest](https://app.slack.com/team/UGJM9S2D9)  [3 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564326761014900?thread_ts=1564326187.014600&cid=CGLNXR332)
 IMHO Dona M. Wong's book provided me the best details on chart architecture: [https://www.amazon.com/Street-Journal-Guide-Information-Graphics/dp/0393347281/ref=sr_1_1?keywords=wall+street+journal+data+visualization&qid=1564326693&s=gateway&sr=8-1](https://slack-redir.net/link?url=https%3A%2F%2Fwww.amazon.com%2FStreet-Journal-Guide-Information-Graphics%2Fdp%2F0393347281%2Fref%3Dsr_1_1%3Fkeywords%3Dwall%2Bstreet%2Bjournal%2Bdata%2Bvisualization%26qid%3D1564326693%26s%3Dgateway%26sr%3D8-1&v=3)

[Mace](https://app.slack.com/team/ULU1E93C0)![:flag-dk:](file:///C:/Users/Henry/AppData/Local/Packages/oice_16_974fa576_32c1d314_37df/AC/Temp/msohtmlclip1/01/clip_image002.png)  [3 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564338080015500?thread_ts=1564326187.014600&cid=CGLNXR332)
 If I remember correctly, Kirk has some stuff about axis in his *Data Visualization. A Handbook for Data Driven Design*  (2016)

[Mace](https://app.slack.com/team/ULU1E93C0)![:flag-dk:](file:///C:/Users/Henry/AppData/Local/Packages/oice_16_974fa576_32c1d314_37df/AC/Temp/msohtmlclip1/01/clip_image002.png)  [3 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564338130015700?thread_ts=1564326187.014600&cid=CGLNXR332)
 Tufte too; paraphrasing: keep removing everything and making everything thinner until it becomes worse, in which case move on to removing something else and making it thinner. E.g. the intersection of *x* and *y* axes

[Stephanie Tuerk](https://app.slack.com/team/UGKK7A6G2)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564343498015900?thread_ts=1564326187.014600&cid=CGLNXR332)
 Having just gone through an effort to educate myself about accessibility (particularly 508 compliance, with is the USGov's set of requirements for complying, I believe, with ADA?), I immediately thought about accessibility concerns when you mentioned contrast. (For 508 compliance, there are quantitative specifications for contrast) Granted that there are ways to make data accessible that allow data visualizations themselves to not have to meet contrast requirements, but it seems like guidelines we produce these days for data viz should make a good faith effort to make recommendations that result in accessible visualizations. I feel like a lot of data viz guidelines/best practices are pretty established, and have been for a while. I.e. imo what the world needs now is not another book that says , "don't truncate y-axes". (Not that this is what you are proposing) OTOH, the question of how to make data visualization accessible seems wide open, and like a super fecund site for future work in the field, and I think that new guidelines that incorporate best practices for accessibility would be super useful. Which is just to say: keep in mind accessibility when recommending things that are "barely noticeable." I love a minimalist aesthetic myself, but I know that I need to figure out how to do minimalism that is also accessible. (edited)

[Will Chase](https://app.slack.com/team/UGJN75T5Z)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564345941016400?thread_ts=1564326187.014600&cid=CGLNXR332)
 [@Stephanie Tuerk](https://datavizsociety.slack.com/team/UGKK7A6G2) yeah those are good points. I think you're right that accessibility is wide open right now and really deserves more attention. I think one of the big challenges is what accessibility means and what tradeoffs you make when designing for accessibility. If there's changes you can make that improve accessibility at no expense to the rest of the audience then it's a no-brainer. But a lot of times you'll have to think carefully about what you're sacrificing when you make accessibility decisions, and I think that's something that we need to consider as well, but it can be hard to talk about. I saw a recent tweet that was something to the effect of "If you're not making accessibility a top priority in your web design you don't deserve to code and you should be fired and replaced with someone who isn't an ableist." Clearly that's an extreme example, but because people over-simplify accessibility and equate it with inclusiveness, it can be a touchy subject, and I've seen a lot of "burn them at the stake" sort of responses when people question accessibility choices.My big issue is, people over-emphasize certain types of accessibility and don't always consider the tradeoff when catering to a certain group of people. Color blindness is a good example. If you can design a nice color palette that's totally color-blind friendly, that's great. But there are times when you'll have a complex palette that you might just not be able to optimize for ie. Protanopia while maintaining a pleasing palette, and in my opinion we should ask whether it's worth it to make a chart ugly to accommodate 0.56% of the population. People might outcry and say, but for those people the chart is unreadable, while for the rest it's "just aesthetics", but the truth is that if your chart has an ugly an unpleasant color palette, it will turn away a lot of people on first glance, in essence making it inaccessible to those people (inaccessible isn't the right word, because they are **capable** of looking at it, but in my mind if they don't then it's the same effect). If people don't buy that example, then here's one where you have to make a direct tradeoff choice for two different types of accessibility. Guidelines for low-vision accessibility recommend using high-contrast text since it's easier to read for vision impaired people, but high-contrast between background and text is the worst case scenario for dyslexia, and guidelines for dyslexic-friendly visuals recommend using relatively low-contrast text and background.Just to be clear, I'm not at all advocating for ignoring accessibility, just trying to open up the discussion and point out that a lot of the current discourse is pretty narrow and doesn't always consider the tradeoffs or less-talked-about forms of disability that impact your ability to read a chart.

[Jason Forrest](https://app.slack.com/team/UGJM9S2D9)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564346343016600?thread_ts=1564326187.014600&cid=CGLNXR332)
 I think that's a completely reasonable point Will! I'm totally in agreement.

[Jason Forrest](https://app.slack.com/team/UGJM9S2D9)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564346945016900?thread_ts=1564326187.014600&cid=CGLNXR332)
 I feel like the accessibility in color has been a bit over-indexed upon because it's actually the contrast ratios that are more important than the actual hues. The weight of axis lines and marks is definitely something that also impacts one's understanding.

[Will Chase](https://app.slack.com/team/UGJN75T5Z)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564347273017100?thread_ts=1564326187.014600&cid=CGLNXR332)
 Yeah for sure. And we're also at a point where more creative solutions will be needed. I can imagine serving up a visual with higher contrast, bigger lettering, and stronger grids/axes if it detects a screenreader, and serving up a different chart otherwise. Obviously you can't optimize for every single scenario, but these are the kinds of things we should explore

[Stephanie Tuerk](https://app.slack.com/team/UGKK7A6G2)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564347487017300?thread_ts=1564326187.014600&cid=CGLNXR332)
 [@Will Chase](https://datavizsociety.slack.com/team/UGJN75T5Z) Totally agree with you 1000% that this needs to be talked about -- and in a way that is nuanced and reflects the complexities of reality rather than the neatness of mutually exclusive binaries. I think the question of "who do we design for?" is a super important, particularly given a part of the data viz world is interested in producing  empirically-derived knowledge about visualization best practices using human subjects. (Are these subjects actually who we are designing for?Along the same lines, "ugliness" and "aesthetically pleasing" are socio-historical constructs, so, these will vary from person to person) I will say (speaking equally to myself here because I am usually very much on Team 1. is Conceptually Robust and 2. Looks Good) that the idea that people will be turned away from the visualization because it isn't pleasing to them, from my perspective, ignores the fact that the visualization ostensibly has information that people need to access -- and that they will access it regardless. This also suggests that accessibility and looking good are mutually exclusive properties, which I just don't think is true. I'm not saying there aren't trade-offs, but I think a small hit in "attractiveness" is worth it to maximize accessibility -- recognizing that total accessibility to all is possibly impossible. As designers, I feel like we should see this as an opportunity to sharpen our design skills rather than an onerous constraint that prevents us from making something really great.

[Stephanie Tuerk](https://app.slack.com/team/UGKK7A6G2)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564347887017600?thread_ts=1564326187.014600&cid=CGLNXR332)
 Basically, I think we should all strive not to be the jerk who designs the data viz equivalent of this and then is like, "but it looks good." There are lots of ways to make public, interactive sculptures that are more accessible than this, and we can do that with data viz too, imo. If we put accessibility in guidelines, people will just rule this out from the start.

The-Vessel-Hudson-Yards-Climb-Photo-Staircase-Thomas-Heatherwick-NYC1-3.jpg 

[![The-Vessel-Hudson-Yards-Climb-Photo-Staircase-Thomas-Heatherwick-NYC1-3.jpg](file:///C:/Users/Henry/AppData/Local/Packages/oice_16_974fa576_32c1d314_37df/AC/Temp/msohtmlclip1/01/clip_image003.png)](https://files.slack.com/files-pri/TFGGL73J7-FLTV8JEGL/the-vessel-hudson-yards-climb-photo-staircase-thomas-heatherwick-nyc1-3.jpg)

[Will Chase](https://app.slack.com/team/UGJN75T5Z)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564348628018100?thread_ts=1564326187.014600&cid=CGLNXR332)
 Wow, so much here to talk about. I think you hit the nail on the head, it's just so important to ask ourselves "who are we designing for?". Unfortunately too many people fall into the trap of not asking, and then the answer ends up being "I'm designing for me". Which is how you end up with the example you gave of inaccessibility. Like you say, realizing that there will always be tradeoffs, but at the same time always striving to be better, to design better and for more people is key. And it's key to be able to say "With this design I tried to make it accessible by using X, Y, Z, which benefits these groups of people" and not have people dogpile and say "But you forgot about **these** people" is so important.. after all we're all just trying to do our best. And ideally your designs that help some will really benefit the masses (thinking Don Norman here).

[Will Chase](https://app.slack.com/team/UGJN75T5Z)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564348752018300?thread_ts=1564326187.014600&cid=CGLNXR332)
 I think a big problem in moving things forward is the lack of infrastructure. So many people in dataviz, coding, web dev, are self taught (myself included) and really mastering the techniques of accessibility thought design and code is something that takes years of practice and study to achieve. I'm hoping there are more and more resources in the coming years to address that. And of course there has to be demand for it from companies who are hiring or else people will just think it's a useless skill.

[Stephanie Tuerk](https://app.slack.com/team/UGKK7A6G2)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564349986018500?thread_ts=1564326187.014600&cid=CGLNXR332)
 ![:point_up_2:](file:///C:/Users/Henry/AppData/Local/Packages/oice_16_974fa576_32c1d314_37df/AC/Temp/msohtmlclip1/01/clip_image005.png)x100. My recent experience that has given me a new perspective on this is that I spent maybe 2 months designing and fairly substantial web-based data portal w/ interactive visualizations vaguely knowing that I had to make it 508 compliant (my first time), not really knowing what that entailed, and vaguely knowing that I would address it later. When it came time to address it, I was like, okay, how can I figure out exactly what constitutes 508 compliance, and...the infrastructure for this is TERRIBLE. There are WCA Guidelines which is about as easy to interpret as the tax code ([https://www.w3.org/TR/WCAG21/](https://slack-redir.net/link?url=https%3A%2F%2Fwww.w3.org%2FTR%2FWCAG21%2F&v=3)), googling stuff didn't really help, etc. I think that a large part of this is that 508 compliance (which is not the same as accessibility, I realize) is necessarily a matter of interpretation, and from a legal perspective, it is not advantageous to create a definitive checklist -- because there IS no definitive checklist. Which leaves designers in a meta-gray zone where they don't know if they are in the clear, in the black, in a legal gray zone, or in an ethical gray zone. I was like, "how am I supposed to do this?!?" And the answer is, you make a good faith attempt, then it is reviewed by whatever federal agency you are designing for, then you have a back and forth with them where they say, "this thing isn't accessible," and you say, "but this same information can be accessed in this accessible way over here," and then they give you approval. I was like, seriously, *this* is *the* way?I think the good/interesting news is that the market might actually incentivize designers to know how to make visualizations accessible? Did you see that a case against Domino's is going to the SC over website accessibility concerns? [https://www.eater.com/2019/7/25/8930669/dominos-supreme-court-website-accessible-blind-users](https://slack-redir.net/link?url=https%3A%2F%2Fwww.eater.com%2F2019%2F7%2F25%2F8930669%2Fdominos-supreme-court-website-accessible-blind-users&v=3) Seems very likely that companies are increasingly going to understand that, from a legal perspective, they have to make things accessible, and they need people who can learn to do this. (Not that hard, tbh)OTOH, I agree that it is totally fine and appropriate to maintain conceptual distinctions between different kinds of design concerns (say, informational organization, graphic hierarchies, accessibility), and that to say that all design concerns are the same is reductive.

w3.org

[Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/)

Web Content Accessibility Guidelines (WCAG) 2.1 covers a wide range of recommendations for making Web content more accessible. Following these guidelines will make content more accessible to a wider range of people with disabilities, including accommodations for blindness and low vision, deafness and hearing loss, limited movement, speech disabilities, photosensitivity, and combinations of these, and some accommodation for learning disabilities and cognitive limitations; but will not address every user need for people with these disabilities. These guidelines address accessibility of web content on desktops, laptops, tablets, and mobile devices. Following these guidelines will also often mak… 

![Eater](file:///C:/Users/Henry/AppData/Local/Packages/oice_16_974fa576_32c1d314_37df/AC/Temp/msohtmlclip1/01/clip_image007.png)Eater

[Domino’s Fights Ruling on Making Its Website Accessible to the Blind](https://www.eater.com/2019/7/25/8930669/dominos-supreme-court-website-accessible-blind-users)

The chain is willing to go all the way to the Supreme Court to fight the ruling

25 Jul(94 kB)

[https://cdn.vox-cdn.com/thumbor/nRANHk7WeHF5V4ti6MGa0wcYZ6Y=/0x217:3000x1788/fit-in/1200x630/cdn.vox-cdn.com/uploads/chorus_asset/file/18336002/3362000.jpg.jpg](https://slack-redir.net/link?url=https%3A%2F%2Fcdn.vox-cdn.com%2Fthumbor%2FnRANHk7WeHF5V4ti6MGa0wcYZ6Y%3D%2F0x217%3A3000x1788%2Ffit-in%2F1200x630%2Fcdn.vox-cdn.com%2Fuploads%2Fchorus_asset%2Ffile%2F18336002%2F3362000.jpg.jpg&v=3)

[Wendy Small](https://app.slack.com/team/UGMG6E560)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564354318020200?thread_ts=1564326187.014600&cid=CGLNXR332)
 [@Jason Forrest](https://datavizsociety.slack.com/team/UGJM9S2D9) ok with you if I add your comment and reference in the Best Practice category on Discourse Beta?

[Jason Forrest](https://app.slack.com/team/UGJM9S2D9)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564354497020500?thread_ts=1564326187.014600&cid=CGLNXR332)
 Mine? Sure, but it's the weakest part of this particular thread, haha

[Wendy Small](https://app.slack.com/team/UGMG6E560)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564354680023200?thread_ts=1564326187.014600&cid=CGLNXR332)
 [@Jason Forrest](https://datavizsociety.slack.com/team/UGJM9S2D9) it’s the link that I thought we could save off before it’s  eaten away by the archive!

[Wendy Small](https://app.slack.com/team/UGMG6E560)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564354829025100?thread_ts=1564326187.014600&cid=CGLNXR332)
 [@Will Chase](https://datavizsociety.slack.com/team/UGJN75T5Z) a summary of this thread would be great for Discourse Beta if you have time. (edited)

[Will Chase](https://app.slack.com/team/UGJN75T5Z)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564355071025500?thread_ts=1564326187.014600&cid=CGLNXR332)
 is there a link or somewhere I can sign up

[Jason Forrest](https://app.slack.com/team/UGJM9S2D9)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564355119025800?thread_ts=1564326187.014600&cid=CGLNXR332)
 Dona's book should be on our all DVS reading lists, etc. She's another person I'd love to feature in Nightingle!

[Wendy Small](https://app.slack.com/team/UGMG6E560)  [2 days ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564355283028600?thread_ts=1564326187.014600&cid=CGLNXR332)
 [@Will Chase](https://datavizsociety.slack.com/team/UGJN75T5Z) DM [@Mollz](https://datavizsociety.slack.com/team/UFJ2S850W) or [@lord](https://datavizsociety.slack.com/team/UGP0H5SG6) for access. It’s still in testing mode. Content like this would be great to add in. Thanks Will

[Lisa Waananen Jones](https://app.slack.com/team/UK610MWF2)  [2 hours ago](https://datavizsociety.slack.com/archives/CGLNXR332/p1564550934031000?thread_ts=1564326187.014600&cid=CGLNXR332)
 This is a great conversation and this suggestion feels slightly off-topic now, but I love this series: [https://www.visualisingdata.com/2016/03/little-visualisation-design/](https://slack-redir.net/link?url=https%3A%2F%2Fwww.visualisingdata.com%2F2016%2F03%2Flittle-visualisation-design%2F&v=3)

 