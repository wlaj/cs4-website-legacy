<script>
import { storyblokEditable } from "@storyblok/svelte";

export let blok;
</script>

<div use:storyblokEditable={blok}>
   <ul class="flex flex-col mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium">
        <li>
          <a href={blok.link} class="block py-2 pr-4 pl-3 text-neutral-700 border-b border-neutral-100 hover:bg-neutral-50 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-neutral-400 md:dark:hover:text-white dark:hover:bg-neutral-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-neutral-700">{blok.name}</a>
        </li>
      </ul>
</div>