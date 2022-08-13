<script>
	import { storyblokEditable } from '@storyblok/svelte';

	export let blok;
</script>

<div use:storyblokEditable={blok} id="banner" class="max-w-full mx-auto bg-neutral-50 dark:bg-neutral-900 text-center">
	<div class="max-w-5xl py-10 mx-6 lg:mx-auto">
		<h2
			class="mb-4 text-3xl font-extrabold leading-tight tracking-tight text-neutral-900 dark:text-white"
		>
			{blok.headline}
		</h2>
		<p class="mb-6 font-light text-neutral-500 dark:text-neutral-400 md:text-lg">
			{blok.description}
		</p>
		<a
			href={blok.link}
			class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800"
			>{blok.button}</a
		>
	</div>
</div>
