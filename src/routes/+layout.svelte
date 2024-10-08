<script lang="ts">
	import '../app.postcss';
	import { AppShell, initializeStores, Drawer, storePopup } from '@skeletonlabs/skeleton';
	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
	import AppBar from '../components/AppBar.svelte';

	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow });
	initializeStores();
</script>

<Drawer />

<AppShell>
	<svelte:fragment slot="header"><AppBar /></svelte:fragment>
	<!-- (sidebarLeft) -->
	<!-- (sidebarRight) -->
	<!-- (pageHeader) -->
	<!-- Router Slot -->
	<div class="flex flex-col items-center">
		<div class="prose lg:prose-xl dark:prose-invert px-4 py-8">
			<slot />
		</div>
	</div>
	<!-- ---- / ---- -->
	<!-- (pageFooter) -->
	<!-- (footer) -->
</AppShell>
