<script lang="ts">
	import { storeDrawer } from '$lib/Navigation/stores';

	function drawerClose(): void {
		storeDrawer.set(false);
	}
</script>

<nav class="list-nav p-4">
	<ul>
		<li><a on:click={drawerClose} href="/">Homepage</a></li>
		<li><a on:click={drawerClose} href="/about">About</a></li>
		<li><a on:click={drawerClose} href="/blog">Blog</a></li>
		<li><a on:click={drawerClose} href="/contact">Contact</a></li>
	</ul>
</nav>