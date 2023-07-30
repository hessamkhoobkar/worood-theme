<script lang="ts">
	import { slide, fly } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import { clickOutside } from '$lib/clickOutside';

	import Bell from '@assets/icons/Bell.svelte';
	import Magnifer from '@assets/icons/Magnifer.svelte';
	import Notification from '@assets/icons/Notification.svelte';
	import userAvatar from '@assets/imgs/user_avatar.jpg';

	let userMenu: boolean = false;

	// MockData
	const userLinks = [
		{ label: 'My Profile', url: '#' },
		{ label: 'My Projects', url: '#' },
		{ label: 'My Subscription', url: '#' },
		{ label: 'My Statements', url: '#' }
	];
	const actionLinks = [
		{ label: 'Color Mode', url: '#' },
		{ label: 'Language', url: '#' },
		{ label: 'Account Settings', url: '#' },
		{ label: 'Sign Out', url: '#' }
	];
</script>

<div class="flex justify-end items-center ms-auto">
	<button
		class="p-4 rounded-xl text-ink-300 hover:text-white hover:bg-ink-800 transition-all duration-200 ease-in-out"
	>
		<Magnifer size={24} />
	</button>
	<button
		class="p-4 rounded-xl text-ink-300 hover:text-white hover:bg-ink-800 transition-all duration-200 ease-in-out"
	>
		<Notification size={24} />
	</button>
	<button
		class="p-4 rounded-xl text-ink-300 hover:text-white hover:bg-ink-800 transition-all duration-200 ease-in-out"
	>
		<Bell size={24} />
	</button>
	<div use:clickOutside on:click_outside={() => (userMenu = false)}>
		<button
			on:click={() => (userMenu = !userMenu)}
			class="p-2 rounded-xl hover:bg-ink-800 transition-all duration-200 ease-in-out"
		>
			<img
				src={userAvatar}
				alt="a emoji of the user with a white background"
				class="w-10 h-10 rounded-xl"
			/>
		</button>

		{#if userMenu}
			<div
				in:fly={{
					duration: 300,
					x: 0,
					y: -10,
					opacity: 0.5,
					easing: quintOut
				}}
				out:fly={{
					duration: 300,
					x: 0,
					y: -10,
					opacity: 0,
					easing: quintOut
				}}
				class="absolute w-64 end-0 top-full bg-ink-800 shadow-xl shadow-ink-950 rounded-2xl z-10"
			>
				<!-- Profile -->
				<div class="flex justify-start items-start gap-4 p-4">
					<img
						src={userAvatar}
						alt="a emoji of the user with a white background"
						class="w-12 h-12 rounded-xl"
					/>
					<div class="flex flex-col justify-start items-start gap-1">
						<span>
							Helena Rose
							<!-- label -->
							<span
								class="text-xs bg-orange-500 bg-opacity-20 text-orange-500 px-2 py-1 rounded-xl"
							>
								Pro
							</span>
						</span>

						<span class="text-sm text-ink-400">h.Rose@bigbis.com</span>
					</div>
				</div>
				<div class="w-full border-b border-ink-900" />
				<!-- links -->
				<div class="flex flex-col justify-start items-start p-2">
					{#each userLinks as { label, url }}
						<a
							href={url}
							class="w-full text-sm text-ink-100 py-3 px-4 hover:bg-ink-900 hover:text-orange-500 rounded-lg transition-all duration-200 ease-in-out"
						>
							{label}
						</a>
					{/each}
				</div>
				<div class="w-full border-b border-ink-900" />
				<!-- settings -->
				<div class="flex flex-col justify-start items-start p-2">
					{#each actionLinks as { label, url }}
						<a
							href={url}
							class="w-full text-sm text-ink-100 py-3 px-4 hover:bg-ink-900 hover:text-orange-500 rounded-lg transition-all duration-200 ease-in-out"
						>
							{label}
						</a>
					{/each}
				</div>
			</div>
		{/if}
	</div>
</div>
