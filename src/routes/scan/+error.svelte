<script>
	import { Page, Block, Navbar, NavbarBackLink } from 'konsta/svelte';
</script>

<Page>
	<Navbar title="Scan your content">
		<NavbarBackLink slot="left" text="Back" onClick={() => history.back()} />
	</Navbar>
	<Block>
		<div class="grid place-items-center">
			<p class="text-5xl text-center">Oh, no! something has gone wrong!</p>
		</div>
	</Block>
</Page>
