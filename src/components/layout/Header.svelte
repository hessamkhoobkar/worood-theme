<script lang="ts">
	import Bell from '@assets/icons/Bell.svelte';
	import Magnifer from '@assets/icons/Magnifer.svelte';
	import Notification from '@assets/icons/Notification.svelte';
	import userAvatar from '@assets/imgs/user_avatar.jpg';
	import NavRail from '@component/header/NavRail.svelte';

	// Mock Data
	const mainlinks = [
		{ label: 'Dashboard', url: '#' },
		{ label: 'Pages', url: '#' },
		{ label: 'Apps', url: '#' },
		{ label: 'Help', url: '#' }
	];

	let parentNavCurrent: number = 0;
	let childNavCurrent: number = 0;
</script>

<!-- Top -->
<div class="bg-[#0D1117] w-full">
	<div class="w-full max-w-screen-2xl mx-auto px-4 flex justify-start items-center">
		<div class="flex justify-start items-center gap-4">
			<div>
				<span class="text-xl font-black">THEME LOGO</span>
			</div>

			<NavRail linkList={mainlinks} isCurrent={parentNavCurrent} />
		</div>
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
			<button
				class="p-2 rounded-xl text-ink-300 hover:text-white hover:bg-ink-800 transition-all duration-200 ease-in-out"
			>
				<img
					src={userAvatar}
					alt="a emoji of the user with a white background"
					class="w-10 h-10 rounded-xl"
				/>
			</button>
		</div>
	</div>
</div>

<!-- Bottom -->
<div class="bg-[#010409] w-full h-56 border-y border-[#1E2329]">
	<div class="w-full max-w-screen-2xl mx-auto p-4">
		<span
			>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Qui quia aliquam dolorum ad atque
			porro natus quos harum eos eaque veniam saepe animi eius voluptate tenetur maiores,
			repudiandae pariatur mollitia?</span
		>
	</div>
</div>
