---
title: Named slots in layout files in sveltekit
layout: post
---
A little while ago I found out you [can't use named slot in +layout.svelte files](https://www.reddit.com/r/sveltejs/comments/12vf9m4/passing_correct_slots_to_component_slot_from_a/). But there is an alternative way of doing things. Rich Harris, one of the creators of Svelte, has an explaining of why this doesn't work but also suggested [an alternative way that does work](https://github.com/sveltejs/kit/issues/627#issuecomment-1458539744). 

He's done a [demo](https://stackblitz.com/edit/sveltejs-kit-template-default-c4ybjv?file=src%2Froutes%2Fblue%2F%2Bpage.svelte,src%2Froutes%2Fgreen%2F%2Bpage.svelte,src%2Froutes%2Fgreen%2FGreen.svelte,src%2Froutes%2Fgreen%2F%2Bpage.js,src%2Froutes%2Fblue%2F%2Bpage.js,src%2Froutes%2Fblue%2FBlue.svelte,src%2Froutes%2F%2Blayout.svelte&terminal=dev) which show how it works and can also see it [implemented](https://github.com/ONSdigital/explore-local-statistics-app/pull/56/commits/dea88931a94029260c5bb50b6d21c3ae07419743) in ELS. 

In the `+layout.js` file, import any components and any data you might need to feed your component.

```javascript
import type { LayoutLoad } from './$types';
import { base } from '$app/paths';
import { Breadcrumb } from '@onsvisual/svelte-components';

export const load: LayoutLoad = async ({ fetch }) => {
	const coreMetadata = await (await fetch(`${base}/insights/core-metadata.json`)).json();
		coreMetadata,
		title: `Explore local statistics - ONS`,
		description: `Find, compare and visualise statistics about communities in the United Kingdom. Includes data on population, economy and health.`,
		pageType: `home page`,
		component: Breadcrumb,
		breadcrumbLinks: [
			{ label: 'Home', href: 'https://www.ons.gov.uk/', refresh: true },
			{ label: 'Explore local statistics' }
		],
		background: '#e9eff4'
	};
};
```

Then in the `+layout.svelte` file, you have access to those components and data. You can use a `<svelte:component>` to specify the component and then pass through any data to the props for that component.
```javascript
{#if $page.data.component}
    <svelte:component
        this={$page.data.component}
        links={$page.data.breadcrumbLinks}
        background={$page.data.background ?? ''}
    />
{:else}
    <p>$page.data.component is undefined</p>
{/if}
```

According to the Github issues thread, this issue is fixed in Svelte5 with fragments. 
