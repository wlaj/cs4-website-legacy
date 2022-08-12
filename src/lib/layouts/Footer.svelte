<script>
	import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';

	export let blok;
</script>

<div use:storyblokEditable={blok}>
	<footer
		class="w-max-5xl mx-auto p-4 bg-white shadow md:flex md:items-center md:justify-between md:p-6 dark:bg-neutral-900/80"
	>
		<span class="text-sm text-neutral-500 hidden sm:flex sm:text-center dark:text-neutral-400"
			>© 2022 <a href={blok.link} class="hover:underline">{blok.name}</a>. All Rights
			Reserved.
		</span>
		{#each blok.columns as blok}
			<StoryblokComponent {blok} />
		{/each}
	</footer>
</div>
