<script lang="ts">
	import '@brainandbones/skeleton/themes/theme-crimson.css';
	import '@brainandbones/skeleton/styles/all.css';
	import '../app.postcss';
	import { AppShell, AppBar, Drawer } from '@brainandbones/skeleton';
	import { writable, type Writable } from 'svelte/store';
	import Navigation from '$lib/Navigation/Navigation.svelte';
	import { storeDrawer } from '$lib/Navigation/stores';

	function drawerOpen(): void {
		storeDrawer.set(true);
	}
</script>

<Drawer open={storeDrawer} position="left">
	<Navigation />
</Drawer>

<!-- App Shell -->
<AppShell slotSidebarLeft="bg-surface-500/5 w-0 lg:w-64">
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<div class="flex items-center">
					<button class="lg:hidden btn btn-sm mr-4" on:click={drawerOpen}>
						<span>
							<svg viewBox="0 0 100 80" class="fill-token w-4 h-4">
								<rect width="100" height="20" />
								<rect y="30" width="100" height="20" />
								<rect y="60" width="100" height="20" />
							</svg>
						</span>
					</button>
					<strong class="text-xl uppercase">Skeleton</strong>
				</div>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a
					class="btn btn-sm btn-ghost-surface"
					href="https://discord.gg/EXqV7W8MtY"
					target="_blank"
					rel="noreferrer">Discord</a
				>
				<a
					class="btn btn-sm btn-ghost-surface"
					href="https://twitter.com/SkeletonUI"
					target="_blank"
					rel="noreferrer">Twitter</a
				>
				<a
					class="btn btn-sm btn-ghost-surface"
					href="https://github.com/Brain-Bones/skeleton"
					target="_blank"
					rel="noreferrer">GitHub</a
				>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Left Sidebar Slot -->
	<svelte:fragment slot="sidebarLeft">
		<Navigation />
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
