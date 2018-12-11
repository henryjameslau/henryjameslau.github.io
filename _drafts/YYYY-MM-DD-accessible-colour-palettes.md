# Accessible colour palettes

Colours is a big part of what makes up graphics and making colours accessible is important. 

### Contrast ratio

The most relevant part of web guidelines regarding colour relate to text. They say for WCAG AA compliance text and images of text should have a minimum contrast ratio of 4.5:1 for normal text and 3:1 for large text.

The first thing to note is that this related to text. Charts and interactives can contain many things other than text such as bars, lines, squares, circles and other shapes. All of these shapes can be big or small or a mix. A good approximate rule is that you'd want your colours to meet the large text contrast ratio for big object like bars and the normal text contrast ratio for smaller objects for example dots or lines.

Also with most interactives and especially maps, you have colours next to each other rather than on a background, so there needs to be some consideration of the spacing between colours that they are distinguishable. 

### Colour space

We're used to thinking of colours in terms of red, green and blue. Add these colours together and you get white. We can describe colours using RGB, breaking up each colour channel into 256 parts. Increase the red channel and you get <span style="color:rgb(255,0,0)">red</span>. Add the blue channel and you get <span style="color:rgb(255,0,255)">purple</span>. Add the green channel and you'll get <span style="color:rgb(255,255,255)">white</span>.

#### The human eye

This works quite well for computers, just add three numbers together to make a colour. The problem comes when we apply human physiology to the issue. Inside the eye, there are two type of cells that sense light: rods and cones. Rods mostly deal with low light and cones are used to tell colour in well-lit conditions.

![Graph of cone sensitivity by wavelength](https://upload.wikimedia.org/wikipedia/commons/1/1e/Cones_SMJ2_E.svg)

Image: [Wikimedia](https://commons.wikimedia.org/wiki/File:Cones_SMJ2_E.svg), [CC-BY](https://creativecommons.org/licenses/by/3.0/deed.en)

The three rods are sensitive to different wavelengths of light, with one roughly at blue, yellow and red. But these don't respond linearly (i.e. a light twice as bright doesn't send a signal twice as strong). What this means is that we should consider what colours our eyes are drawn to, what colours make up the data vis and what parts of the visual you'd like to draw attention to.

#### A different way to think about colour

A alternative way of thinking about colour instead of RGB is Hue, Chroma, and Luminance (HCL). The advantages of using HCL is that it takes into account the way the human eye perceives colour. 

Hue is the shade (red,green,blue), Chroma is the richness of colour (it's a bit like saturation but takes into account the colour of other white objects). Luminance is the perceived brightness of that colour. 

Whereas RGB could be imagined as a cubic colour space with each dimension going from 0 to 255. HCL works in a cylindrical colour space. Hue ranges from 0-360°. Chroma start at 0 but the maximum can vary with hue and luminance. Luminance is from 0 to 100. 

Luminance is dependent on hue and chroma. 

### Colours to represents your data

Be mindful that when using colour to represents your data that it shows the relationships in your data. e.g. if your data is different categories, your colours should be as distinct as possible. If your data is sequential or represents a range, colour should change in a sensible way. Lab and HCL colour spaces calculate colour based on the way the human eye works, rather than how computers calculate colours.

### Colour blindness

I am colourblind myself (slightly red/green) which is useful when it comes to [calling out](https://twitter.com/henryjameslau/status/920409974706188290) [bad colours](https://twitter.com/henryjameslau/status/880788875471454208) on charts. Approximately 8% of men are colourblind and 0.5% of women. There are two main types, difficulty seeing red/green and difficulty seeing blue/yellow. 

The best write up I've seen about testing colours in charts for colourblindness comes from Gregor Aisch of datawrapper. [He applies simulated colour blind vision to a set of colour and then looked at difference between colours](https://vis4.net/blog/2018/02/automate-colorblind-checking/). Where the differences are not great enough a warning is given.

You can [check your colour palette in datawrapper](https://blog.datawrapper.de/colorblind-check/) and check if they give any warnings. 

### Semantics

Colour also has semantic meaning. We're tired of seeing blue for males and pink for females for any dataset, but it's hard to break away from the associated meaning of those colours. Datawrapper did [a recent review of what colours people are using to represent gender](https://blog.datawrapper.de/gendercolor/). 

Be careful to check what those colours could mean for people. Meaning also vary culturally so may mean different things outside what you're used to.

### What to think about when picking colours

To make a good sequential colour scale, you need to steadily change the lightness of the colours. 

For categorical colour, need to keep chroma and luminance steady.

### Tools to help you choose colours

For maps - http://tristen.ca/hcl-picker/#/hlc/6/1/15534C/E2E062 

### Testing our your palettes

Use tools to test out palettes with what they'll look like http://projects.susielu.com/viz-palette





References:

http://www.hclwizard.org/why-hcl/

https://www.vis4.net/blog/2013/09/mastering-multi-hued-color-scales/

https://munsell.com/color-blog/difference-chroma-saturation/

