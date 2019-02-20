---
layout: post
title: Accessible colours and contrast
---

Why I don't think data visualisation should follow the accessibility guidelines for contrast.

We are having  a bit of discussion internally about accessibility. [New law comes in that public bodies websites have to be accessible by 2021](https://gds.blog.gov.uk/2018/09/24/how-were-helping-public-sector-websites-meet-accessibility-requirements/). To meet AA standard, we need to have [a contrast ratio of 3:1 for graphical objects](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast).

They give the example of an exploded pie chart and a line chart. 

I could pick a few faults in the guidance (says it relies on seeing the sides of the slices to determine information whereas it's actually the angle that's encoding the data or how the explodedness of the pie removes the part-to-whole relationship), but I'd rather think about ways we can be smarter about it.

- We can reshape our data so that it doesn't rely on colour to tell the story
- We can use a different chart type that doesn't rely on colour
- We can make the chart accessible in other ways, for example a really detailed description.

Here's a few thoughts on why the contrast ratio is restricting and for data vis we should be allowed to bend it.

- reduces the colour space, hard to distinguish colours from each other, makes it harder for colour blind people, printing B+W, dominance of colours
- Disservice to users, makes the visualisation harder to read.



