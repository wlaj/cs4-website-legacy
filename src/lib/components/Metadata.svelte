<script>
	import { storyblokEditable } from '@storyblok/svelte';

	export let blok;
</script>

<svelte:head>
	<div use:storyblokEditable={blok}>
		<meta charset="UTF-8">
		<title>{blok.title}</title>
		<meta name="description" content={blok.description} />
		<meta name="og:title" property="og:title" content={blok.headline} />
		<meta name="keywords" content={blok.keyword}>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta name="robots" content="index, follow" />
	</div>
</svelte:head>
