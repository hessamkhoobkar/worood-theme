<script>
	import '../app.css';
	import Header from '../components/layout/Header.svelte';
</script>

<Header />
<slot />

<!-- Footer -->

<style lang="postcss">
	:global(html) {
		color: theme(colors.white);
		font: theme(fontFamily.sans);
		background-color: theme(colors.ink.900);
	}
</style>
