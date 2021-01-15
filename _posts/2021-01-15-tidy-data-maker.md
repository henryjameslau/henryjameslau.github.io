---
title:Tidydata Maker
layout:post
---

The [small multiple line chart template](https://github.com/ONSvisual/Simple-charts/tree/master/all-templates/small-multiple-line) I developed last year uses [tidy data](http://www.jstatsoft.org/v59/i10/paper) but we are used to seeing data in a wide format as it makes it quicker to grasp what's going on. 

We have been copying and pasting data around to rearrange it to fit the format needed for the template and a colleague asked whether I could make something to do this quickly. 

And here it is, [the tidy data maker](https://www.henrylau.co.uk/tidy-data-maker/index.html).

![tidydatamaker](https://github.com/henryjameslau/henryjameslau.github.io/raw/master/_media/tidydatamaker.gif) 

I wanted to learn [svelte](https://svelte.dev/) as part of building this tool and use their REPL tool. [Here is the svelte code](https://svelte.dev/repl/ef024a5a75994f598baabb9d1e614ce2?version=3.31.2).



To publish the tool. I downloaded the zip file, unzipped it in a new repo and turned on Github pages. The only thing to note is that svelte put links to the root rather than local so once you've changed that so it looks like this it works.

```html
<link rel='stylesheet' href='./global.css'>
<link rel='stylesheet' href='./build/bundle.css'>
<script defer src='./build/bundle.js'></script>
```

