<script>
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}

<footer>
	<p>Copyright POLIMI 2026</p>
</footer>	

<style>
	:global(p) {color: yellowgreen;}	
</style>		
