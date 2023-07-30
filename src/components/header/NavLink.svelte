<script lang="ts">
	export let label: string;
	export let url: string;
	export let isCurrent: boolean;
</script>

<a
	href={url}
	class="p-6 hover:text-orange-500 transition-all duration-200 ease-in-out overflow-hidden {isCurrent
		? 'text-orange-500'
		: 'text-ink-100'}"
	on:click|preventDefault
>
	<span>
		{label}
	</span>
	<div
		class="absolute inset-x-0 {isCurrent
			? 'bottom-0'
			: '-bottom-2'} h-1 bg-orange-500 rounded-t-full transition-all duration-300 ease-in-out"
	/>
</a>
