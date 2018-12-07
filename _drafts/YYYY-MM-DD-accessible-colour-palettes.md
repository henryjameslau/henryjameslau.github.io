# Accessible colour palettes

Colours is a big part of what makes up graphics and making colours accessible is important. 

### Contrast ratio

The most relevant part of web guidelines regarding colour relate to text. They say for WCAG AA compliance text and images of text should have a minimum contrast ratio of 4.5:1 for normal text and 3:1 for large text.

The first thing to note is that this related to text. Charts and interactives can contain many things other than text such as bars, lines, squares, circles and other shapes. All of these shapes can be big or small or a mix. A good approximate rule is that you'd want your colours to meet the large text contrast ratio for big object like bars and the normal text contrast ratio for smaller objects for example dots or lines.

Also with most interactives and especially maps, you have colours next to each other rather than on a background, so there needs to be some consideration of the spacing between colours that they are distinguishable. 

### Colour space



### Colours to represents your data

Be mindful that when using colour to represents your data that it shows the relationships in your data. e.g. if your data is different categories, your colours should be as distinct as possible. If your data is sequential or represents a range, colour should change in a sensible way. Lab and HCL colour spaces calculate colour based on the way the human eye works, rather than how computers calculate colours.

### Colour blindness

I am colourblind myself (slightly red/green) which is useful when it comes to [calling out](https://twitter.com/henryjameslau/status/920409974706188290) [bad colours](https://twitter.com/henryjameslau/status/880788875471454208) on charts. Approximately 8% of men are colourblind and 0.5% of women. There are two main types, difficulty seeing red/green and difficulty seeing blue/yellow. 

The best write up I've seen about testing colours in charts for colourblindness comes from Gregor Aisch of datawrapper. In his blog post, he looks at [https://vis4.net/blog/2018/02/automate-colorblind-checking/](https://vis4.net/blog/2018/02/automate-colorblind-checking/). He applied simulated colour blind vision to a set of colour and then looked at difference between colours. Where the differences are not great enough a warning is given.

To [check your colour palette in datawrapper](https://blog.datawrapper.de/colorblind-check/), why not put them try in data wrapper and check if they give any warnings. 

### Semantics

Colour also has semantic meaning. Be careful to check what those colours could mean for people. Meaning also vary culturally so may mean different things outside what you're used to.

We're tired of seeing blue for males and pink for females for any dataset, but it's hard to break away from the associated meaning of those colours. Datawrapper did [a recent review of what colours people are using to represent gender](https://blog.datawrapper.de/gendercolor/). 

### Tools to help you choose colours

For maps - http://tristen.ca/hcl-picker/#/hlc/6/1/15534C/E2E062 

### Testing our your palettes

Use tools to test out palettes with what they'll look like http://projects.susielu.com/viz-palette

### Tools to generate palettes







Be mindful that when using colour to represents your data that it shows the relationships in your data. E.g. if your data is different categories, your colours should be as distinct as possible. If your data is sequential or represents a range, colour should change in a sensible way. Lab and HCL colour spaces calculate colour based on the way the human eye works, rather than how computers calculate colours.

Colour blindness



Colour meaning



https://blog.graphiq.com/finding-the-right-color-palettes-for-data-visualizations-fcd4e707a283

https://www.youtube.com/watch?reload=9&v=LBmLspdAtxM