<script>
	import { Page, Navbar, Block, Button, List, ListItem, BlockTitle } from 'konsta/svelte';
</script>

<Page>
	<Navbar title="My App" />

	<Block strong>
		<p>Here is your SvelteKit & Konsta UI app. Let's see what we have here.</p>
	</Block>
	<BlockTitle>Navigation</BlockTitle>
	<List>
		<ListItem title="About" />
		<ListItem title="Form" />
	</List>

	<Block strong class="flex space-x-4">
		<Button href="/scan">Scan now</Button>
		<Button href="/history">YOur history</Button>
	</Block>
</Page>
