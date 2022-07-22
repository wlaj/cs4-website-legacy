<script>
import { storyblokEditable } from "@storyblok/svelte";

export let blok;
</script>

<div use:storyblokEditable={blok}>
  <a href={blok.link} class={blok.style}>{blok.name}</a>
</div>