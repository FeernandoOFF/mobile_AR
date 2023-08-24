<script>
	import { page } from '$app/stores';
	import { Block, Navbar, NavbarBackLink, Page } from 'konsta/svelte';
</script>

<Page>
	<Navbar title="Result N{$page.params.result}">
		<NavbarBackLink slot="left" text="Back" onClick={() => history.back()} />
	</Navbar>
	<Block>
		<p>This is your medicine</p>
		<div class="w-full max-w-sm h-[30vh] bg-gray-400" />
	</Block>
</Page>
