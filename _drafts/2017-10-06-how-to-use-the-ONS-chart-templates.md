# How to use the ONS simple charts templates

Firstly need to talk about how the data vis team works, and it will give some context to how our graphs work for us. 

- How the team is made up

- Idea. From business, from team. Need regular meetings, visibility so people know what you're trying to do, the audience you're trying to reach and why. Use ONS data, scheduled release, ad hocs, big releases.

- Explore. Find the story of what you want to write about, what do you want to say. This might need input from editorial side, business area. Uses tools like excel, python, drag and drop interfaces like plotly, tableau, rawgraphs, datawrapper.

- Commissioned. The rough outline of what you want to say, how you're going to say it, the risks, external factors, other angles.

- Development and feedback. Create the vis and write the article. In line with principles and standards. e.g. mobile.

- Publish.

Why it works for us - mobile, easily configurable, uses templates, same code, just adjust the config files, lightweight, embeddable (pym).

- Let's jump to that bit where you know what you want to say. You have a story, it's been commissions and you're making graphs to go with the article. You have your excel sheets there.

- Choose the right chart to say what you want to say. 
- Choose the template, download it. 
- Edit the config and data
- Run it, host it on github, embed it. 




- fork it, github pages
- iframes, pym


Pym is our awy of embedding iframes so they behave responsibly. 
Normal iframe you specific height and width

In our products we need to change the size of the iframe depending on what’s inside, eg. Graph
Child contains the content, interactive 
tells parents what size to change to
Child looks at the body height and sends it over.
Width is set to 100%

Var pymchild = new ….
Loads pym and tell it there’s a child element.
You can tell pym to fire whenever is resized
Function(drawgraphic){…..RenderCallback:drawgraphic}

Pymchild.sendheight() – tells the parent to resize.

Get the parent code set up in your cms. Other people use it, so can just lift stuff straight from your site to theirs.
Can create wrapper that embeds child to test parent functions
