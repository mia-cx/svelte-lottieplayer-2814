<script context="module" lang="ts">
  export let siteName = "LottiePlayer";
</script>

<script lang="ts">
  import "../app.css";
</script>

<svelte:head>
	<meta property="og:site_name" content={siteName} />
	<meta name="theme-color" content="#fffaf7">
</svelte:head>

<div id="svelte">
  <slot />
</div>

<style>
  #svelte {
    background-color: var(--background-color);
    display: flex;
    flex-direction: column;
    margin: 0 auto;
    max-width: 960px;
    min-height: 100%;
    justify-content: center;
  }
</style>