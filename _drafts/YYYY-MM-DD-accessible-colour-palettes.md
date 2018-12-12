# Accessible colour palettes

Colours is a big part of what makes up graphics and making colours accessible is important. 

## The basics

### Colour space

We're used to thinking of colours in terms of red, green and blue. Add these colours together and you get white. We can describe colours using RGB, breaking up each colour channel into 256 parts. Increase the red channel and you get <span style="color:rgb(255,0,0)">red</span>. Add the blue channel and you get <span style="color:rgb(255,0,255)">purple</span>. Add the green channel and you'll get <span style="color:rgb(255,255,255)">white</span>.

#### The human eye

This works quite well for computers, just add three numbers together to make a colour. The problem comes when we apply human physiology to the issue. Inside the eye, there are two type of cells that sense light: rods and cones. Rods mostly deal with low light and cones are used to tell colour in well-lit conditions.

![Graph of cone sensitivity by wavelength](https://upload.wikimedia.org/wikipedia/commons/1/1e/Cones_SMJ2_E.svg)

Image: [Wikimedia](https://commons.wikimedia.org/wiki/File:Cones_SMJ2_E.svg), [CC-BY](https://creativecommons.org/licenses/by/3.0/deed.en)

The three rods are sensitive to different wavelengths of light, with one roughly at blue, yellow and red. But these don't respond linearly (i.e. a light twice as bright doesn't send a signal twice as strong). What this means is that we should consider what colours our eyes are drawn to, what colours make up the data vis and what parts of the visual you'd like to draw attention to. Perhaps you need to use a colour to highlight a specific aspect. 

#### A different way to think about colour

A alternative way of thinking about colour instead of RGB is Hue, Chroma, and Lightness (HCL). The advantages of using HCL is that it takes into account the way the human eye perceives colour. 

Hue is the shade (red,green,blue), Chroma is the richness of colour (it's a bit like saturation but takes into account the colour of other white objects). Lightness is the perceived brightness of that colour. 

Whereas RGB could be imagined as a cubic colour space with each dimension going from 0 to 255. HCL works in a cylindrical colour space. Hue ranges from 0-360°. Chroma start at 0 but the maximum can vary with hue and lightness. lightness is from 0 to 100. Lightness is also dependent on hue and chroma. 

## Colour considerations

### Contrast ratio

The most relevant part of web guidelines regarding colour relate to text. They say for WCAG AA compliance text and images of text should have a minimum contrast ratio of 4.5:1 for normal text and 3:1 for large text. Contrast ratio is [calculated by comparing the relative luminance](https://www.w3.org/TR/WCAG20/#contrast-ratiodef) of the lighter colour divided by the [relative luminance](https://www.w3.org/TR/WCAG20/#relativeluminancedef) of the darker colour. What's important to note is that it doesn't depend on hue as people's colour vision are different and it's the contrast in lightness. 

The first thing to note is that this related to text and having enough colour difference to determine letterforms. Charts and interactives can contain many things other than text such as bars, lines, squares, circles and other shapes. All of these shapes can be big or small or a mix. Smaller objects would need a higher contrast ratio whereas a high contrast colour for large blocks would be too strong. 

Also with most interactives and especially maps, you have colours next to each other rather than on a background, so there needs to be some consideration of the spacing between colours that they are distinguishable. 

### Represents your data

Be mindful that when using colour to represents your data that it shows the relationships in your data. e.g. if your data is different categories, your colours should be as distinct as possible. If your data is sequential or represents a range, colour should change in a sensible way.

### Semantics

Colour also has semantic meaning. We're tired of seeing blue for males and pink for females for any dataset, but it's hard to break away from the associated meaning of those colours. Datawrapper did [a recent review of what colours people are using to represent gender](https://blog.datawrapper.de/gendercolor/). 

Be careful to check what those colours could mean for people. Meaning also vary culturally so may mean different things outside what you're used to.

### Colour blindness

I am colourblind myself (slightly red/green) which is useful when it comes to [calling out](https://twitter.com/henryjameslau/status/920409974706188290) [bad colours](https://twitter.com/henryjameslau/status/880788875471454208) on charts. Approximately 8% of men are colourblind and 0.5% of women. There are two main types, difficulty seeing red/green and difficulty seeing blue/yellow. 

The best write up I've seen about testing colours in charts for colourblindness comes from Gregor Aisch of datawrapper. [He applies simulated colour blind vision to a set of colour and then looked at difference between colours](https://vis4.net/blog/2018/02/automate-colorblind-checking/). Where the differences are not great enough a warning is given.

You can [check your colour palette in datawrapper](https://blog.datawrapper.de/colorblind-check/) and check if they give any warnings. 

## How to pick colours

So now we've learnt about colour and we're aware of all the considerations we have to take we can start choosing colours.

Let's start with the easy one first.

### Sequential colours 

To make a good sequential colour scale, you need to vary chroma and lightness of the colours through the scale. 

Let's start with a colour that low in chroma and high in lightness. This is going to be a pale blue.

<div style="height:40px;width:40px;background-color:#eff3ff;"></div>

We want another colour that's the opposite so high chroma and low in lightness.

<div style="height:40px;width:40px;background-color:#08519c;"></div>

And let's make a scale that add three steps in between.

<div style="height:40px;width:40px;background-color:#eff3ff;"></div>
<div style="height:40px;width:40px;background-color:#bdd7e7;"></div>
<div style="height:40px;width:40px;background-color:#6baed6;"></div>
<div style="height:40px;width:40px;background-color:#3182bd;"></div>
<div style="height:40px;width:40px;background-color:#08519c;"></div>

| Colour                                                       | Chroma | Lightness | Hue     |
| ------------------------------------------------------------ | ------ | --------- | ------- |
| <span style="background-color:#eff3ff">#eff3ff</span>        | 6.275  | 95.86     | 277.995 |
| <span style="background-color:#bdd7e7">#bdd7e7</span>        | 11.999 | 84.58     | 243.693 |
| <span style="background-color:#6baed6;color:white">#6baed6</span> | 28.73  | 68.205    | 248.879 |
| <span style="background-color:#6baed6;color:white">#3182bd</span> | 38.134 | 52.164    | 263.369 |
| <span style="background-color:#6baed6;color:white">#08519c</span> | 47.432 | 34.672    | 281.958 |

Analysing the colours we can see chroma increases and lightness decreases. If you think this palette looks familiar you'd be right. It's the [blue palette from colorbrewer](http://colorbrewer2.org/#type=sequential&scheme=Blues&n=5).

This is what is called a single hue as although the hue varies, it's pretty constant.

##### Multi-hue sequential palettes

Although this colour scale is good, there are benefits from using multi-hue sequences.  From Gregor Aisch [article](https://www.vis4.net/blog/2013/09/mastering-multi-hued-color-scales/) on colour

> Hue variation provides a better color contrast and thus makes the colors easier to differentiate.

But as the creators of colorbrewer say, they are tricky to create because 

> "[all three dimensions of colour are changing simultaneously](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.361.6082&rep=rep1&type=pdf)".



Luckily for us Gregor Aisch has created [a tool to help create smooth palettes](http://gka.github.io/palettes/) by interpolating between colours in three dimensional colour space with bezier curves. I highly recommend reading his article [Mastering Multi-hued Color Scales with Chroma.js](https://www.vis4.net/blog/2013/09/mastering-multi-hued-color-scales/) to understand more.  He also includes a neat trick to make sure lightness increases linearly. 

#### Divergent palettes

Now we know how to make sequential palettes, we can make divergent palettes by sticking two sequential ones back to back. [Gregor has even made a tool for that.](https://gka.github.io/palettes/#diverging|c0=darkred,lightyellow|c1=lightyellow,darkblue|steps=7|bez0=1|bez1=1|coL0=1|coL1=1) 

#### Some notes

As advised by graphiq, [choose colours that make sense](https://blog.graphiq.com/finding-the-right-color-palettes-for-data-visualizations-fcd4e707a283). This generally means faint colours for low numbers  and stronger colours for high numbers, although this might depend on your data.

You are going to need to think through the starting points for your colours.  The more colours you have in your scale, the larger the colour difference between the start and end point. 



#### Categorical colours 

For categorical colours, need to keep chroma and lightness steady so colours don't seem stronger than each other but for greyscale you need variation in lightness. 

Getting colours to work to be distinct enough in greyscale helps viewers in colour

Do you have a theme for your colours that you need to stick to. Maybe limit the hue, but have large variance in chroma and lightness.

### Tools to help you choose colours

For maps - http://tristen.ca/hcl-picker/#/hlc/6/1/15534C/E2E062 

https://www.vis4.net/blog/2013/09/mastering-multi-hued-color-scales/

https://gka.github.io/palettes/

http://tools.medialab.sciences-po.fr/iwanthue/

### Testing our your palettes

Use tools to test out palettes with what they'll look like http://projects.susielu.com/viz-palette





References:

https://earthobservatory.nasa.gov/blogs/elegantfigures/2013/08/05/subtleties-of-color-part-1-of-6/



http://www.hclwizard.org/why-hcl/

https://www.vis4.net/blog/2013/09/mastering-multi-hued-color-scales/

https://munsell.com/color-blog/difference-chroma-saturation/

