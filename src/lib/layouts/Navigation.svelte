<script>
import { storyblokEditable, StoryblokComponent } from "@storyblok/svelte";

export let blok;
</script>

<div use:storyblokEditable={blok} class="w-full sticky top-0 mx-auto bg-white border-neutral-200 py-2.5 rounded backdrop-blur dark:bg-neutral-900/80">
  <div class="max-w-5xl flex flex-wrap justify-between items-center mx-6 lg:mx-auto">
    <a href="https://flowbite.com/" class="flex items-center">
        <img src={blok.logo} class="mr-3 h-6 sm:h-8" alt={blok.name} />
        <span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">{blok.name}</span>
    </a>
    <button data-collapse-toggle="navbar-default" type="button" class="inline-flex items-center p-2 ml-3 text-sm text-neutral-500 rounded-lg md:hidden hover:bg-neutral-100 focus:outline-none focus:ring-2 focus:ring-neutral-200 dark:text-neutral-400 dark:hover:bg-neutral-700 dark:focus:ring-neutral-600" aria-controls="navbar-default" aria-expanded="false">
      <span class="sr-only">Open main menu</span>
      <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
    </button>
    <div class="hidden w-full md:flex md:space-x-4 md:w-auto" id="navbar-default">
    {#each blok.columns as blok }
      <StoryblokComponent {blok} />
    {/each}
    </div>
  </div>
</div>