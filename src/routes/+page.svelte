<script>
	import { Page, Navbar, Block, Button, List, ListItem, BlockTitle } from 'konsta/svelte';
</script>

<Page>
	<Navbar title="My App" />

	<Block class="text-center ">
		<p class="text-red-500 dark:text-blue-600">
			This is text is red in white mode and blue in dark
		</p>
	</Block>
	<BlockTitle>Navigation</BlockTitle>
	<List>
		<ListItem title="Scan now" href="/scan" />
		<ListItem title="History" href="/history" />
	</List>
</Page>
