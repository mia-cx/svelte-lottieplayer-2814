<script lang="ts">	
	import LottiePlayer from '$lib/components/LottiePlayer.svelte';

	import { siteName } from './__layout.svelte';
	
	import intro from '$lib/assets/lottie/intro.json';
	import headbang from '$lib/assets/lottie/headbang.json';
	import settle from '$lib/assets/lottie/settle.json';
	
	export let lotties = [intro, headbang, settle];
</script>

<svelte:head>
	<title>{siteName}</title>
	<meta name="keywords" content="{siteName}">	
	<meta name="description" content="Latest content by {siteName}">

	<meta name="robots" content="index, follow">
	
	<meta property="og:title" content={siteName} />
	<meta property="og:description" content="Latest content by {siteName}" />
	<meta property="og:image" content="https://example.com/image.jpg" />
	<meta property="og:url" content="https://example.com" />
</svelte:head>

<main class="index">
	<LottiePlayer lotties={lotties} />
	<b><h1>{siteName}</h1></b>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		margin: 0 auto;
		align-items: center;
	}
</style>
