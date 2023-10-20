<script lang="ts">
	import '../app.postcss';
	import { AppShell } from '@skeletonlabs/skeleton';
	import Navigation from '$lib/Navigation/Navigation.svelte';
	import { AppBar } from '@skeletonlabs/skeleton';
	import { initializeStores, Drawer, getDrawerStore } from '@skeletonlabs/skeleton';

	initializeStores();

	const drawerStore = getDrawerStore();
	function drawerOpen(): void {
	drawerStore.open({});
}
</script>

<AppBar>
	<svelte:fragment slot="lead">
    <div class="flex items-center">
        <button class="lg:hidden btn btn-sm mr- " on:click={drawerOpen}>
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
</AppBar>
<Drawer><Navigation/></Drawer>
<AppShell  slotSidebarLeft="bg-surface-500/5 w-0 lg:w-64">
	<svelte:fragment slot="sidebarLeft">
		<!-- Hidden below Tailwind's large breakpoint -->
		<div id="sidebar-left" ><Navigation/></div>
	</svelte:fragment>
	<slot/>
</AppShell>

