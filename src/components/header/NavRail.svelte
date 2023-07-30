<script lang="ts">
	import NavLink from './NavLink.svelte';

	interface Link {
		label: string;
		url: string;
	}

	export let linkList: Link[] = [];
	export let isCurrent: number = 0;
</script>

<div class="flex justify-start items-center">
	{#each linkList as { label, url }, index}
		<NavLink
			{label}
			{url}
			isCurrent={isCurrent === index}
			on:click={() => {
				isCurrent = index;
			}}
		/>
	{/each}
</div>
