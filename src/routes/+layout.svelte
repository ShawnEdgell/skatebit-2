<script lang="ts">
	import '../app.postcss';
	import {
		AppShell,
		initializeStores,
		Drawer,
		getDrawerStore,
		storePopup
	} from '@skeletonlabs/skeleton';
	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
	import AppBar from '../components/AppBar.svelte';

	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow });
	initializeStores();

	const drawerStore = getDrawerStore();

	// Define the function to close the drawer
	function closeDrawer() {
		drawerStore.close();
	}

	// Navigation items array
	const navItems = [
		{ href: '/guides', label: 'Guides' },
		{ href: '/mods', label: 'Mods' },
		{ href: '/links', label: 'Links' },
		{ href: '/stats', label: 'Stats & Settings' }
	];
</script>

<Drawer>
	<ul class="p-4 space-y-2">
		{#each navItems as { href, label }}
			<li>
				<a {href} class="btn btn-lg w-full variant-filled" on:click={closeDrawer}>
					{label}
				</a>
			</li>
		{/each}
	</ul>
</Drawer>

<AppShell>
	<svelte:fragment slot="header"><AppBar /></svelte:fragment>
	<!-- Router Slot -->
	<div class="flex flex-col items-center">
		<div class="prose lg:prose-xl dark:prose-invert px-4 py-8">
			<slot />
		</div>
	</div>
</AppShell>
