<script>
	import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';

	export let blok;
</script>

<section class="bg-neutral-50 dark:bg-neutral-900">
	<div
		use:storyblokEditable={blok}
		class="max-w-5xl py-8 mx-6 lg:mx-auto space-y-12 lg:space-y-20 lg:py-24"
	>
		<div class="items-center gap-8 lg:grid lg:grid-cols-2 xl:gap-16">
			<div class="text-neutral-500 sm:text-lg dark:text-neutral-400">
				<h2 class="mb-4 text-3xl font-extrabold tracking-tight text-neutral-900 dark:text-white">
					{blok.headline}
				</h2>
				<p class="mb-8 font-light lg:text-xl">{blok.description}</p>
				<ul class="pt-8 space-y-5 my-7">
					{#each blok.columns as blok}
						<li class="flex space-x-3">
							<svg
								class="flex-shrink-0 w-5 h-5 text-blue-500 dark:text-blue-400"
								fill="currentColor"
								viewBox="0 0 20 20"
								xmlns="http://www.w3.org/2000/svg"
								><path
									fill-rule="evenodd"
									d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
									clip-rule="evenodd"
								/></svg
							>
							<span>
								<StoryblokComponent {blok} />
							</span>
						</li>
					{/each}
				</ul>
			</div>
			<img
				class="hidden w-full mb-4 rounded-lg lg:mb-0 lg:flex"
				src={blok.image}
				alt={blok.headline}
			/>
		</div>
	</div>
</section>
