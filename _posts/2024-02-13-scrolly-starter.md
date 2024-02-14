---
title: Scrollystarter with .docx and ArchieML parser 
layout: post
---
One problem we've encounted while producing an article that uses a scrollytelling format, for example [Understanding unemployment: what role does ethnicity and disability play?](https://www.ons.gov.uk/visualisations/dvc2281/), is editing the text. 

## The problem: word and html

The copy for the article is normally drafted in a word doc. The text is then copied across from the word doc into HTML and Svelte elements. This involved a lot of hand-cranking, for example open and closing `<p>` tags or `<Em>` component. Hyperlinks also need the `href` not just the text to display. 

The word doc for the article is sent round for review and people add comments, track changes, or don't track changes and just edit it. 

When you are trying to keep the text in the scrolly up to date with the changes, it becomes a lot of work to track which changes you need to implement, or spending lots of time putting all the text in fresh again.

## The solution: ArchieML

The New York Times created a markup language called [ArchieML](http://archieml.org/) which was built for the newsroom. It relies on everything that needs to put into a structure having a key:value pair. And anything else is just a comment. 

[Reuters and others have a workflow where they draft in Google docs](https://reuters-graphics.github.io/graphics-components/?path=/docs/guides-using-with-google-docs--docs), writing their content in ArchieML. This then gets pulled into a SvelteKit alongside their graphics components so they can quickly spin up a scrollytelling article.

## Making it work with .docx

Unfortunately at ONS, we can't use Google docs so I thought can we do it with word's .docx files. 

A quick search showed [Mammoth](https://github.com/mwilliamson/mammoth.js) as a good node library to convert .docx to HTML, passed through a HTML parser and then finally parsed as ArchieML, which is the [approach suggested by ArchieML in their example script](https://github.com/newsdev/archieml-js/blob/master/examples/google_drive.js) when working with Google docs. Converting to HTML preserves hyperlinks but you don't really need anything else.

### Using AI
I could get Mammoth to read the file, but when I passed that to a HTML parser, it was harder to figure out what was going on. I could tell it was nesting stuff, but not much else. It looked something like this. 



```
<ref *1> [
  <ref *2> Element {
    parent: Document {
      parent: null,
      prev: null,
      next: null,
      startIndex: null,
      endIndex: null,
      children: [Circular *1],
      type: 'root'
    },
    prev: null,
    next: Element {
      parent: [Document],
      prev: [Circular *2],
      next: [Element],
      startIndex: null,
      endIndex: null,
      children: [Array],
      name: 'p',
      attribs: {},
      type: 'tag'
    },
    startIndex: null,
    endIndex: null,
    children: [ [Text] ],
    name: 'p',
    attribs: {},
    type: 'tag'
  },
  <ref *3> Element {
    parent: Document {
      parent: null,
      prev: null,
      next: null,
      startIndex: null,
      endIndex: null,
      children: [Circular *1],
      type: 'root'
    },
    prev: <ref *2> Element {
      parent: [Document],
      prev: null,
      next: [Circular *3],
      startIndex: null,
      endIndex: null,
      children: [Array],
      name: 'p',
      attribs: {},
      type: 'tag'
    },
    next: Element {
      parent: [Document],
      prev: [Circular *3],
      next: [Element],
      startIndex: null,
      endIndex: null,
      children: [Array],
      name: 'p',
      attribs: {},
      type: 'tag'
    },
    startIndex: null,
    endIndex: null,
    children: [ [Text] ],
    name: 'p',
    attribs: {},
    type: 'tag'
  },

  
...

  <ref *17> Element {
    parent: Document {
      parent: null,
      prev: null,
      next: null,
      startIndex: null,
      endIndex: null,
      children: [Circular *1],
      type: 'root'
    },
    prev: <ref *16> Element {
      parent: [Document],
      prev: [Element],
      next: [Circular *17],
      startIndex: null,
      endIndex: null,
      children: [Array],
      name: 'p',
      attribs: {},
      type: 'tag'
    },
    next: null,
    startIndex: null,
    endIndex: null,
    children: [ [Text] ],
    name: 'p',
    attribs: {},
    type: 'tag'
  }
]
```

In the example script from ArchieML, there's a bit to specify how to handle the parsing, so I knew I had to adapt it. In the example script, it basically makes most things text apart from `<a>` tags.

I used the Google AI Bard to [help me write a function](https://g.co/gemini/share/3fb7077f1afb) to go through the parsed output and extract the text from the word docx. 

This could then be passed again to ArchieML to be parsed into JSON. Finally I had a workflow that worked. 

## Making a scrolly starter
Modelled on the robo-embed template, I wrapped everything up into a [scrolly starter](https://github.com/ONSvisual/scrolly-starter) template that uses ONS Svelte Component's feature article as an example for the content. It takes the content from a demo .docx written ArchieML. More instruction of how to use it are in the repo.

## Future improvements
At the moment, it uses svelte's [@html](https://learn.svelte.dev/tutorial/html-tags) to render the content as html so that links work. However, custom components like `<Em>` don't work so I can't make it exactly like the feature article. 






