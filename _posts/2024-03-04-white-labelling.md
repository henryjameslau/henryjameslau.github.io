---
title: White labelling interactives 
layout: post
---
One ambition we've had in the team is to allow white labelling of our interactives so external organisations can style it how they like. From conversations with news organisations, this is something they would like and would help with them embedding our tools. 

We were inspired when [Jon McClure](https://twitter.com/jonrmcclure) came to speak to us about the graphics team at Reuters. Their business model also relied on getting other organisation to restyle their interactives as a way of selling their embeds. 

We found the [2022 US mid term election results page on the BBC](https://www.bbc.co.uk/news/election/2022/us/results) as an example. 

The map and table are from Reuters but BBC have styled them with their own colours and fonts. 


Inspecting the element you can see that the iframe has some parameters including one where a URL is given for an externally hosted CSS.

```
customStylesheet=https://static.files.bbci.co.uk/elections/styles/BBC_Override.css
```

I had a chat with Ahmad, the brains behind [ONS' svelte components](https://github.com/ONSvisual/svelte-components) and he came up with a way to integrate it with our components. 

Again following the Reuter's [way](https://github.com/reuters-graphics/graphics-components/blob/main/src/components/Theme/Theme.svelte) of doing things we created a prop for our `Theme` component, a `allowClientOverrides` boolean which can then be targetted with CSS. By using CSS variables, these overrides are carried through to child components. 

## How it works
When using the `<Theme>` component, specify a `theme` and set the prop `allowClientOverrides` to true. This then sets a `div` with the class `client-css-override` inside the theme which can then be targetting with CSS, for example

```css
div.client-css-override{
    --text: #f9ea9a;
}
```

The external stylesheet is loaded if `customStylesheet` is passed as a parameter in the url. SvelteKit uses the `$page` store to get the URL and then gets the key `customStylesheet`.

```
const customStylesheet = $page.url.searchParams.get("customStylesheet");
```

If there is a customStylesheet it gets loaded via a `<link>` element.

```
{#if customStylesheet}
       <link rel="stylesheet" href={customStylesheet} />
{/if}
```

Here's a [little demo](https://github.com/henryjameslau/White-labelling-example).
