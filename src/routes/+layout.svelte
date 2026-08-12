<script lang="ts">
	import "../global.css";
	import favicon from "$lib/assets/favicon.png";
	import Header from "$lib/components/header.svelte";
	import Footer from "$lib/components/footer.svelte";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<Header />
<main>
	<div class="wrapper">
		{@render children()}
	</div>
</main>
<Footer />

<style>
	.wrapper {
		width: 100%;
		max-width: 80rem;
		flex: 1;
		display: flex;
		flex-direction: column;
	}
</style>
