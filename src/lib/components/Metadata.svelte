<script>
	import { storyblokEditable } from '@storyblok/svelte';

	export let blok;
</script>

<svelte:head>
	<div use:storyblokEditable={blok}>
		<title>{blok.title}</title>
		<meta name="description" content={blok.description} />
		<meta name="og:title" property="og:title" content={blok.headline} />
		<meta name="robots" content="index, follow" />
	</div>
</svelte:head>
