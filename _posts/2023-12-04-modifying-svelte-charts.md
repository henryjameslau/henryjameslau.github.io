---
title: Modifying svelte charts 
layout: post
---
Really quick post about modifying modules from an NPM import. I wanted to use the svelte charts library but adapt it. I tried editing the files in the node_modules folders but looks like they aren't watched. Followed a few stackoverflow trails ([this comment](https://stackoverflow.com/questions/63323287/how-to-modify-sveltejs-froms-package-locally-for-my-own-use#comment111992867_63327298) and [this answer](https://stackoverflow.com/a/38417065)).

What you have to do is download the svelte chart repo locally and then from the project you're working in tell npm to install it from a local dependency.

`npm install --save /path/to/localversion`

You'll have to run npm install from the local folder (svelte-charts) to get all the stuff it relies on.

In the package.json it now lists the path of svelte-charts as a local one

`"devDependencies": {
        "@onsvisual/svelte-charts": "file:../modified-svelte-charts",`



