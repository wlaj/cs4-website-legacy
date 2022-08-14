<script>
	import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';

	export let blok;
</script>

<svelte:head>
	{#each blok.metafield as blok}
		<StoryblokComponent {blok} />
	{/each}
</svelte:head>

<div use:storyblokEditable={blok}>
	{#each blok.body as blok}
		<StoryblokComponent {blok} />
	{/each}
</div>
