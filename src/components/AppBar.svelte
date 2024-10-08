<script lang="ts">
	import { AppBar } from '@skeletonlabs/skeleton';
	import { LightSwitch } from '@skeletonlabs/skeleton';
	import { getDrawerStore } from '@skeletonlabs/skeleton';
	const drawerStore = getDrawerStore();

	function openDrawer() {
		drawerStore.open({ id: 'main-menu' });
	}
</script>

<AppBar
	gridColumns="grid-cols-3"
	slotDefault="place-self-center md:place-self-center"
	slotTrail="place-content-end"
>
	<!-- Lead Slot (Hamburger Icon for mobile and logo for larger screens) -->
	<svelte:fragment slot="lead">
		<!-- Hamburger Icon (visible only on mobile screens) -->
		<button class="btn p-0 md:hidden" on:click={openDrawer}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				viewBox="0 0 24 24"
				fill="none"
				stroke="currentColor"
				stroke-width="3"
				stroke-linecap="round"
				stroke-linejoin="round"
				class="w-6 h-6"
			>
				<line x1="3" y1="12" x2="21" y2="12" />
				<line x1="3" y1="6" x2="21" y2="6" />
				<line x1="3" y1="18" x2="21" y2="18" />
			</svg>
		</button>

		<!-- Skatebit title (on larger screens) -->
		<a
			href="/"
			class="hidden md:block text-2xl font-extrabold italic"
			data-sveltekit-preload-data="hover">Skatebit</a
		>
	</svelte:fragment>

	<!-- Center Title (visible only on mobile) -->
	<a
		href="/"
		class="block md:hidden text-2xl font-extrabold italic"
		data-sveltekit-preload-data="hover">Skatebit</a
	>

	<!-- Centered Navigation Links (visible only on larger screens) -->

	<!-- Trail Slot (Light Switch) -->
	<svelte:fragment slot="trail">
		<div class="hidden md:flex justify-center font-medium space-x-4">
			<a href="/guides" class="btn hover:bg-primary-500/10" data-sveltekit-preload-data="hover"
				>Guides</a
			>
			<a href="/mods" class="btn hover:bg-primary-500/10" data-sveltekit-preload-data="hover"
				>Mods</a
			>
			<a href="/links" class="btn hover:bg-primary-500/10" data-sveltekit-preload-data="hover"
				>Links</a
			>
			<a href="/stats" class="btn hover:bg-primary-500/10" data-sveltekit-preload-data="hover"
				>Stats & Settings</a
			>
			<div class="p-2">
				<LightSwitch />
			</div>
		</div></svelte:fragment
	>
</AppBar>
