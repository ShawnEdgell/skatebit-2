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
		<button class="btn m-0 p-0 md:hidden" on:click={openDrawer}>
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
		<a href="/" class="hidden md:block btn p-0 font-extrabold italic">SKATEBIT</a>
	</svelte:fragment>

	<!-- Center Title (visible only on mobile) -->
	<a
		href="/"
		class="block md:hidden btn p-0 font-extrabold italic"
		data-sveltekit-preload-data="hover">SKATEBIT</a
	>

	<!-- Centered Navigation Links (visible only on larger screens) -->
	<div class="hidden md:flex justify-center space-x-4">
		<a
			href="/guides"
			class="text-sm font-medium hover:underline"
			data-sveltekit-preload-data="hover">Guides</a
		>
		<a
			href="/tutorials"
			class="text-sm font-medium hover:underline"
			data-sveltekit-preload-data="hover">Tutorials</a
		>
		<a
			href="/contact"
			class="text-sm font-medium hover:underline"
			data-sveltekit-preload-data="hover">Contact</a
		>
	</div>

	<!-- Trail Slot (Light Switch) -->
	<svelte:fragment slot="trail">
		<LightSwitch />
	</svelte:fragment>
</AppBar>
