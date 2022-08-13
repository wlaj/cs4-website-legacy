<script>
	import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';

	export let blok;
</script>

<div use:storyblokEditable={blok} class="bg-white dark:bg-black">
	<div
		class="items-center max-w-5xl py-8 mx-6 lg:mx-auto lg:grid lg:grid-cols-4 lg:gap-16 xl:gap-24 lg:py-24"
	>
		<div class="col-span-2 mb-8">
			<p class="text-lg font-medium text-blue-600 dark:text-blue-500">{blok.caption}</p>
			<h2
				class="mt-3 mb-4 text-3xl font-extrabold tracking-tight text-gray-900 md:text-3xl dark:text-white"
			>
				{blok.headline}
			</h2>
			<p class="font-light text-gray-500 sm:text-xl dark:text-gray-400">{blok.description}</p>
			<div class="pt-6 mt-6 space-y-4 border-t border-gray-200 dark:border-gray-700">
				{#each blok.buttons as blok}
					<div>
						<StoryblokComponent {blok} />
					</div>
				{/each}
			</div>
		</div>
		<div class="col-span-2 space-y-8 md:grid md:grid-cols-2 md:gap-12 md:space-y-0">
			{#each blok.points as blok}
				<div>
					<StoryblokComponent {blok} />
				</div>
			{/each}
		</div>
	</div>
</div>
