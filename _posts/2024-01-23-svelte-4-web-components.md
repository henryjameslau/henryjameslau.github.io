---
title: Making web components in svelte 4 
layout: post
---
I came across this [BBC article](https://www.bbc.co.uk/news/uk-politics-67361138) where they have a scrolly inside a webpage and looking through the DOM, they are using a `<template>` and using the template as a web-component which then inserts stuff onto a shadow-root. Here's a good MDN article about [templates and slots](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_templates_and_slots). I first heard about web-components when datawrapper said they had [a new way of embedding](https://blog.datawrapper.de/web-component-embedding/) charts using web-components.


When we tried to do a scrolly embedded in an article using an iframe, the page and iframe scrolly separately so was a bit janky and quite an unsatisfying experience. Since we use Svelte as our main framework, I did some exploring and found Svelte can compile components to web components. 

There is a way of using the old svelte template and rollup to generate web-components that can be imported as standalone .js files (See [phptuts](https://phptuts.github.io/svelte-docs/webcomponents/) or [logrocket](https://blog.logrocket.com/build-web-components-svelte/#building-your-web-components) for a walkthrough) but this version uses vite and svelte 4.



## The how
Svelte can set up projects to be like a component library using `npm create svelte@latest` and this is the recommended way from comments. 

For library projects, your interesting stuff is in `lib` and then how it works is in `routes`. I've created a svelte component inside `lib` and added this line to the to the .svelte file.
```
<svelte:options customElement="count-er> 
```

Also added `compilerOptions` to `svelte.config.js`
```
compilerOptions:{customElement:true}
```

When you run `npm run package`, this creates files in a `dist` folder.

Following instructions from [this recipe](https://github.com/sveltejs/kit/issues/10320#issue-1789185724) you can run vite again on the `dist/index.js` to create the standalone iife .js files. See the `vite.webcomponents.config.js` and the modified `build` command in the package.json file. These standalone files can be then loaded from a webpage and then the web-component can be used. See the `test-page` folder for an example.

## The finish result
Here's my github [repo for svelte 4 web components](https://github.com/henryjameslau/svelte-web-component). I used this [template](https://github.com/Tropix126/sveltekit-package-template/tree/master) as a good starting point and followed [this recipe](https://github.com/sveltejs/kit/issues/10320#issue-1789185724) which I found from a stackoverflow answer. 




