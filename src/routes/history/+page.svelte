<script>
	import { Block, List, ListItem, Navbar, NavbarBackLink, Page, Searchbar } from 'konsta/svelte';
	let historyItems = Array.from('123341567810111212131414');
</script>

<Page>
	<Navbar title="History">
		<NavbarBackLink slot="left" text="Back" onClick={() => history.back()} />
		<Searchbar slot="subnavbar" disableButton disableButtonText="Cancel" />
	</Navbar>
	<List>
		{#each historyItems as result}
			<ListItem href="/results/{result}" title="Result N {result}" />
		{/each}
	</List>
</Page>
