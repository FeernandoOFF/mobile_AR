<script>
	import { Block, List, ListItem, Navbar, NavbarBackLink, Page } from 'konsta/svelte';
</script>

<Page>
	<Navbar title="History">
		<NavbarBackLink slot="left" text="Back" onClick={() => history.back()} />
	</Navbar>
	<List>
		{#each [1, 2, 3, 4] as result}
			<ListItem href="/results/{result}" title="Result N {result}" />
		{/each}
	</List>
</Page>
