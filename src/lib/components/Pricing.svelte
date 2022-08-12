<script>
	import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';

	export let blok;
</script>

<div
	use:storyblokEditable={blok}
	class="flex flex-col max-w-5xl p-6 mx-6 lg:mx-auto text-center text-neutral-900 bg-white border border-neutral-100 rounded-lg shadow dark:border-neutral-600 xl:p-8 dark:bg-neutral-800 dark:text-white"
>
	<h3 class="mb-4 text-2xl font-semibold">{blok.headline}</h3>
	<p class="font-light text-neutral-500 sm:text-lg dark:text-neutral-400">{blok.description}</p>
	<div class="flex items-baseline justify-center my-8">
		<span class="mr-2 text-5xl font-extrabold">${blok.price}</span>
		<span class="text-neutral-500 dark:text-neutral-400">/month</span>
	</div>
	<!-- List -->
	<ul class="mb-8 space-y-4 text-left">
		{#each blok.features as blok}
			<li class="flex items-center space-x-3">
				<svg
					class="flex-shrink-0 w-5 h-5 text-green-500 dark:text-green-400"
					fill="currentColor"
					viewBox="0 0 20 20"
					xmlns="http://www.w3.org/2000/svg"
					><path
						fill-rule="evenodd"
						d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
						clip-rule="evenodd"
					/></svg
				>
				<StoryblokComponent {blok} />
			</li>
		{/each}
	</ul>
	<a
		href="/contact"
		class="text-white bg-blue-600 hover:bg-blue-700 focus:ring-4 focus:ring-blue-200 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:text-white  dark:focus:ring-blue-900"
		>Get started</a
	>
</div>
