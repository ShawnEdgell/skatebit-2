<script lang="ts">
	import '../app.postcss';
	import { initializeStores, Drawer } from '@skeletonlabs/skeleton';
	import AppBar from '../components/AppBar.svelte';

	initializeStores();
</script>

<Drawer />

<div class="flex flex-col items-center min-h-screen">
	<div class="fixed top-0 w-full z-10">
		<AppBar />
	</div>
	<main class="prose lg:prose-xl dark:prose-invert w-full flex-1 mt-[4.5rem] px-4 py-8">
		<slot />
	</main>
</div>
