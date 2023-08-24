<script>
	import { Block, Navbar, NavbarBackLink, Page } from 'konsta/svelte';
</script>

<Page>
	<Navbar title="Scan your content">
		<NavbarBackLink slot="left" text="Back" onClick={() => history.back()} />
	</Navbar>
	<Block>
		<p>You can scan something here:</p>
	</Block>
	<div class="w-full max-w-sm h-[30vh] bg-gray-400" />
</Page>
