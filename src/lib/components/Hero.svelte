<script>
	import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';

	export let blok;
</script>

<div use:storyblokEditable={blok}>
	<section class="bg-white dark:bg-black">
		<div class="flex max-w-5xl mx-auto pt-20 pb-8 lg:gap-8 xl:gap-0 lg:py-16 lg:pt-28">
			<div class="mr-auto place-self-center lg:col-span-7">
				<h1
					class="max-w-2xl mb-4 text-4xl font-extrabold leading-none tracking-tight md:text-5xl xl:text-6xl dark:text-white"
				>
					{blok.name}
				</h1>
				<p
					class="max-w-2xl mb-6 font-light text-neutral-500 lg:mb-8 md:text-lg lg:text-xl dark:text-neutral-400"
				>
					{blok.description}
				</p>
				<div class="space-y-4 sm:flex sm:space-y-0 sm:space-x-4">
					{#each blok.columns as blok}
						<div>
							<StoryblokComponent {blok} />
						</div>
					{/each}
				</div>
			</div>
			<div class="hidden lg:mt-0 lg:col-span-5">
				<img src={blok.image} alt={blok.name} />
			</div>
		</div>
	</section>
</div>
