<script context="module">
	import { storyblokInit, apiPlugin } from '@storyblok/svelte';
	import Feature from '$lib/components/Feature.svelte';
	import Grid from '$lib/components/Grid.svelte';
	import Page from '$lib/components/Page.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import Navigation from '$lib/components/Navigation.svelte';
	import Slug from '$lib/components/Slug.svelte';
	import Block from '$lib/components/Block.svelte';
    import Button from '$lib/components/Button.svelte';
    import Overview from '$lib/components/Overview.svelte';
    import Point from '$lib/components/Point.svelte';
    import Banner from '$lib/components/Banner.svelte';
    import List from '$lib/components/List.svelte';
    import Pricing from '$lib/components/Pricing.svelte';

	storyblokInit({
		accessToken: import.meta.env.VITE_STORYBLOK_ACCESS_TOKEN,
		use: [apiPlugin],
		components: {
			navigation: Navigation,
			slug: Slug,
			feature: Feature,
			grid: Grid,
			page: Page,
			hero: Hero,
			block: Block,
            button: Button,
            overview: Overview,
            point: Point,
            banner: Banner,
            list: List,
            pricing: Pricing,
		}
	});
</script>

<script>
	import '../app.css';
</script>

<main>
	<slot />
</main>
