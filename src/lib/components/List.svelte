<script>
	import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';

	export let blok;
</script>

<div use:storyblokEditable={blok}>
	<section class="bg-white dark:bg-black">
		<div class="max-w-5xl px-4 py-8 mx-8 lg:mx-auto lg:py-24 lg:px-6">
			<div class="max-w-5xl mx-auto mb-8 text-center lg:mb-12">
				<h2 class="mb-4 text-3xl font-extrabold tracking-tight text-neutral-900 dark:text-white">
					{blok.headline}
				</h2>
				<p class="mb-5 font-light text-neutral-500 sm:text-xl dark:text-neutral-400">
					{blok.description}
				</p>
			</div>
			<div class="space-y-8 lg:grid lg:grid-cols-3 sm:gap-6 xl:gap-10 lg:space-y-0">
				{#each blok.columns as blok}
					<div>
						<StoryblokComponent {blok} />
					</div>
				{/each}
			</div>
		</div>
	</section>
</div>
